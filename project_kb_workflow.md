---
name: LLM knowledge base workflow (Karpathy-style)
description: Vas is building an Obsidian-based LLM-compiled wiki; current state, seed role, scope decisions
type: project
originSessionId: cbf017bc-7b94-4ca1-ab1e-1649ef9d6205
---
Vas is adopting the Karpathy-style "LLM-compiled markdown wiki in Obsidian" workflow. Plan approved 2026-04-15, stored at `~/.claude/plans/hidden-baking-gadget.md`.

**Scope decisions he's made:**
- Seed role: **MMA Global** first (highest volume, clearest taxonomy). One-week trial before scaling.
- Cross-role synthesis: "nice to have" — single vault with role-scoped folders + tags, not separate vaults.
- No confidentiality constraints across roles — cross-linking is fine.
- Skip Vas Collective (too little content). Personal role is last in priority order.

**Why:** Multi-role operator (MMA Global SVP, Moveo CMO, Mbriyo owner, Vas Collective, Personal) — needs the KB to surface value **within** each role and **across** roles without over-bootstrapping.

**How to apply:**
- Vault lives at `~/Documents/Obsidian Vault/` (NOT `~/Obsidian Vault/` — the plan file has that path slightly wrong).
- Structure: `raw/{role}/`, `wiki/{role}/`, `indexes/`, `generated/`.
- Do NOT re-ingest the existing OneDrive "MMA Knowledge GPT" corpus into `raw/` — point the compile loop at it in place.
- Skills to build (in order): `/kb-ingest-fireflies`, `/kb-compile`, `/kb-ask`, `/kb-lint`. All scoped by `--role` flag.
- Git-init the vault; every compile run must commit — LLM-maintained content needs undo.
- Biggest risk he's been warned about: over-scoping to all five roles at once. Stay MMA-only until the single-role loop earns its keep.
