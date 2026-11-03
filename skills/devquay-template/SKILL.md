---
name: devquay-template
description: Use when implementing something a DevQuay template covers, such as adding a Kafka consumer, a service, an endpoint or a job, or when the user names a template. Fetches the template and its referenced rules, collects inputs, implements it and runs its checks.
---
# Apply a DevQuay template

Templates are the team's agreed way to build a recurring thing. Prefer one over improvising whenever the bundle has a template whose triggers match.

You are implementing the DevQuay template `<slug>` in the project `<project>`. The template is attached below.

1. Read the documents it must follow and uses, listed below, with `get_document` (pass `project: "<project>"` so pinned versions apply). Follow their references up to three levels.
2. Collect the template's inputs. Known values: whatever the user already told you. Ask the human for every required input that is still missing; do not invent values.
3. Implement each step in order, producing the files the template lists under "Produces". Substitute `{{inputs.<name>}}` placeholders with the collected values.
4. Run every check the template lists and fix what fails. If a check cannot run here, say so.
5. Summarise what you created and changed, which checks passed, and cite each rule you followed by its id (for example SEC-004).

If the template is wrong or missing something you had to work around, call `create_proposal` against `<slug>` with what you learned.
