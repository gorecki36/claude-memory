---
name: SVG draw order matters
description: When building SVG charts, always draw reference lines BEFORE data lines. Got stuck 5 times on this — zero line rendered on top of the green revenue line.
type: feedback
originSessionId: 8ad75611-302c-47a2-b83c-198a8e6097c8
---
In SVG, elements drawn later render on top. When building charts:
1. Draw backgrounds/zones first
2. Draw grid lines and reference lines (like $0 line)
3. Draw filled areas
4. Draw data curve strokes LAST so they always appear on top

**Why:** Spent 5 iterations failing to fix a zero-line-on-top-of-green-line issue because I kept changing line thickness and opacity instead of fixing draw order. Vas was rightfully frustrated.

**How to apply:** Any time building SVG/HTML charts, explicitly comment and enforce the draw order. Test visually at points where data lines intersect reference lines.
