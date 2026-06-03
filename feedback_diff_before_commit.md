---
name: diff-before-commit
description: "Always run git diff before staging/committing; never trust git status' file-level summary as a proxy for change size"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 1d6b436d-e369-4512-9932-b7397d79492c
---

Always run `git diff <file>` (or `git diff --staged`) before `git add` + `git commit`, especially when the working tree had pre-existing modifications I didn't make. `git status --short` showing ` M file.html` means "one file modified" — not "one small change." A single file can contain dozens of pre-existing uncommitted edits that will silently ride along with mine.

**Why:** On 2026-06-03, I edited `public/ai-economics.html` to add a 7-line GA snippet and ran `git add public/ai-economics.html && git commit`. The working tree also contained Vas's unfinished "Variable 5 of 5 / Seats and seat prices" work (~75 lines of additions). All of it shipped to prod under a commit message that only mentioned GA. He had to revert. The fix was easy; the trust hit was not.

**How to apply:** Before any `git add <file>` where the file might already be dirty:
1. `git diff <file>` to see what's actually changing
2. If the diff includes anything I didn't intentionally edit, STOP and surface to Vas before staging — never assume his uncommitted work is ready to ship
3. If only my intended changes show up, proceed
4. After commit, `git show HEAD --stat` to confirm the size matches expectations; if insertion count is much larger than my edit, investigate before pushing

Stricter than the default "verify before destructive action" because git commits to main on this repo auto-deploy to prod via Vercel. There is no preview/staging gate. See also [[feedback_disclose_incomplete_review]] (related discipline: never recommend/act without knowing the actual scope).
