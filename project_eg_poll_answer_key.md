---
name: project-eg-poll-answer-key
description: The Market Truths / Marketing Evidence & Truths poll answer key is the pre-launch validated Master Question Bank, not a key rebuilt from the EG corpus
metadata:
  type: project
---
The validated answer key for the Marketing Evidence & Truths poll (SurveyMonkey 423416331) is `~/Documents/mma-global/project EG/quiz/Market Truths - Master Question Bank.html` (31 Aug 2026; answers validated 15 Jul against source papers). `eg_poll_stats.load_key()` applies it.

**Why:** On 2026-09-24 Vas found the toplines had used a key rebuilt from the corpus that differed on 2 of 19 items (recession: Increases; brand switching: About 75%), overstating the score as 33% instead of 32%. He had asked for everything to be validated before launch; that work existed in `quiz/` and was not consulted.

**How to apply:** Before scoring or quoting any answer, read the Master Question Bank in `quiz/` first. Never derive answers from the corpus when a validated key exists. Related: [[feedback_verify_metric_against_primary_source]], [[feedback_check_filesystem_first]].
