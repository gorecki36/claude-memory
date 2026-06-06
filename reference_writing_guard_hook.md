---
name: reference-writing-guard-hook
description: "Writing-enforcement hook that blocks banned patterns in published prose files; scope, tuning, bypass"
metadata: 
  node_type: memory
  type: reference
  originSessionId: 3b59a10e-1343-419d-8594-fb9a9937eeb6
---

A writing guard enforces Vas's voice rules at the harness level, because CLAUDE.md/memory are passive context that decay over a session and never execute. Only hooks execute.

**Principle Vas set:** the guard polices the OUTPUT people read, not the process of producing it. So it scans published, reader-facing files only. No chat scanning, no code, no KB/memory.

- **Script:** `~/.claude/writing-guard.py`. **Wired in** `~/.claude/settings.json` as a PostToolUse hook on `Write|Edit` (no Stop hook anymore).
- **Scope:**
  - Writing rules (long-dash, jargon, the silence word, stale "just" + past verb) run on prose deliverables: `.md` `.mdx` `.html` `.txt`.
  - The chip/pill CSS rule runs on style/component files: `.css` `.scss` `.tsx` `.jsx` `.html`.
  - Skipped entirely: anything under the Obsidian vault or `~/.claude` (process/KB), and all other extensions (code, config, shell, JSON).
- **Behavior:** on a hit it exits 2 and writes the offending matches to STDERR, which blocks the write and forces a fix before the file ships. Fails OPEN on any error.
- **Bypass:** the token `[[skip-guard]]` anywhere in the content skips the check (used when legitimately quoting a banned term; it sits in the guard's own docstring so the script can edit itself).
- **Tuning:** edit the `WRITING_PATTERNS` / `JARGON` / `STYLE_PATTERNS` lists, `PROSE_EXTS` / `STYLE_EXTS`, or `EXCLUDE_PREFIXES` at the top of the script. Jargon list started tight (~18): leverage, synergy, seamless, utilize, delve, boast, myriad, plethora, robust, elevate, garner, tapestry, "it's worth noting", "that said", "in today's world", "ever-evolving", "navigate the landscape", "game-changer".
- **Caveat:** a newly-added or rewired hook may need `/hooks` opened once or a CLI restart to load; the script file itself is re-read on every run.

Enforces the same rules as [[feedback_no_em_dashes]], [[feedback_no_stale_just]], [[feedback_plain_headlines]], [[feedback_no_chip_pills]], [[feedback_quality_standards]] mechanically rather than by reminder. Configured via [[reference_environment]].
