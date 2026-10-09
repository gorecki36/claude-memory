---
name: feedback-surveymonkey-weighted-average
description: SurveyMonkey "Weighted Average" in summary exports is a column index, wrong for 0-based scales and bucketed counts; recompute from the distribution
metadata:
  type: feedback
---
SurveyMonkey's summary-export "Weighted Average" scores the columns 1..N. It is wrong for a 0-10 scale (NPS-style question: 9.51 reported, true mean 8.51) and for count buckets (workflows 0..10, 11-20, 21+: 5.97 reported, true median 5). Boost Awards put both artifacts into the AI-AF Digiday entry on 2026-10-08.

**Why:** These numbers go into signed award entries and decks; an off-by-one-point score is a false claim.
**How to apply:** Whenever a SurveyMonkey export is used, recompute means/medians/NPS from the response counts. Check that the scale starts at 0 or 1, and check any bucketed answers. Related: [[feedback_compute_before_characterizing]], [[feedback_verify_metric_against_primary_source]].
