---
name: feedback-compute-before-characterizing
description: "Compute the actual statistic before describing a dataset's magnitude (sample size, variance, range); never characterize data by eyeballing"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: c0436bcf-5ef2-4236-aab9-9ed479025194
---

Do not characterize a dataset's magnitude (how long the series is, how much a variable varies, how big a share is) until I have computed it. In the Moveo BR spend-lag work I twice asserted a magnitude before measuring: first "only 7 weeks" (Q1 weekly data existed in the `Q1_BASE` tab, making it 19), then "spend barely varies ~$900-2,100" (that is a 2.3x range, CV 18.5%, which is substantial). Both times Vas caught it with a one-line question.

**Why:** Eyeballed magnitude claims become load-bearing in the analysis (they drove the "we can't measure it" conclusion, which was wrong; the real cause was channel composition). Vas works source-first and under-claims; an unverified characterization is the same failure mode as an unverified fact. See [[feedback-verify-claims]] and [[feedback-quality-standards]].

**How to apply:** Before writing "only N weeks", "barely varies", "tiny share", "most of", etc., run the number (count, min/max, ratio, CV, sum) and quote it. If I cannot compute it yet, say "need to check" rather than asserting. For series/coverage specifically, check the base/feed sheets, not just the pre-built dashboard tabs, before concluding the data is short. Related: [[feedback-narrative-grounding]] (don't let framing run ahead of evidence).
