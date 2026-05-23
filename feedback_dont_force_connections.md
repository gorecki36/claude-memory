---
name: feedback-dont-force-connections
description: "When synthesizing multiple sources or news items, don't force a narrative arc that glosses over which layer of the system each source describes. Shared topic (\"AI in 2026\", \"marketing\") is not a structural connection."
metadata: 
  node_type: memory
  type: feedback
  originSessionId: e4af278f-1234-4b05-b0a9-f995e0a8c654
---

When asked to find a "story arc" or synthesize across multiple research items, news stories, or data sources, **do not force connections at all costs**. Before proposing a unified narrative, check whether the sources actually describe the same layer of the system. If they only share a topic ("AI", "marketing", "trust"), that's an umbrella, not a structural connection. Surface that explicitly when offering an arc, and offer to split into separate pieces if the connection is thin.

**Why:** 2026-05-23. Vas asked if there was a story arc connecting the Sinch "AI Production Paradox" report (n=2,527 enterprise customer-comms AI deployments, 74% rollback rate) with seven news links covering Google Marketing Live, ChatGPT ads, LiveRamp into Publicis, Canva-Gemini, LinkedIn slop crackdown, Google AI Overviews killing publisher traffic, and Starbucks pulling its AI inventory tool. I built a "closing of the marketing stack" arc: open infrastructure consolidating into closed AI platforms, with broken production inside. Vas asked me to simplify in 3-4 lines, then immediately caught the overreach: the Sinch data is about **enterprise customer-comms agents** (Bank X's WhatsApp bot failing), while the news links are about **ad/marketing infrastructure consolidation** (Google search, ChatGPT placements, identity layers). They're different layers of the stack. Saying "broken production inside the consolidating platforms" implied a causal connection the Sinch data doesn't support. Starbucks rollback was a third category (internal operational AI), so it didn't bridge them either.

**How to apply:**
- Before proposing a narrative connecting N sources, ask: are they at the same layer of the system? Do failure modes / causal mechanisms actually connect, or do they just share a topic?
- "Both involve AI" / "both involve marketing" / "both involve trust" is an umbrella, not a connection. State this explicitly when offering.
- When the connection is thin, propose splitting into separate pieces rather than forcing one. Give Vas the choice. He prefers two clean pieces over one stretched piece.
- The two-essay or three-essay option is often the right call. For the Sinch + news links example, the right move was: governance theater piece using Sinch alone, consolidation piece using the news links, no forced arc.
- Related: [[feedback_verify_claims]], [[feedback_narrative_grounding]], [[feedback_disclose_incomplete_review]]. The pattern is the same — don't let framing run ahead of evidence.
