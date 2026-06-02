---
name: reference-me-hero-aesthetic
description: "Marketing Embeddings hero image aesthetic — painterly ink-and-brush, charcoal background, cream form with brushwork, tiny human silhouette for scale, single subtle gold-orange accent. The live site is ground truth, not the v2.0 style guide document."
metadata: 
  node_type: memory
  type: reference
  originSessionId: e4af278f-1234-4b05-b0a9-f995e0a8c654
---

Marketing Embeddings uses TWO distinct hero aesthetics depending on the content layer:

**Aesthetic 1 — Painterly ink-and-brush (Big Picture / lead pieces)**
- Heavy gestural brushwork, impasto texture, canvas-like background grain
- Cream-whites and bone-whites painted forms on deep charcoal black background
- Single subtle warm gold-orange accent (~#C6904A, matching the "Embeddings" logo)
- Single dramatic subject filling most of the upper frame, with a tiny human silhouette at the bottom for dramatic scale (~2-3% of image height)
- Movie-poster framing
- Reference style: Yuko Shimizu, Sergio Toppi, old movie posters painted in ink wash
- Reference image provided by Vas 2026-06-02: tiny figure on a rise looking up at a massive billowing cloud, single thin gold line near the feet
- Working examples: `2026-04-27-gauge.json`, `2026-05-18-dissolving-walls.json`, `2026-06-02-looming-bills.json`

**Aesthetic 2 — Sharpie hand-drawn (Policy Corner / sidebar pieces)**
- Bold black Sharpie marker line drawing on clean cream paper (#F2EDE3)
- Single rust-orange terracotta accent (~#A04830) on one element only
- Multi-stroke slightly imperfect outline, visible felt-tip texture, hand-drawn quality
- Single object, generous white space (25%+ margin), New Yorker single-concept cover composition
- No painterly textures, no shadows, no gradients
- Reference image provided by Vas 2026-06-02: magnifying glass with rust-orange concentric rings inside the disc, black Sharpie outline on cream
- Reference style: Scott Galloway's No Mercy / No Malice + New Yorker single-concept covers
- This aesthetic matches `hero-image-style-guide-v2.docx`. Style guide and live site DO NOT conflict; they describe different image layers.

**Important: pick the aesthetic to match the content layer:**
- Big Picture / lead essay → Aesthetic 1 (painterly)
- Policy Corner / sidebar / shorter pieces → Aesthetic 2 (Sharpie)

**How to apply for new heroes:**
- Start prompts with "Painterly editorial illustration in heavy ink-and-brush style with visible gestural brushwork."
- Always specify deep charcoal background, cream/bone-white forms with shadow greys for depth.
- Always include "small human silhouette for scale" at the bottom of the frame, no more than 2-3% of image height, if the concept supports it.
- Single subtle warm gold-orange accent (#C6904A) on one element only.
- Reference Yuko Shimizu or Sergio Toppi or movie-poster ink wash in the prompt.
- Negative-prompt against: photorealistic, smooth digital art, sharp clean lines, sharpie line art, cartoon, neon, sci-fi, gradient backgrounds, multiple accent colors.
- Single concept, single subject. No multi-element compositions.

**Prior hero JSONs that match this aesthetic** (use as templates):
- `2026-04-27-gauge.json`
- `2026-05-18-dissolving-walls.json`
- `2026-05-12-open-lock.json`
- `2026-06-02-looming-bills.json` (cost piece)
- `2026-06-02-raised-gavel.json` (tax piece)

**Off-brand prior attempts** (don't use as templates):
- `2026-06-02-shrinking-coin.json` / `2026-06-02-coin-magnifier.json` — too multi-element, too object-focused, no human scale
- `2026-06-02-shrinking-coin-v2.json` / `2026-06-02-coin-magnifier-v2.json` — Sharpie-style overcorrection following the doc instead of the live site
