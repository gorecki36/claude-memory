---
name: Stop hook stderr rule
description: Claude Code Stop hooks must echo blocking feedback to stderr, not stdout, or the harness wraps it as "[<path>]: No stderr output"
type: feedback
originSessionId: ef2525a9-ceb6-49d5-862b-1de99e89305a
---
Stop hooks (and other exit-2 blocking hooks) in Claude Code must write their feedback message to **stderr**, not stdout. If the hook does `echo "msg"` (stdout) + `exit 2`, the harness surfaces the noise `[<path>]: No stderr output` instead of the actual message — and you'll get that meaningless feedback on every turn while the blocking condition holds.

**Why:** Claude Code's hook harness reads `stderr` to determine what to show as user-visible feedback when a hook exits non-zero. Stdout output from old-style exit-2 hooks is silently discarded. Newer JSON-style hooks (printing `{"decision":"block","reason":"..."}` to stdout) work differently and bypass this.

**How to apply:**
- For any shell Stop hook that uses `echo + exit 2`, always pipe the echo to stderr: `echo "msg" >&2 && exit 2`.
- If you ever see repeated `Stop hook feedback: [<path>]: No stderr output` in a session, that's the signature — fix the script, don't chase ghosts.
- For Python/JSON-style hooks (like `~/.claude/productivity/tracker.py`), print the JSON to stdout as normal — those use the new protocol.

**Caught at:** 2026-05-22, after the vault-session-end.sh hook noise spammed the conversation tens of times until Vas asked "what the heck is wrong with you". One-line fix in `~/.claude/vault-session-end.sh:38` added `>&2`.
