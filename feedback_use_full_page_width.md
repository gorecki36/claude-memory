---
name: use-full-page-width
description: "When placing an image/visual on a page that already has text content, default to a two-column layout that uses the full page width — never stack image-then-text in a single narrow column leaving the other half empty"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 1d6b436d-e369-4512-9932-b7397d79492c
---

When adding an image, photo, or visual to a page that has body content (bio, copy, etc.), the default layout is **two columns** that fill the page width:
- Text on one side at a comfortable reading width (max-w-md to max-w-2xl)
- Image on the other side, taking the remaining width as the visual anchor
- Match the site's wide container (`max-w-7xl` on vasteams.com)

NEVER stack image-above-text in a single narrow column on a wide page. NEVER leave the right half of a page empty when there's content that could fill it.

**Why:** Vas has corrected this repeatedly. The original /about page placed the new image at `max-w-2xl` above the bio, also `max-w-2xl`, in a `max-w-5xl` container. The right ~50% of the page was a black void. He told me: "I've told you a million times that you have to use the whole page, the whole page. Move the freaking image to the right; make it bigger." This is a recurring pattern, not a one-off.

**How to apply:**
- When the user asks to "add an image to [page]", check the page's existing content layout first
- If there's body text + a wide container, propose a two-column layout (text 4–5 cols, image 7–8 cols of a 12-col grid)
- If the image is portrait, image can be narrower (col-span-4 to 5)
- If the image is landscape, give it the bigger column (col-span-7 to 8)
- Image width on a real viewport should be visibly dominant — if my output looks like a thumbnail surrounded by emptiness, I did it wrong
- This applies to all pages: site pages, slide layouts, presentation visuals, briefs in HTML

Related: [[feedback_design_direction]] (light/airy, gradient cards, 18px+ body), [[reference_revealjs_centering]] (pin headers + center content).
