---
name: Split long headlines into two rows
description: Always break slide headlines into two rows when they can fit on one line; use line breaks for readability
type: feedback
originSessionId: b2a3c9fc-a9c6-4f64-95ac-b656c298e651
---
Always split slide headlines into two rows if they can fit on one. Don't cram everything into a single long line.

**Why:** Vas flagged this during deck editing. Long single-line headlines feel cramped and are harder to scan. Two lines with a natural break point read better on slides.

**How to apply:** When writing slide headlines (sl-title class or similar), look for a natural sentence break and add a `<br/>` there. Prefer breaking after periods, commas, or logical pauses.
