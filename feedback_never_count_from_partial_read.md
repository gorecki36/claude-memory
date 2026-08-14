---
name: feedback-never-count-from-partial-read
description: "Never count or tally from a paginated/truncated tool result; page to the end or extract programmatically over the full dataset, and match on word boundaries not substrings"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: c8934d42-df63-4adf-bad4-c483bb67d592
  modified: 2026-08-14T19:14:16.010Z
---

A paginated or truncated tool result is a partial read, not a sample. Do not count, tally, or rank from it. Either page to the very end, or extract the field programmatically across the merged full response set, and print the base (`n` answering) next to every count so a wrong denominator is visible.

**Why:** Building the CCS 2026 post-event deck I counted "other industry events attended" from a verbatim dump I had only read the first ~40% of, and shipped the counts as if they covered the sample. Every figure was low, some by nearly half (CES 21 against a true 37). Vas's analyst caught it and asked whether their numbers or mine were right. Theirs were. The counts had already gone into a slide and a headline.

**How to apply:**
- When a tool result says "showing lines 1-N of M" or gets persisted to a file, treat any number derived from it as unverified until the full file has been processed in code.
- Do the counting in a script over the merged raw records, never by eye over a preview.
- Match text on word boundaries, not substrings. `ces` matches conferences/services/processes; `ana` matches analytics/management. The failure is inconsistent (some brand names survive naive matching) which makes it easy to miss.
- When someone challenges one of my numbers, recompute from source before defending it. See [[feedback-verify-metric-against-primary-source]] for the mirror case where the challenge was wrong; the discipline is the same, recompute first.

Related: [[feedback-compute-before-characterizing]], [[feedback-verify-claims]], [[feedback-quality-standards]].
