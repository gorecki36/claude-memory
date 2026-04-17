---
name: Mbriyo deployment
description: Repo, hosting (Vercel), git auth (SSH), deploy steps, known issues with pushing from Claude Code
type: reference
originSessionId: c4062990-49dc-480d-bdeb-5c6227dbe6b2
---
**Mbriyo deployment info.** (Reconstructed — verify specifics against current setup.)

- **Repo:** GitHub, SSH auth (`git@github.com:...`)
- **Hosting:** Vercel (auto-deploys from main branch)
- **Local path:** `~/Documents/mbriyo/`
- **Role charter:** `~/Documents/mbriyo/CLAUDE.md`

**Known friction:** Git pushes from inside Claude Code have historically had intermittent auth issues. If `git push` fails from a tool call, check SSH agent (`ssh-add -l`) and consider pushing from a terminal outside Claude Code instead. When it works, SSH remote is the path that succeeds.

**Deploy:** commit to main + push → Vercel picks up automatically, no extra step.

**How to apply:** When touching Mbriyo work, read this note first. If a push fails, don't loop on retries — flag for Vas to push from terminal. Specific deploy commands and env vars live in the charter.
