---
name: Supabase free tier auto-pauses after 7 days
description: Supabase pauses free-tier projects after 7 days of inactivity; caused vasteams.com Pulse to go down 2026-05-20
type: reference
originSessionId: 0150e8c3-3bbf-4b2c-8c0b-89d9aad34358
---
Supabase free-tier projects auto-pause after 7 days of inactivity. When paused, DNS stops resolving entirely (not just slow -- unreachable). Restoring takes 5-10 minutes and shows 521 errors during boot.

**vasteams.com Supabase project:** `zbhajokmkznwwcklypdg`
**Health check:** `curl -s -o /dev/null -w "%{http_code}" https://zbhajokmkznwwcklypdg.supabase.co`
**Dashboard:** https://supabase.com/dashboard/projects

**Impact on 2026-05-20:** Site went down with 504 errors. The middleware was calling Supabase auth on every request including the homepage. Fixed by removing `/` from middleware matcher and adding fail-open try/catch.

**How to apply:**
- Check Supabase is alive weekly (or set up a cron ping)
- If Pulse has no users for a week, Supabase will pause again
- Options to prevent: upgrade to Pro ($25/mo), or set up a weekly cron that hits the Supabase API to keep it alive
- The `/api/pulse/cron` route already exists and could serve as a keep-alive if called weekly
