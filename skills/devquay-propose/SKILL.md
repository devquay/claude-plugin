---
name: devquay-propose
description: Use when a DevQuay document or rule turns out to be wrong, missing, outdated or impossible to follow, or when you learned something the team's rules should say. Opens a proposal for people to review instead of diverging silently.
---
# Propose a change to the rules

You cannot publish to DevQuay; you propose, and people review. That is the right move whenever the rules and reality disagree.

Turn this learning into a proposal to the DevQuay document `<slug>`: what you learned while working

1. Read the current document with `get_document` (format `json`) so you change only what needs changing.
2. Check `list_my_proposals` for an open proposal that already covers this; update it with `update_proposal` instead of opening another.
3. Write a short title that says what changes, and a description that says why: what happened, where (files, incidents, reviews), and what the change prevents.
4. Put only the changed parts in `content`: the body section, the rule, the step or the field. Keep ids of existing rules and steps.
5. Call `create_proposal`. If it returns validation errors, fix exactly those paths and call again.
6. Give the human the proposal number and link. People review it; you cannot publish.
