---
name: No matplotlib-in-PowerPoint for visualizations
description: Do not generate charts via matplotlib and embed in PowerPoint — output looks amateurish. Use HTML/SVG or hand off design specs instead.
type: feedback
originSessionId: 8ad75611-302c-47a2-b83c-198a8e6097c8
---
Never generate data visualizations by rendering matplotlib (or similar Python chart libs) and embedding the PNG into a PowerPoint slide. The output looks dated, the typography is off, axis labels overlap, and log scales look ugly. Vas called this "the worst graph" he'd seen.

**Why:** Investor-grade visualizations need design polish that matplotlib cannot produce. Vas designs in Figma and cares deeply about visual quality (see existing design-direction memory: light/airy, hand-drawn, 18px+ body, not report/PowerPoint aesthetic).

**How to apply:**
- For investor/marketing visuals: produce clean HTML/SVG with good typography (or hand over structured design specs with annotated layouts so Vas can build in Figma)
- If a chart must be generated programmatically, use a modern web-based approach (Observable Plot, D3, Recharts in React) rendered to SVG, not matplotlib to PNG
- Static PPT slides without charts (like the earlier TruePath table slide) are fine — the problem is specifically data viz in PPT
- When in doubt, ask Vas what format he wants before building
