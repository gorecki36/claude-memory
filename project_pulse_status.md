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
- SECURITY: `responses` + `user_preferences` have RLS disabled; participant emails readable with the public anon key. Check how /api/pulse/submit authenticates before enabling RLS. Flagged to Vas 2026-06-11, decision pending.
- Low DB activity triggered Supabase pause warning 2026-06-10; keep-alive hardened, see [[supabase-free-tier-auto-pauses-after-7-days]]

**Why:** Flagship "Quick Build" on vasteams.com. Demonstrates AI + research positioning in action.

**How to apply:** When Pulse comes up, don't re-ask status from scratch — read this note, update after each milestone. Code at `~/Documents/personal/matrix/simulator/app/`. Query the `responses` table for ground truth on usage, not this note.

**Related:** [[personal/vasteams.com]] in the Obsidian vault has full site/tool inventory.
