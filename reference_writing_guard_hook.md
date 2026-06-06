---
name: reference-writing-guard-hook
description: Writing-enforcement hook that hard-blocks banned writing patterns; how to tune it and bypass it
metadata: 
  node_type: memory
  type: reference
  originSessionId: 3b59a10e-1343-419d-8594-fb9a9937eeb6
---

A writing guard enforces Vas's voice rules at the harness level, because CLAUDE.md/memory are passive context that decay over a session and never execute. Only hooks execute.

- **Script:** `~/.claude/writing-guard.py`. **Wired in** `~/.claude/settings.json` as a Stop hook (scans my final assistant message via `transcript_path`) and a PostToolUse hook on `Write|Edit` (scans written file content).
- **Behavior:** on a banned pattern it exits 2 and writes the offending matches to STDERR, which blocks the turn and forces a revision before Vas sees the text. Fails OPEN on any error (never blocks on a guard bug).
- **Bypass:** include the token `[[skip-guard]]` in the text. Needed when legitimately quoting or discussing a banned term (e.g. explaining the blocklist itself).
- **Tuning:** edit the `PATTERNS` and `JARGON` lists in the script. Started tight/high-confidence (~18 jargon terms): leverage, synergy, seamless, utilize, delve, boast, myriad, plethora, robust, elevate, garner, tapestry, "it's worth noting", "that said", "in today's world", "ever-evolving", "navigate the landscape", "game-changer". Plus: em-dash, "quiet", stale "just"+past-verb, chip/pill `border-radius:999px`.
- **Caveat:** newly-added hooks may not fire until `/hooks` is opened once or the CLI restarts (settings watcher).

Enforces the same rules as [[feedback_no_em_dashes]], [[feedback_no_stale_just]], [[feedback_plain_headlines]], [[feedback_no_chip_pills]], [[feedback_quality_standards]] — but mechanically rather than by reminder. Configured via [[reference_environment]].
