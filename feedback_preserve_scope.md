---
name: Preserve scope when paraphrasing findings
description: When restating quantitative findings from a paper, always carry the population (category, geography, time period) the finding applies to. CMO-friendly paraphrasing tends to strip these qualifiers silently.
type: feedback
originSessionId: eb141910-bb95-438a-9710-d1a271d55c32
---
When restating a quantitative finding from a paper in CMO-friendly language, always preserve the **scope** of the finding: the category, the geography, the time period, and the specific outcome variable.

**Why:** During Project EG website prototype work, the Pass 2 CMO summary for Joo et al. (2014) pulled correct numbers but quietly dropped scope. "+1.7% per 10% TV spend" was framed as universal when the paper measured it on 15 financial services brands over Oct-Dec 2011. The "6-11h peak" was framed as total search lift when the paper measured it on the inverted-U curve of branded vs generic keyword choice. Vas caught the first claim by asking "is this finding coming from the paper?" — verification only worked because he asked.

**How to apply:**
- Every numeric claim in a CMO summary or pitch must carry its population in the same sentence, or in the visible caption directly below the chart. Not in a footnote.
- When paraphrasing, distinguish what was *measured* (e.g., branded keyword choice) from what is *implied* (e.g., total search behavior). The paper measured the former; do not let the paraphrase implicitly upgrade the claim.
- Limitations sections should match the paper's actual scope (one category, sample size, dates, geography), not generic hedges like "older data."
- For Project EG specifically: the Pass 2 prompt needs an explicit scope-preservation rule before scaling to 225 EGs. Add to the v2 prompt set with Alec.
- This pairs with `feedback_verify_claims.md` — verification catches errors of fact, scope-preservation catches errors of generalization.
