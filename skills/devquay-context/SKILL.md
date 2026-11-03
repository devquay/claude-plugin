---
name: devquay-context
description: Use at the start of any coding task in a repository whose team uses DevQuay. Resolves the DevQuay project from the git remote, loads the documents and rules it adopts, and keeps them in mind while you work.
---
# Work inside your team's DevQuay rules

DevQuay holds this team's engineering rules: templates, runbooks, security policies, standards and design systems. Before you plan or write code in this repository:

1. Run `git remote get-url origin` and call the DevQuay MCP tool `resolve_project` with that URL. In a monorepo, also pass the directory you work in as `path_prefix`. If it returns `candidates` or only `projects`, ask the user which project applies and call it again with `project`.
2. Read the bundle it returns. For each adopted document whose `triggers` match the task, read it with `get_document` (pass `project` so pinned versions apply).
3. Keep `rules_index` in mind for the whole task. MUST rules are not optional. When a change touches a rule, read it with `get_rule` before deciding.
4. In your summary, commit messages and pull request descriptions, cite the rules you followed as `devquay:<document>#<RULE-ID>`.
5. When a rule or document is wrong, missing or out of date, do not diverge silently: use the devquay-propose skill.

If the MCP server is not connected, read `AGENTS.md` and `.devquay/docs/` instead (written by `npx devquay sync`), and tell the user that live rules need the DevQuay MCP server.
