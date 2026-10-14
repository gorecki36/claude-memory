---
name: reference-wispr-meeting-transcripts
description: "Mbriyo/BHI Google Meet transcripts live in local Wispr Flow files, not Gmail Gemini notes or Fireflies"
metadata:
  node_type: memory
  type: reference
  originSessionId: 4584e894-f771-450a-8f3c-0b82cbc9d312
  modified: 2026-10-14T13:48:29.833Z
---

When Vas asks for "Gemini transcripts" of Mbriyo/BHI calls, look in Wispr Flow first:
`~/Library/Application Support/Wispr Flow/meetings/<uuid>/refined.ndjson` (one JSON line per utterance: timestamp, text, speaker id; speakers unnamed, attribute from context). Find the meeting by folder mtime + grep for names (Korina, Thanos, Gustav).

**Why:** 2026-10-14, no Gemini notes email had ever reached vasbakos@gmail.com; Fireflies/Granola are tied to the MMA account and don't hold BHI calls. Vas pointed to Wispr.

**How to apply:** skip the Gmail/Drive/Fireflies hunt for Mbriyo meeting transcripts; go straight to Wispr. Related: [[reference_environment]].
