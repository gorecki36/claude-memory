---
name: feedback-output-format-html
description: "Output briefs, research notes, and standalone deliverables as styled HTML, not Markdown. Vas can't read Markdown comfortably."
metadata: 
  node_type: memory
  type: feedback
  originSessionId: e4af278f-1234-4b05-b0a9-f995e0a8c654
---

**NEVER hand Vas a `.md` deliverable file.** He restated this flatly as "never use md" (2026-06-23) after I saved two MRS award drafts as `.md`. Pick the format by workflow: HTML for standalone briefs/research; **`.docx` (Word) when the workflow is document-based and shared with colleagues** (award entries, anything where the surrounding artifacts are already `.docx`, e.g. the ESOMAR drafts, or where a colleague like Alex works in Word). Use `python-docx` to generate `.docx` directly. Output formal deliverables (briefs, research summaries, analysis docs, decks-in-doc-form, anything meant to be read as a finished artifact) as **HTML with inline CSS** or **`.docx`**, never Markdown.

**Why:** Vas said directly "I can't really read md" (2026-05-23) and "never use md" (2026-06-23). Raw Markdown with `#`/`*`/`-` syntax is hard for him to skim, and Word/HTML feel like real deliverables.

**How to apply:**
- **Word-document workflows (awards, submissions, anything alongside existing `.docx`)** → `.docx` via `python-docx`. Match the format of files already in the folder.
- **Standalone briefs/research notes** → `.html` with inline `<style>` block. Sans-serif (per [[feedback_no_serif]]), light/airy with gradient cards or subtle backgrounds (per [[feedback_design_direction]]), 18px+ body text, no chip/pill labels (per [[feedback_no_chip_pills]]), no em-dashes (per [[feedback_no_em_dashes]]).
- **Plain in-chat responses** → keep using normal Markdown formatting (the terminal renders it fine). The HTML rule is for files Vas opens separately.
- **Existing project files** → match whatever format the project already uses (Obsidian vault notes stay `.md` because Obsidian renders them; code project READMEs stay `.md`). The HTML preference applies to *new* one-off briefs and research outputs.
- **Vault notes specifically** → stay `.md` because they're consumed inside Obsidian, which renders them.

When in doubt about whether a deliverable is "standalone" vs. "project-internal," ask, but default to HTML for anything in `~/Documents/{role}/research/` or `~/Documents/{role}/tasks/`.
