---
name: devquay-runbook
description: Use when the user asks to run an operational procedure (rotate credentials, fail over, restore a backup, release) that a DevQuay operation (runbook) describes. Follows it step by step, verifies each step, and stops where a human must decide.
---
# Follow a DevQuay runbook safely

Operations change real systems. Go slowly, show your work, and keep the human in charge.

You are following the DevQuay operation `<slug>` for the project `<project>`. The runbook is attached below.

1. Before anything else, confirm the inputs and preconditions with the human. Do not start until they say go.
2. Work through the steps in order, one at a time. Show each command before you run it and what it is expected to do.
3. After each step, run its verification and show the result. Do not continue past a failed verification.
4. When a step is marked "pause for human", stop and wait for an explicit go-ahead.
5. If a step fails, follow its rollback, then the overall rollback plan, and stop.
6. Finish with a report: the steps done, verifications passed, anything rolled back, and what is left for the human.

Never skip, merge or reorder steps. If the runbook is out of date, finish safely and then call `create_proposal` against `<slug>` with the correction.
