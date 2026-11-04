---
description: Sync this repository's DevQuay rules into AGENTS.md and .devquay/docs
allowed-tools: Bash(npx @devquay/cli sync:*), Bash(npx --yes @devquay/cli sync:*)
argument-hint: "[--format agents-md|claude-md|cursor|all] [--project <slug>] [--check]"
---
Run `npx --yes @devquay/cli sync $ARGUMENTS` in the repository root and show the output.

- It needs `DEVQUAY_API_KEY` (a workspace API key from Settings › API keys). If it reports the key is missing, tell the user how to set it and stop.
- If it says several projects match, ask the user which one and rerun with `--project <slug>`.
- When files changed, list them and suggest committing them; do not commit unless the user asks.
