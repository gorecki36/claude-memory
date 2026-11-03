---
name: project_knotch_report_webinar_sync
description: "Knotch report and webinar deck must stay in sync; two generators, shared slides come from the report generator, seven webinar-only slides need hand mirroring"
metadata:
  node_type: memory
  type: project
  originSessionId: 1cdc26fd-88fc-434e-8d72-20784bf137b8
  modified: 2026-11-03T18:46:40.147Z
---

Knotch deliverables (as of 2026-11-03) live in `~/Documents/mma-global/knotch/`:
- Report: `gen_survey_report_v3.py` -> `Knotch survey report 3-xx.html` (+ PDF via headless Chrome). 45 slides: foreword, goal, methodology, exec summary (verdicts), agenda, Part A (3 Knotch slides), Part B (4 chapters), six moves. Design: black/gold/warm grey, bare line icons, light-gold tint for Knotch data, agenda strip on every divider.
- Webinar deck (Nov 11 2026, "AI and the Changing Consumer Journey"): `gen_webinar_deck.py` imports the report generator -> `Webinar deck 1-xx.html`. 20 slides.
- Run of show: `Webinar run of show 1-00.html`.

**Why:** Vas asked (2026-11-03) that any change made to the report is also made to the relevant webinar slides and vice versa.

**How to apply:** Goal, methodology, agenda components, Part A chart slides, verdicts and six moves are shared code: rebuild BOTH decks after any edit and name both new version numbers. Seven webinar-only slides (54x pair, engaged on arrival, sense the shift, see it and act, the limits, leaders vs laggards, panel) are in the webinar generator and must be mirrored by hand. Always say which deck is open in Chrome; Vas mistook the webinar deck for the report once.
