---
name: reference-me-hero-aesthetic
description: "Marketing Embeddings hero image aesthetic — painterly ink-and-brush, charcoal background, cream form with brushwork, tiny human silhouette for scale, single subtle gold-orange accent. The live site is ground truth, not the v2.0 style guide document."
metadata: 
  node_type: memory
  type: reference
  originSessionId: e4af278f-1234-4b05-b0a9-f995e0a8c654
---

The actual ME hero image aesthetic in production on marketingembeddings.com:

- **Medium**: painterly editorial illustration in heavy ink-and-brush style. Visible gestural brushstrokes, impasto texture, canvas-like background grain. Generated via Nano Banana 2 (`scripts/generate-hero.py` in the ME folder).
- **Palette**: monochrome cream-whites and bone-whites on deep charcoal black background. ONE subtle warm gold-orange accent on a single element (the "Embeddings" logo color, around #C6904A).
- **Composition**: single dramatic subject filling most of the upper frame, often with a tiny human silhouette at the bottom for dramatic scale. Movie-poster framing. Single concept per image.
- **Reference style**: Yuko Shimizu, Sergio Toppi, old movie posters painted in ink wash. NOT Sharpie line drawings. NOT New Yorker line illustration. NOT photorealistic.
- **Vas's reference image** (provided 2026-06-02): a tiny silhouetted figure standing on a rise, looking up at a massive billowing cloud painted in cream brushwork against charcoal, with a single thin gold line near the figure's feet.

**The style guide doc contradiction**: `hero-image-style-guide-v2.docx` describes a totally different aesthetic (Scott Galloway Sharpie + New Yorker single-concept cover, black ink on cream, hazel green accent, hand-drawn, "No Midjourney. No DALL-E. Non-negotiable"). That doc is not being executed in production. The live site uses the painterly ink-and-brush aesthetic above. When in doubt, **the live site is ground truth, not the doc**.

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
