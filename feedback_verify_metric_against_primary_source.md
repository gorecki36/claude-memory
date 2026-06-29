---
name: feedback-verify-metric-against-primary-source
description: "Before flagging a number as wrong, verify against the team's OWN primary source (the deck/report) and confirm it is the same metric. A web figure that disagrees usually measures something different (conditional vs unconditional, base, window), not an error."
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 478e380c-715d-4c88-8aa6-df2545e3224b
---

**Do not call a number wrong without primary-source verification, the same way you never assert a claim is true without it.** Over-flagging a correct, well-sourced figure is as damaging as letting a false one through: it strips accurate claims and costs trust.

**Incident (2026-06-29):** In the MRS Thought Leadership entry I flagged "83% of these searches end without a click (Similarweb, May 2025)" as incorrect, based on a web search returning Similarweb's ~69% overall zero-click rate. The team's own deck showed 83% is the zero-click rate **conditional on an AI Overview appearing** (Without AIO 60%, With AIO 83%, AI Mode 93%; Similarweb May 2025). The submission's "of these [AI-summary] searches, 83% end without a click" matched the deck exactly. My 69% was a different, unconditional metric. I then changed a correct number to a wrong one in the rebuild before catching it.

**How to apply:**
1. Before calling a number wrong, check the **primary source it came from** (the deck or report the team built), not a generic web search.
2. When a web figure disagrees, confirm you are comparing the **same metric**: conditional vs unconditional, base population, time window, geography, definition. A different number usually means a different measure, not an error.
3. If a figure does look off, say "this looks like a different metric, let me check the deck," not "this is wrong."

Mirror of [[feedback_never_assert_compliance]] (do not assert TRUE without a source) and a refinement of [[feedback_research_before_refuting]] (a web search alone is not enough; match the metric and prefer the team's primary source). Full incident also in vault `mma/Operational Lessons` (lesson 7) and `~/Documents/mma-global/tasks/lessons.md`.
