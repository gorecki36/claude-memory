---
name: feedback-output-contract
description: "Where output goes: short answers in chat, long answers as .md opened in Cursor, deliverables as .html opened in Chrome. Always open the file."
metadata:
  type: feedback
---

**Simplify the answer first, then route it.** Set 2026-08-31 when Vas showed his Cursor layout: roughly 25 named, colour-coded Claude sessions in the right rail, every response landing as a wall of text in one middle scroll, and the editor pane above it sitting on a file-not-found error.

- Normal answer: short, in chat.
- An answer that still runs longer than about two thirds of a page after editing: write a `.md` file and `open -a Cursor <path>`.
- A **deliverable** (report, brief, email draft, analysis, deck, one-pager, anything treated as a finished artifact): `.html` with inline CSS, and `open -a "Google Chrome" <path>`.

**Why:** he runs many workstreams in parallel and can only see one at a time. Long prose in the scroll buries the one line that matters and forces a re-read every time he switches sessions. Chrome renders a designed page properly; the Cursor editor pane shows HTML as source code and can only preview plain Markdown.

**How to apply:**
- Length is a failure to edit, not a reason to make a file. Cut before routing.
- Never paste a deliverable into chat. Automatically, without asking first.
- One artifact per turn. The path replaces the summary, never both.
- Always run the `open` command. A reported path he has to open himself does not count.
- The `.md` route is for long **answers during the work** only. It does not soften [[feedback_output_format_html]]: deliverables are never `.md`.
- End every response with a status line: `[topic] · done | blocked | waiting · next: <the one thing>`.

Related: [[feedback_short_responses]], [[feedback_output_format_html]], [[feedback_file_locations]], [[feedback_specify_file_paths]].
