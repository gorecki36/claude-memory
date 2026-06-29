---
name: feedback_deck_design_system
description: "Default layout rules for Vas's reveal.js decks so slides fill the canvas and aren't small/ugly — apply by default, stop making him repeat per-slide fixes"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: b55e6cb0-a43a-49d5-91ed-10b2004f4e3f
---

Vas has corrected the same deck problems many times: slides leave 40-50% of the canvas empty, elements are too small, jargon is used as hero numbers, and +/- data is drawn as same-direction bars. Apply these by default on every deck, do not wait to be told.

**Fill the canvas.** Never a thin band of small content floating with empty top/bottom. For multi-block slides set the body to `justify-content:space-evenly`; give process/step and stat cards large `min-height` (~300px+) so centered content nearly fills the slide.

**Big components.** Step/process cards: a 50-60px gold icon on top, ~1.3rem title, ~1.05rem description. Stakes/bullet text ~1.4rem. Headlines bold ~clamp(1.5-2rem); split long ones.

**Icons on cards.** Every dimension/step card gets an inline-SVG line icon in gold (no external assets).

**Hero = one meaningful number + one plain sentence.** No jargon on the slide face (e.g. translate "0.86 AUC" to "picks the better-converting ad 86% of the time"). Spell out any acronym once. Put technical detail in a small footnote. Never stack 3-4 competing similar numbers.

**Diverging chart for +/- data.** Positive one side, negative the other side of a center axis (gold = higher/positive, slate = lower/negative). Not same-direction bars.

**Group into labeled families with a divider** when the content has categories (e.g. Kroger-specific vs executional). Mark do/avoid with gold check / grey cross, not pills.

**Consistency + build hygiene.** Reconcile numbers across slides (e.g. ~30 attributes = 231 levels). Build via a Python generator, never hand-edit the HTML, and verify each slide with a headless Chrome screenshot (`--headless --screenshot`, `#/<n>`) before showing.

**House template:** start from the generator CSS in `~/Documents/mma-global/vidmob/gen_kroger_narrative_deck_v2.py` (gold/black system, all components above).

Related: [[feedback_use_full_page_width]] [[feedback_no_chip_pills]] [[reference_research_presentation_process]] [[process_figma_visuals]]
