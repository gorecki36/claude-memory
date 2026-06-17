---
name: reference_vasteams_smoke_test
description: "vasteams.com render smoke test + the \"pin every CDN dependency\" rule after /ai-economics.html went blank from unpinned Babel"
metadata: 
  node_type: memory
  type: reference
  originSessionId: 1a2da5a8-9df6-4117-9667-9041a2e212cd
---

vasteams.com has a render smoke test at `~/Documents/personal/matrix/simulator/app/scripts/smoke/` (`smoke-test.mjs`, Playwright pinned `1.49.1`) run by `.github/workflows/smoke-test.yml` daily at 09:00 UTC. It loads all 11 public pages in headless Chromium and FAILs (emailing repo admins) if a page is 4xx/5xx, throws, hits a fatal console error, or renders below a per-page visible-text floor. Run locally: `cd scripts/smoke && npm install && npm test`. Add/adjust pages in the `PAGES` array (homepage floor is 150 — sparse ~223-char landing page). Catches *blank renders* (server up, page broken) that a URL pinger cannot.

**Rule it enforces:** never load an unpinned "latest" of a runtime compiler/library from a CDN — pin every external `<script src>` to at least a major version. Origin: 2026-06-17 `/ai-economics.html` rendered blank in prod (HTTP 200, never painted) because `@babel/standalone` was loaded unpinned; unpkg served a newer Babel whose react preset defaults to the automatic JSX runtime, emitting an unresolvable `react/jsx-runtime` import. Fix: pin `@babel/standalone@7` + register a `react-classic` preset (`runtime:'classic'`). Only the `ai-economics*.html` static pages use in-browser Babel; other tools are Next.js routes compiled at build time.

Full incident + monitor details in the Obsidian note [[vasteams.com]] (2026-06-17 entry). Related: [[reference_supabase_free_tier]] (the other silent-failure layer), [[feedback_dont_stop_midtask]] (on a prod-down report, fix→verify→ship, don't gate on deploy-method questions — rated 1/5 for stalling here).
