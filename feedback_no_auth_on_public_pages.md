---
name: Never put auth middleware on public pages
description: Supabase auth middleware on homepage caused 504 gateway timeout when Supabase was slow; site went down
type: feedback
originSessionId: 0150e8c3-3bbf-4b2c-8c0b-89d9aad34358
---
Never put auth/session middleware on public pages (homepage, about, research, work, projects, ai-clock).

**Why:** On 2026-05-20, vasteams.com went down with 504 GATEWAY_TIMEOUT because the Supabase auth middleware was running on `/` (homepage). When Supabase was slow, the `auth.getUser()` call hung for 30s until Vercel's middleware timeout killed it. The middleware had been on `/` since The Pulse was built -- it was a latent bug that detonated when Supabase had a slow moment.

**How to apply:**
- Middleware matcher must ONLY include paths that require auth (e.g. `/pulse/*`, `/api/pulse/*`, `/auth/*`)
- Never add `/`, `/about`, `/research`, `/work`, `/projects`, `/ai-clock` or any public page to the matcher
- All auth middleware must fail open: wrap external calls in try/catch so a slow third-party service degrades gracefully instead of taking down the site
- Before deploying any middleware change, check the matcher array and ask: "Would this 504 the homepage if this service is down?"
