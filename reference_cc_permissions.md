---
name: cc-permissions
description: Claude Code permissions config in global settings.json — acceptEdits mode + read-only/export allowlist to reduce approval prompts
metadata: 
  node_type: memory
  type: reference
  originSessionId: dab83365-f45b-4c60-af02-b5a37a4a9c82
---

Global `~/.claude/settings.json` (backup `settings.json.bak`) was configured 2026-06-16 to cut approval prompts during deliverable work (deck/report building, website checks). Decided from a scan of the 50 most recent session transcripts.

- **`permissions.defaultMode: "acceptEdits"`** — Write/Edit no longer prompt (biggest source, ~886 calls). Destructive bash (`rm`), publishing, and out-of-scope actions still confirm.
- **`permissions.allow` (26 entries):** `WebFetch`, `WebSearch`, `Bash(open:*)`, the Chrome binary (deck-to-PDF render), and read-only MCP tools (SurveyMonkey, Obsidian read/search, Fireflies, Granola, Gmail read, Vercel list_deployments, Supabase get_advisors, Drive search_files).
- **Still gated by design:** `npx`/`decktape` and `python3` (arbitrary code exec), `deploy_to_vercel`, Obsidian `patch_note`/`write_note`. The decktape PDF-export step still prompts once per run.

Rule for future edits: never wildcard an interpreter/package-runner (`python3`, `node`, `npx`) — equals "run any code without asking." Use `/fewer-permission-prompts` to regenerate the read-only allowlist from transcripts. Full record in vault: tech-stack/Overview.md. Related: [[reference-environment]], [[reference-productivity-tracker]].
