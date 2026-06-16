---
name: The Pulse project status
description: Weekly AI self-assessment on vasteams.com; LAUNCHED 2026-03-25; usage decayed to Vas-only weeklies by late April; email reminders never built
type: project
originSessionId: c4062990-49dc-480d-bdeb-5c6227dbe6b2
---
**The Pulse** — weekly 45-second AI self-assessment on vasteams.com.

- **Path:** `/pulse`
- **API:** `/api/pulse`
- **Positioning:** "Is AI making you sharper or just faster?" Tracks how AI shapes thinking, meaning, and growth at work.
- **Tech:** Next.js + Supabase + Vercel

**Launched 2026-03-25.** Usage reality (from `responses` table, checked 2026-06-11):
- 34 submissions, 17 real participants (+1 QA account)
- Launch week Mar 25-28: 20 submissions from 13 people, then fast decay
- Last new participant: 2026-04-23. Since then 100% of submissions are Vas's own weeklies (one/week, May 11 week skipped, last 2026-06-03)
- `user_preferences` has 0 rows: the email reminder pipeline was never built, which tracks with the retention collapse

**Open items:**
- Email reminder pipeline (the missing retention mechanism)
- Launch essay for Marketing Embeddings (never published; would drive a second signup wave)
- SECURITY (RESOLVED 2026-06-16): `responses` + `user_preferences` had RLS disabled — participant data readable/writable with the public anon key. Verified ALL access to both tables goes through `createAdminSupabaseClient()` (service-role, bypasses RLS) in the `/api/pulse/*` routes; no browser component queries them directly. So enabled RLS with NO policies (`ALTER TABLE ... ENABLE ROW LEVEL SECURITY`) via migration `enable_rls_pulse_tables` — locks out anon, app unaffected. Both ERROR advisors cleared; now benign INFO `rls_enabled_no_policy`. NOTE: `pulse_heartbeat()` SECURITY DEFINER stays anon-executable on purpose — `/api/heartbeat` calls it with the anon key for keep-alive. Leaked-password protection still off (Auth dashboard toggle, minor).
- Low DB activity triggered Supabase pause warning 2026-06-10; keep-alive hardened, see [[supabase-free-tier-auto-pauses-after-7-days]]

**Why:** Flagship "Quick Build" on vasteams.com. Demonstrates AI + research positioning in action.

**How to apply:** When Pulse comes up, don't re-ask status from scratch — read this note, update after each milestone. Code at `~/Documents/personal/matrix/simulator/app/`. Query the `responses` table for ground truth on usage, not this note.

**Related:** [[personal/vasteams.com]] in the Obsidian vault has full site/tool inventory.
