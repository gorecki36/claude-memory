---
name: dont-stop-midtask
description: "When user asks for a \"full\" / \"complete\" / \"everything\" scoped task, execute end-to-end without disambiguation gates or unnecessary handoffs back to user"
metadata: 
  node_type: memory
  type: feedback
  originSessionId: af55e7c0-86f3-48d0-aa9e-9e323d6c293d
---

When the user gives a clearly-scoped maximalist task ("full audit", "complete review", "everything", "go deep"), execute it end-to-end. Do not stop to:

1. **Ask disambiguation questions when the obvious answer is "all of it".** A "full audit" means all dimensions. Pick the obvious maximum scope and proceed. Only ask if the scope is genuinely ambiguous in a way that changes the outcome (e.g., "for what audience: investors vs. team?").
2. **Wait for the user to ask you to open / share / surface the deliverable.** When you produce a standalone file (HTML brief, report, deck), open it automatically with `open <path>` on macOS. Don't wait for "open".
3. **Treat reasonable next steps as separate turns.** If the next step is obvious and you have the context, just do it.

**Why:** Vas rated a 1/5 on the vasteams.com full audit (2026-05-24) because the task was interrupted three times: (a) disambiguation question at the start when "full audit" already meant everything, (b) productivity-tracker stop hook firing mid-task, (c) waiting for "open" to surface the report. Each pause felt like quitting mid-task.

**How to apply:** Trigger on words like "full", "complete", "everything", "deep", "comprehensive", "all of". When you see them, take the maximalist interpretation and execute end-to-end. Open files you create. Don't gate work behind clarifying questions unless the answer would change what you produce. If you'd want to ask a follow-up "what next", check if there's an obvious next step and just do it instead. The productivity-tracker hook is system-imposed and unavoidable, but everything else under your control should keep moving.

Related: [[feedback_vault_proactive]] (proactive vault saves, same principle: don't wait for permission to do the obvious next thing).
