---
name: reveal.js slide layout pitfalls
description: How to pin a header at fixed Y and vertically center content on every reveal.js slide without fighting its centering JS
type: reference
originSessionId: bb035281-4bc3-425c-b2da-bdeae2d0a3ef
---
Reveal.js with `center:true` sets `section.style.top = Math.max((slideHeight - section.scrollHeight)/2, 0)` via JS. Inline style beats stylesheet rules without `!important`, and `scrollHeight` does not reflect flex-centered children the way you expect — so `display:flex; justify-content:center` on the section looks applied in devtools but content still sits near the top.

Also: `.reveal .slides>section{display:none}` by default, `display:block` only on `.present`. Forcing `display:flex` on all matching sections (without scoping to `.present`) unhides every slide and they stack — looks like "slides were deleted."

**Working pattern** (iOpex deck, `~/Documents/mma-global/iopex/data/presentation/index-v2.html`):

```css
.reveal .slides > section:has(> .sec-label){
  min-height:720px !important;
  height:720px !important;
  padding:0 !important;
  top:0 !important;
  box-sizing:border-box;
}
.reveal .slides > section:has(> .sec-label) > .sec-label{
  position:absolute !important; top:60px !important; left:72px !important; right:72px !important;
  margin:0 !important; z-index:5;
}
.reveal .slides > section:has(> .sec-label) > .sl-title{
  position:absolute !important; top:98px !important; left:72px !important; right:72px !important;
  margin:0 !important; z-index:5;
}
.reveal .slides > section:has(> .sec-label) > .content-center,
.reveal .slides > section:has(> .sec-label) > svg{
  position:absolute !important;
  top:405px !important;  /* midpoint of below-header zone: 130→680 */
  left:72px !important; right:72px !important;
  transform:translateY(-50%) !important;
  margin:0 !important;
  max-width:calc(100% - 144px);
}
```

Key ideas:
- Lock section to exact 720×(slide width) with `top:0 !important` so reveal's JS can't shift it.
- Absolute-position the header at fixed Y so it doesn't depend on content size.
- Absolute-position the content block at a fixed midpoint Y with `translateY(-50%)` — deterministic, does not depend on flex or scrollHeight.
- Don't use `display:flex` on the section unless scoped to `.present` (and even then, it didn't reliably center in this deck).

**How to apply:** any reveal.js deck using `center:true` + a two-line header pattern (e.g. `.sec-label` slash + `.sl-title`). Adjust the `top:405px` midpoint if header/footer zones differ.
