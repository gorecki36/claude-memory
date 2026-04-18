---
name: Research to executive presentation process
description: Transferable workflow for analyzing survey data, structuring CMO-grade presentations, writing headlines, and designing slides. Applies to any MMA or research project.
type: reference
originSessionId: 10b3b38f-882b-4ec5-8b30-12f40d2b310f
---
## How We Analyze the Data

### Start broad, then segment
1. Run every question at total sample first. Only surface big contrasts.
2. Define a primary segmentation (e.g., Leaders vs Laggards) using a cross-tab of two questions. The definition should be intuitive and defensible.
3. Run EVERY question by the two groups. Don't cherry-pick. The biggest gaps are often in questions you didn't expect.
4. Use three indexing views: within-group (top = 100), vs group average (100 = baseline), group-vs-group (one group = 100).
5. Run a secondary segmentation on a different axis (e.g., knowledge level). Verify it's not a proxy for the first (check overlap %).

### Quantify what separates
6. Run odds ratios and correlations for each potential differentiator against group membership.
7. Group differentiators into 2-3 named factors. Name them as insights, not categories ("They fund it like they mean it" not "Commitment").
8. Build a composite score to show the staircase (e.g., 0 of 5 factors = 0% Leaders, 5 of 5 = 86%).

### Test for paradoxes
9. Map each "future belief" question to a "current state" data point.
10. Classify each pair: consistent with data, contradicted by experience, or a paradox (belief contradicts evidence).
11. Check for blind spots: barriers with no corresponding prediction about resolution.

### Defensibility gates
12. Validate every number against the source column before presenting.
13. Use CMO Reviewer agent for narrative defensibility.
14. Use tech-decision-advisor agent for statistical/logical defensibility.
15. If a stat doesn't differentiate between groups, kill the slide. Don't present non-findings.
16. Verbatims must match their category. A quote about processes belongs under "people," not "data."

## How We Structure the Presentation

### Narrative arc
1. **Setup:** 2-3 provocative questions the audience is already wondering. Tee up, don't reveal. These should be pre-existing anxieties, not previews of findings.
2. **State of play:** Where the market actually is (maturity model, data visualization).
3. **Where it's heading:** Current application vs future ambition.
4. **What breaks down:** Barriers, with voices from respondents.
5. **What separates leaders:** The named factors, visualized.
6. **What the market believes vs what the data shows:** Predictions vs reality.
7. **The personal lens:** Why individual proximity/knowledge matters.
8. **Key takeaways:** 3 distilled insights, peer language.
9. **Closing questions:** Action-oriented, tied back to the setup.

### Setup questions connect to closing questions
The opening questions should map to the closing action items. The audience should feel the arc close.

## How We Write Headlines

### Headlines state the insight, not describe the chart
- Bad: "Where belief matches reality, and where it doesn't."
- Good: "Challenged by talent and governance, hopeful about data and creative."

### Don't reveal findings in setup questions
- Bad: "If every team uses AI, why does almost no one let it act?"
- Good: "How far along is agentic AI deployment in the enterprise, really?"

### Use peer language, not lecturer language
- Bad: "Learn the CFO's language."
- Good: "They measure what the board cares about."

### Frame as ongoing, not past
- Bad: "They funded it like they meant it."
- Good: "They fund it like they mean it."

### Test the claim before committing
- If a headline says "the gap is commitment, not technology" but the data shows infrastructure has the highest odds ratio, the headline is wrong. Fix it.
- If a scenario sounds smart but doesn't reflect how the workflow actually works (e.g., "AI detects a conversion drop at 9 PM"), kill it.

### When stuck on a headline, try:
1. State the tension, not the conclusion.
2. Ask "what would a CMO repeat to their team on Monday?"
3. Try the question form first, then convert to a statement.
4. If it sounds like a press release, rewrite it.

## How We Design Slides

### Layout rules
- Headlines always in the same position, pinned to top of every slide.
- Content vertically centered in remaining space below headline (use flex wrapper).
- One visual per slide. Maximum.
- Use the full space. Maximum 15-20% empty. Scale up text, charts, and cards.
- Footer at bottom: source/methodology text left, logo right.

### What never appears on slides
- Rounded pill/chip labels (no pastel background shapes for section labels).
- Em-dashes. Zero tolerance.
- Definitions or methodology in headlines or subheads. Those go in footers.
- Multiple callout boxes or pill rows.
- Color-coded judgments without earning the argument first.

### MMA brand specifics
- Colors: gold (#E8A838) and black (#0f172a) only. No blue.
- Section labels: gold skewed slash bar + bold text.
- Font: system font stack (-apple-system, BlinkMacSystemFont, Segoe UI, Roboto).
- Cards: 12px border-radius, subtle shadow, gold left-bar accent.
- Numbered items: gold numbers, vertical left border connecting items.
- Footer logo via CSS pseudo-element (no manual placement per slide).

### Chart rules
- Horizontal bars for ranking data. Black for primary, gold for secondary.
- Line/waterfall for group comparisons. Black for Leaders, gold for Laggards.
- Stacked bars with animation for "now vs next" comparisons. Keep axis fixed.
- SVG for custom diagrams (axes, radial layouts). Not HTML divs.
- Always sort by rank unless there's a reason not to.
- All bars same color unless there's a reason to differentiate.

### Visual hierarchy
- When showing barriers/factors, the visual size should reflect the relative importance.
- Descending rows: top row gets the most space, bottom row the least.
- Highlight the most important item with gold background or gold left-border ribbon.
- Use icons (SVG, gold stroke) to add visual identity to categories. Never emojis.

### Space and sizing
- If reveal.js center:true pushes headlines to middle, use center:false with flex content-center wrapper.
- Charts: minimum 300-400px height. Never make them tiny.
- Text in cards/tables: minimum 0.85rem for body, 1rem+ for titles.
- If more than 20% of the slide is empty, something needs to be bigger.
