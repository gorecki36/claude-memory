---
name: feedback-dont-drop-top-risk
description: "When Vas approves a subset of edits, don't silently ship only those and leave the highest-risk item dangling; surface the biggest open risk at the decision moment"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 5afd32af-d7eb-44ca-ac4c-ba20398d90de
---

When I've identified the single highest-risk problem in a deliverable, do not let "approved scope" override it. If Vas approves a subset of fixes that excludes the biggest risk, flag that explicitly **at the moment of handing back** ("before I give you this, the highest-risk item is still unfixed, do you want it in?"), rather than quietly delivering the lesser edits and parking the big one in a "still open" footnote.

**Why:** On the ESOMAR Reddit submission I called the 27-month reconciliation the single thing most likely to sink the entry, then shipped the two smaller approved edits (AI-visibility relabel, 48.2% cut) and left the 27-month gap unaddressed and buried. Vas had to be the one tracking that the top risk got dropped. Scored 1/5.

**How to apply:** Treat user approval as a floor, not a ceiling. At every handoff, restate the biggest open risk in one line and force the decision. Don't bury it; don't bundle it without asking either. Caution after a wrong first attempt is fine, but a flagged-and-pending item must not silently drift off the plate. Relates to [[feedback_dont_stop_midtask]] and [[feedback_disclose_incomplete_review]].
