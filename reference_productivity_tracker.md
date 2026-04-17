---
name: Productivity tracker
description: Per-session collaboration tracker with role filtering; logs prompts, turns, tool calls, tokens, and 15-min satisfaction ratings
type: reference
originSessionId: c4062990-49dc-480d-bdeb-5c6227dbe6b2
---
Location: `~/.claude/productivity/` (git-versioned — `git log` to see history).
- `tracker.py` — CLI
- `events.jsonl` — append-only event log (committed to git)
- `dashboard.html` — generated visualization (gitignored)
- `.current_role` — active role tag (gitignored)

Hooks (in `~/.claude/settings.json`):
- `UserPromptSubmit` → `tracker.py log-prompt` (logs chars/words + cwd + role)
- `Stop` → `tracker.py log-stop` (logs tool_calls + tokens + cwd + role; blocks Stop every 15 min to request a 1-5 rating)

CLI commands:
- `tracker.py rate <1-5> [note]` — record satisfaction
- `tracker.py tag <mma|moveo|embeddings|mbriyo|personal>` — set current work's role (overrides cwd detection). Use `tag clear` to revert to auto.
- `tracker.py status` — today's totals
- `tracker.py weekly` — 7-day rollup by day
- `tracker.py viz` — regenerate `dashboard.html` (has role filter chips)
- `tracker.py backfill [--reset]` — parse historical `~/.claude/projects/-Users-vasbakos/*.jsonl`

Roles: `mma, moveo, embeddings, mbriyo, personal`. Auto-detected from cwd via path-prefix map (e.g. `/Documents/mma-global` → mma). Unknown paths default to "personal". Manual tag via `tracker.py tag` persists across sessions via `.current_role` file.

Metrics tracked:
1. User messages per day (count)
2. Chars per message (spell-it-out proxy) + turns per session (back-and-forth proxy)
3. Claude tool calls per day
4. Input + output tokens per day
5. Satisfaction rating (1-5, every 15 min)

When the Stop hook prompts with "Productivity check-in: N min since last rating", ask the user for a 1-5 rating, then call `tracker.py rate <N> [note]`.

**Deployment status:** Local git repo initialized 2026-04-17. No remote yet — user may want to push to a private GitHub repo for off-machine backup.
