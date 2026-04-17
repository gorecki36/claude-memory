---
name: Vas's tooling environment and canonical paths
description: Where things live — Obsidian vault, OneDrive corpora, installed MCPs, per-role folders
type: reference
originSessionId: cbf017bc-7b94-4ca1-ab1e-1649ef9d6205
---
**Canonical paths:**
- Obsidian vault: `~/Documents/Obsidian Vault/` (currently nearly empty: 2 notes, 406 bytes, folders `MMA work/` and `Welcome.md`)
- Per-role charters and workspaces: `~/Documents/{mma-global,moveo,mbriyo,vas collective,personal}/`
- MMA OneDrive corpus: `~/Library/CloudStorage/OneDrive-MMAGlobal/` (includes `AI MMA Upskilling/MMA GPTs/MMA Knowledge GPT/Knowledge Files/` — an already-curated MMA knowledge corpus)
- Claude Code config: `~/.claude/` (commands at `~/.claude/commands/`, plans at `~/.claude/plans/`)
- `~/Documents/global-CLAUDE.md` is a symlink to `~/.claude/CLAUDE.md` — currently dangling, file doesn't exist

**Installed MCPs (as of 2026-04-15):**
- Data sources: Fireflies (meeting transcripts), Gmail, Google Drive, Google Calendar, Notion, Slack, MS365 (covers OneDrive / Outlook / Teams), Obsidian
- Build/deploy: Vercel, Figma, Parallel Search
- Obsidian MCP supports read/write/search/tags/frontmatter — use it instead of shell file ops for vault work

**Mbriyo has a `/session-notes` pattern** — at the start of each Mbriyo conversation, check `~/Documents/mbriyo/notes/` for recent session notes.
