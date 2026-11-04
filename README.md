# DevQuay for Claude Code

Your team's DevQuay engineering rules in Claude Code: templates, runbooks, security policies, standards and design systems over MCP, with skills that apply them and propose fixes.

## Install

```
/plugin marketplace add devquay/claude-plugin
/plugin install devquay@devquay
```

The plugin connects Claude Code to the DevQuay MCP server at `https://mcp.devquay.com/mcp`. Sign in when Claude Code asks (OAuth). For CI or headless use, add an API key instead:

```
claude mcp add --transport http devquay https://mcp.devquay.com/mcp --header "Authorization: Bearer $DEVQUAY_API_KEY"
```

If you belong to several workspaces, use `https://mcp.devquay.com/mcp?workspace=<slug>`.

## What it adds

| Skill | When Claude uses it |
|---|---|
| `devquay-context` | At the start of a task: resolves the project from the git remote, loads its documents and rules. |
| `devquay-template` | When building something a team template covers. |
| `devquay-runbook` | When running an operational procedure, step by step, with you in charge. |
| `devquay-design-check` | Before finishing UI work, against the adopted design system. |
| `devquay-propose` | When a rule is wrong or missing: opens a proposal for review. Agents never publish. |
| `devquay-document-project` | When asked to add this repository to DevQuay: drafts its conventions as proposals, with evidence. |

`/devquay-sync` runs `npx @devquay/cli sync` to refresh `AGENTS.md` and `.devquay/docs/`.

Version 0.1.0. Generated from the DevQuay monorepo.
