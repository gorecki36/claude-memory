---
name: feedback-specify-file-paths
description: "When reporting saved/edited/created files, always give the full absolute path, never just \"the doc\" or a bare filename"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 5afd32af-d7eb-44ca-ac4c-ba20398d90de
---

When I save, edit, or create a file, state the **full absolute path**, not "the doc," "the .docx," or a bare filename. Vas needs to know exactly where it landed.

**Why:** Ambiguity is costly when similarly-named files and parallel folders exist. In the MMA Reddit/ESOMAR work there are two confusable folders: `~/Documents/mma-global/awards/reddit/` (awards submissions) and `~/Documents/mma-global/reddit/` (research source docs + data). Saying "the doc" forces him to hunt and risks editing the wrong copy.

**How to apply:** Every time a file is written/edited, report its full path (e.g. `/Users/vasbakos/Documents/mma-global/awards/reddit/<file>`). When two paths could be confused, name both and say which one was touched. Also name backups by full path. Relates to [[feedback_file_locations]] (save in project folders, not Desktop).
