---
name: V2 CFO App project
description: Built a full-stack CFO intelligence app for V2 (son's DTC clothing brand); scaffolded, demoed, packaged for handoff
type: project
---

Built a CFO app for V2 — a DTC clothing brand doing $500K-$2M ARR, selling via Shopify, using QuickBooks, traditional bank (Plaid), and Meta/Google/TikTok ads. Primary pain point: cash flow is tight (inventory ties up cash).

**What was built:**
- Full-stack app: FastAPI + Next.js, 88 files, 6,451 lines
- 3 production connectors (Shopify, Plaid, QuickBooks), 3 stubs (Meta, Google, TikTok)
- 5 metrics modules: cash flow, margins, inventory, acquisition, revenue
- AI layer: Claude-powered Q&A, weekly briefings, anomaly detection
- 8 dashboard pages with mock data prototype running
- Background job scheduler for all sync frequencies

**Where it lives:**
- Source code: `~/projects/v2-cfo/` (git repo, 2 commits)
- Handoff zip: `~/Documents/v2/v2-cfo.zip`
- Handoff doc: `HANDOFF.md` in the repo root

**Status:** Scaffolded + demoed with mock data. Not production-ready. Needs: API keys, PostgreSQL + Redis, Alembic migrations, end-to-end testing with real Shopify data. Estimated 2-3 weeks for a dev to take to production.

**Why:** Vas's son is the founder of V2. The app was packaged for handoff to V2's team to take live.
