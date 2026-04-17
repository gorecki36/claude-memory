---
name: Survey analysis to executive presentation process
description: End-to-end workflow for turning SurveyMonkey data into CMO-grade interactive presentations with findings, cross-tabs, and significance testing
type: reference
originSessionId: 10b3b38f-882b-4ec5-8b30-12f40d2b310f
---
## Process: Survey Data to Executive Presentation

Developed during the State of Agentic AI in Marketing study (April 2026, n=69). This is the workflow Vas uses to go from raw survey exports to a CMO-ready interactive deck.

### Phase 1: Data Consolidation
1. Import SurveyMonkey xlsx exports (may have multiple collector panels)
2. Compare column headers across files using (question_stem, sub_label) key matching
3. Build a consolidated file: common columns only, Panel tag column added, two-row header preserved
4. Output: single xlsx with all respondents

### Phase 2: Findings by Question (Word doc)
1. For each question, produce a section: headline, source question text, stats
2. Single-choice: show distribution with labels (not numeric codes)
3. Multi-select: show counts per option, ranked
4. Matrix questions: render one sub-heading per row with level distribution
5. Open-ended: show verbatim responses
6. Include Internal vs External breakdown for each option
7. Output: Word doc organized by survey section (Screener, Maturity, Where AI Operates, Governance, Outlook, Classification)

### Phase 3: Top Findings (narrative)
1. Start with total-sample big contrasts only
2. For each finding: state it, show the data, explain why it matters for a CMO
3. Validate every number against the source file before presenting
4. Have CMO Reviewer and tech-decision-advisor agents pressure-test defensibility
5. Kill anything that doesn't survive scrutiny (e.g., the "14% runtime controls" framing was scrapped)

### Phase 4: Segmentation (Leaders vs Laggards)
1. Define groups using a cross-tab of two survey questions (e.g., journey stage x autonomy level)
2. Build a maturity matrix (3x3 in this case) with visual shading for each group
3. Run EVERY question by the two groups, not just the obvious ones
4. Use three indexing views:
   - V1: Within-group salience (top = 100)
   - V2: vs group average (group avg = 100)
   - Index C: group vs group (one group = 100 baseline)
5. Run predictive analysis: point-biserial correlations + odds ratios for each feature
6. Build composite score to show the "staircase" (e.g., 0 factors = 0% Leaders, 5 factors = 86%)
7. Group differentiators into 2-3 named factors (e.g., Commitment, Infrastructure, Measurement)

### Phase 5: Secondary Cuts
1. Identify a second segmentation axis (e.g., hands-on vs working knowledge)
2. Verify it's NOT a proxy for the first (check overlap %)
3. Run all questions with two-proportion z-tests
4. Only report findings at p < 0.10 or with >20pp gaps
5. Write a synthesis paragraph about what this cut adds that the primary cut doesn't

### Phase 6: Paradox / Prediction Analysis
1. Map each "future belief" question to a corresponding "current state" data point
2. Classify each pair: Consistent (belief matches reality), Contradicts (experience vs optimism), Paradox (belief directly contradicts the evidence), Unresolved (barrier with no belief about resolution)
3. Present as a two-panel juxtaposition, not a long table

### Phase 7: Interactive Presentation
1. Use reveal.js + Chart.js, single self-contained HTML file
2. Template per slide: strong headline, ONE visual (chart or table or stat), optional one callout, footnotes at bottom
3. All definitions and methodological notes go in footer, never in headlines or subheads
4. Design: light/airy (off-white bg), Inter font, blue accent, orange for secondary group, sans-serif only
5. Zero em-dashes in all prose
6. Charts: horizontal bars for ranking, line/waterfall for group comparisons, CSS tables for dense comparisons, stat-pair cards for small-n significance findings
7. Three-pillar layout for factor analysis (not tables)
8. Iterate with user: fix one thing at a time, don't rebuild entire slides when a label change will do

### Slide Design Rules (CMO-grade)
- Strong headline that states the finding, not describes the chart
- One visual per slide. Never two charts unless they're a direct comparison (now vs next)
- No pill rows, no multiple callout boxes, no "analyst 101" clutter
- Tables are clean: section headers, two data columns, one note column. Only rows with real gaps.
- Color: blue for Leaders/hands-on, orange/warm for Laggards/working-understanding. Red only for genuine warnings.
- Don't color-code judgments (e.g., red bars for "bad" guardrails) unless you've earned the argument
- Footnotes carry: sample sizes, group definitions, source questions, statistical methods
- Think HBR exhibit, not analyst dashboard

### Quality Gates
- Every number traced to a specific survey column
- CMO Reviewer agent for narrative defensibility
- tech-decision-advisor agent for logical/statistical defensibility
- Grep for em-dashes before every delivery
- Verify the chart actually renders (check JS console for errors, especially missing color constants)
