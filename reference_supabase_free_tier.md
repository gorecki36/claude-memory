---
name: supabase-free-tier-auto-pauses-after-7-days
description: "Supabase pauses free-tier projects after 7 days of inactivity; broke vasteams.com Pulse twice (2026-05-20, 2026-05-28). Fixed with dedicated /api/heartbeat cron and SECURITY DEFINER RPC."
metadata: 
  node_type: memory
  type: reference
  originSessionId: af55e7c0-86f3-48d0-aa9e-9e323d6c293d
---

Supabase free-tier projects auto-pause after 7 days without sufficient external traffic. When paused, fetches throw `TypeError: fetch failed` (not slow, just unreachable). Restoring takes 1-3 minutes via `restore_project` MCP call.

**vasteams.com Supabase project:** `zbhajokmkznwwcklypdg`
**Project name:** congition
**Dashboard:** https://supabase.com/dashboard/projects
**Quick status check (via MCP):** `mcp__claude_ai_Supabase__get_project` with that ID, look for `status: "INACTIVE"` vs `"ACTIVE_HEALTHY"`.
**Quick recovery:** `mcp__claude_ai_Supabase__restore_project` with that ID.

## Outage history

- **2026-05-20:** Site went down with 504. Middleware called Supabase on `/` even when Supabase was slow. Fixed by removing `/` from middleware matcher and adding fail-open try/catch.
- **2026-05-28:** Pulse weekly form showed `TypeError: fetch failed`. Supabase had been paused 6 days after May 22 commit. Existing `/api/pulse/cron` was supposed to keep it warm but was fragile:
  - Returns 401 if CRON_SECRET missing
  - Returns 500 if RESEND_API_KEY missing
  - Only THEN queries DB (a SELECT, on a 1-row `user_preferences` table filtered by `reminder_day = today`)
  - Any of those failure modes → no DB activity → eventual pause

## The fix (applied 2026-05-28)

Dedicated `/api/heartbeat` endpoint with single purpose:

1. **Migration** (already applied to the project): `heartbeat_keepalive`. Created `public.heartbeat` (singleton row, RLS enabled, no direct write policies) and `public.pulse_heartbeat()` (SECURITY DEFINER RPC, executable by `anon`).
2. **Route** at `src/app/api/heartbeat/route.ts`: instantiates anon-key Supabase client, calls `client.rpc("pulse_heartbeat")`. No auth check, no env dependencies beyond `NEXT_PUBLIC_SUPABASE_*`.
3. **Cron** in `vercel.json`: `"0 */6 * * *"` (every 6 hours, 4 hits/day, 28 hits per 7-day window).

The heartbeat goes through PostgREST as external traffic, which is what Supabase's pause heuristic measures.

## How to apply (future projects on Supabase free tier)

Same pattern works for any free-tier Supabase project on Vercel:
- Heartbeat table with singleton row, RLS locked
- SECURITY DEFINER function executable by `anon`
- Public route calling the RPC via anon client
- Vercel cron every 6 hours

The Pulse-specific `/api/pulse/cron` (reminder emails) should NOT be relied on for keep-alive: too many failure modes between cron firing and DB being hit.

For belt-and-suspenders: add an external uptime monitor (UptimeRobot free tier) that pings the heartbeat endpoint hourly and alerts on failure. Catches the case where Vercel cron itself stops firing.

Related: [[feedback_no_auth_on_public_pages]], [[build-lessons]] pattern 4 (rules must be encoded in the build).
