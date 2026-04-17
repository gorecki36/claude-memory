---
name: Check the filesystem before asking identity questions
description: Do not ask the user about their roles, employer, or identity — those signals are already on disk at ~/Documents/{role}/CLAUDE.md
type: feedback
originSessionId: cbf017bc-7b94-4ca1-ab1e-1649ef9d6205
---
Do not ask Vas about his roles, employer, job title, or what he's working on at a high level. He keeps role charters in `~/Documents/{role}/CLAUDE.md` and role-named folders in `~/Documents/`. Read those first.

**Why:** He explicitly pushed back with "you have all my roles in my cloud IAM file. You have just freaking gotta be kidding me." when I asked four questions about his roles in AskUserQuestion — the information was available via Glob/Read from the start. Asking felt insulting and wasted his time.

**How to apply:** Before any AskUserQuestion about identity, role, employer, or workstream, run `ls ~/Documents/` and read any `CLAUDE.md` files in role-shaped subfolders. Only ask if something is genuinely ambiguous after reading. The same rule extends to other signals visible locally: vault contents, OneDrive folder layout, installed MCPs.
