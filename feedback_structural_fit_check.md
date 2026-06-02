---
name: feedback-structural-fit-check
description: "When the user asks me to add an item to a section, verify the item structurally fits the section before adding. If it doesn't, flag the mismatch before making the change. Never publish half-accurate framings."
metadata: 
  node_type: memory
  type: feedback
  originSessionId: e4af278f-1234-4b05-b0a9-f995e0a8c654
---

When the user asks to add an item (a source, a person, an example, a data point) to a specific section of a deliverable, check whether the item structurally fits the section's category before making the change. If the item is related but uses a different mechanism, fits a different layer, or has a different scope, flag the mismatch and propose an alternate location before editing.

Never publish "half-accurate" framings to bridge the gap. If a claim isn't 100% true as stated, it doesn't go in. We only report things we are 100% sure of.

**Why:** 2026-06-02. Caught in Melina's AI Token Tax blog. Vas asked me to add Senator Elizabeth Warren to the "Who's proposing it" section. I verified her proposal (per-kWh data center energy excise + AI billionaire wealth tax) but added her to the token-tax cluster anyway, then bridged the gap with a half-accurate summary line ("Warren's mechanism is notably not a per-token tax: she would tax the energy infrastructure under AI, not the AI output") that ignored the wealth-tax half of her proposal. Vas: "if Warren's is not a token tax then you shouldn't lead with that. You can include it in the end if you want, as other discussions around taxing AI." And: "you can't add something that is half accurate above. Stick to the rules. We only report things that we are 100% sure."

Same miss applied to Dario Amodei in the same piece (his is a 3% revenue tax, not a token tax) — I should have caught that too without being asked.

**How to apply:**
- When user asks to add X to section Y, run a fit check first: does X belong in Y's category, or in a related-but-different category?
- If X doesn't fit Y's structural definition, flag the mismatch before adding. Propose: "X belongs in a separate section because it uses mechanism A while section Y is about mechanism B. Want me to add a related-debate / further-reading section?"
- Don't bridge a structural mismatch with "this is also related" or "interesting contrast" framings. Either it fits or it doesn't.
- Re-audit adjacent items in the same section. If I'm flagging X for not fitting, items already in the section might also not fit — check them all.
- Related: [[feedback_verify_claims]], [[feedback_preserve_scope]], [[feedback_dont_force_connections]]. The pattern is: don't let framing run ahead of mechanism. A category isn't an umbrella for vaguely-related items; it's a specific structural claim.
