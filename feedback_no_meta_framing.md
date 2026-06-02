---
name: feedback-no-meta-framing
description: "Never write meta-framing sentences OR section headers OR inline superiority claims. Strip rhetorical scaffolding; let the substance land directly. Broadened 2026-06-02 after repeat offense."
metadata:
  node_type: memory
  type: feedback
  originSessionId: 21fe3fa6-c4dd-439f-adf2-2a62f85a4c4e
---

Never use meta-framing in any form. Vas has flagged this MANY times. Rule is stricter than the general anti-AI-writing baseline. Broadened 2026-06-02 after I kept doing it even with the prior rule already in memory.

**Sentence-level patterns (banned):**
- "The sharper objection is [X]."
- "The deeper issue is [X]."
- "The bigger / real / more important point is [X]."
- "What's really going on here is [X]."
- "The harder question is [X]."
- "The interesting thing is [X]."

**Section-header patterns (banned — broadened after repeat offense 2026-06-02):**
- "The [X] most discussions miss."
- "What most people get wrong about [X]."
- "The truth about [X]."
- "Why most companies fail at [X]."
- "The [X] they don't tell you."
- "Things you didn't know about [X]."
- "Why this matters now." (predictive setup label that announces importance instead of demonstrating it)
- "The role that is coming." (mild meta — tighter to "The structural role" or just name the role)
- "Where this leads." (announces a destination instead of naming it — tighter to the actual destination)

**Inline superiority claims (banned):**
- "Most people don't realize [X]."
- "Few marketers understand [X]."
- "Implications most marketers haven't worked through."
- "[X] most teams miss."
- "What [X] gets wrong."

**Replace with:**
- Neutral descriptive headers: "The five variables," "What teams are doing today," "The structural role," "Action steps for Q3"
- Direct substantive claims, not setup labels: present the finding without announcing how clever it is

**Self-check before shipping ANY writing:** scan headers and sentence openings for the patterns above. If a header announces that what follows is interesting/contrarian/important, cut the announcement and let the substance carry the weight. Test: does this header ADD content, or does it just announce that what follows is content? If announce-only, rewrite.

**Why this keeps happening:** I default to these constructions because they feel like editorial confidence. They aren't. They're AI-writing scaffolding that announces what's coming instead of just delivering it.

**Caught on (2026-06-02):** Vas: "how can we make sure that you never ever ever ever ever do this again. I HATE THIS: The five variables most discussions miss." LinkedIn long-form article had three meta-framing headers (the variables one, "Why this matters now," "The role that is coming"). Same session also had "implications most marketers haven't worked through" pattern in the Melina blog. Pattern, not a one-off.

**Voice-rules paste-able prompt:** at `~/Documents/marketing-embeddings/voice-rules-prompt.md`. Vas can paste at the start of any writing session to enforce these rules independent of memory governance.

Related: [[feedback-quality-standards]], [[feedback-no-em-dashes]], [[feedback-plain-headlines]], [[feedback-narrative-grounding]], [[feedback-structural-fit-check]].
