---
name: reference_mcp_remote_connectors_not_loading
description: "A claude.ai remote connector can show Connected in `claude mcp list` yet expose no tools to the session; restart Claude Code to fix."
metadata: 
  node_type: memory
  type: reference
  originSessionId: d0316c26-9891-4358-9fd9-cd2acdf9f5db
  modified: 2026-09-24T22:05:18.528Z
---

`claude mcp list` health is NOT the same as tools being available in the running session.

Observed 2026-09-24: `claude.ai SurveyMonkey` reported `✔ Connected`, but no
`mcp__claude_ai_SurveyMonkey__*` tools were registered in the session. The same
applied to every other `claude.ai *` connector (Slack, Notion, Figma, Drive,
Gmail, Supabase, Canva, Vercel). The local servers defined in `~/.claude.json`
(granola, ms365, obsidian, linkedin, feedly, jev) all registered normally.

**Diagnosis order when an MCP tool "doesn't appear":**
1. `claude mcp list` — if the server shows Connected, it is not auth or config.
2. Check whether the missing tool is a `claude.ai *` remote connector vs a local
   `.claude.json` server. Remote ones are the ones that fail to register.
3. `/mcp` will not help; the connector is already enabled.
4. Fix: restart the Claude Code session. Re-auth and settings edits are wasted effort.

**No local API fallback** for SurveyMonkey: no token in env, `~/.zshrc`, or
`~/.config`. The connector is OAuth-only, so a curl workaround is not available.
The fallback is a manual CSV export from the SurveyMonkey web UI.

Allowlisting in `settings.json` (the `mcp__claude_ai_SurveyMonkey__*` entries)
only suppresses approval prompts. It does not cause the tools to load.

Related: [[reference_environment]], [[reference_cc_permissions]]
