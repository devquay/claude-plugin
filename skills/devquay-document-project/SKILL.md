---
name: devquay-document-project
description: Use when the user asks to add this repository to DevQuay, to document the team's conventions, or to draft standards, security rules, templates or a design system from the code. Reads the repository locally, infers the conventions actually in use with evidence, and opens one DevQuay proposal per document for people to review.
---
# Document this project in DevQuay

You describe the conventions this repository already follows, so the team can review and adopt them. You never publish: every document is a proposal. DevQuay does not read the repository itself; you do, locally.

1. **Resolve the project.** Run `git remote get-url origin` and call `resolve_project`. If no project lists this repository, ask the user which project to use, or to create one in DevQuay first, and stop until they answer.
2. **Check what exists.** Read the bundle and `list_documents` so you extend existing documents (with `create_proposal` and `document`) instead of duplicating them, and `list_my_proposals` so you do not propose twice.
3. **Read the evidence.** Manifests and lockfiles (`package.json`, `go.mod`, `pyproject.toml`, `Cargo.toml`, `build.gradle*`), lint, format and type configs, CI workflows, Dockerfiles and infrastructure code, a handful of representative source files per area, and any design tokens, CSS variables or Tailwind config. Never read or quote `.env` files, keys, tokens or other secrets; if you see one, say so to the user and leave it out.
4. **Infer, with evidence.** For each convention, note the files that show it. Only write what the code consistently does; when the evidence is thin or contradictory, ask the user instead of guessing.
5. **Draft one document per subject**, in the shape of DevQuay's collections:
   - *Standards*: naming, structure, error handling, testing, logging, API style. Rules with ids (`STD-001`), MUST/SHOULD/MAY, a statement, rationale and how to verify.
   - *Security*: secrets handling, authentication, dependency and input rules actually enforced (`SEC-001`).
   - *Templates*: a recurring unit of work the code repeats (a service, an endpoint, a consumer), with inputs, the files it produces, steps and the checks to run.
   - *Design system*: tokens in DTCG form and the components in use, when the repository has a UI.
6. **Open the proposals.** For each document call `create_proposal` with `kind`, a clear `title`, `labels: ["adopt:<project>"]` so it is adopted by the project when merged, and a `description` that lists the evidence files. If validation fails, fix exactly the reported paths and call again.
7. **Report.** Give the user the list of proposals with their links and what each covers, and say what you left out and why. Reviewers decide what becomes the team's rules.
