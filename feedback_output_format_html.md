---
name: feedback-output-format-html
description: "Output briefs, research notes, and standalone deliverables as styled HTML, not Markdown. Vas can't read Markdown comfortably."
metadata: 
  node_type: memory
  type: feedback
  originSessionId: e4af278f-1234-4b05-b0a9-f995e0a8c654
---

Output formal deliverables (briefs, research summaries, analysis docs, decks-in-doc-form, anything meant to be read as a finished artifact) as **HTML files with inline CSS styling**, not Markdown.

**Why:** Vas said directly "I can't really read md" (2026-05-23). Raw Markdown with `#`/`*`/`-` syntax is hard for him to skim. Styled HTML renders properly when opened in browser/Quick Look and feels like a real deliverable.

**How to apply:**
- **Standalone deliverable files** → `.html` with inline `<style>` block. Sans-serif (per [[feedback_no_serif]]), light/airy with gradient cards or subtle backgrounds (per [[feedback_design_direction]]), 18px+ body text, no chip/pill labels (per [[feedback_no_chip_pills]]), no em-dashes (per [[feedback_no_em_dashes]]).
- **Plain in-chat responses** → keep using normal Markdown formatting (the terminal renders it fine). The HTML rule is for files Vas opens separately.
- **Existing project files** → match whatever format the project already uses (Obsidian vault notes stay `.md` because Obsidian renders them; code project READMEs stay `.md`). The HTML preference applies to *new* one-off briefs and research outputs.
- **Vault notes specifically** → stay `.md` because they're consumed inside Obsidian, which renders them.

When in doubt about whether a deliverable is "standalone" vs. "project-internal," ask, but default to HTML for anything in `~/Documents/{role}/research/` or `~/Documents/{role}/tasks/`.
