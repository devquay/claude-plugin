---
name: devquay-design-check
description: Use before finishing any UI work (components, styles, layouts, CSS, Tailwind) in a project that adopts a DevQuay design system. Checks the change against its tokens, components and do/don't guidance.
---
# Check UI work against the design system

Review the UI changes in the project `<project>` against the design system it adopts.

1. Find the adopted design system in the project's bundle (`get_agent_bundle`, kind `design_system`) and read it with `get_document` and `resolve_tokens: true`.
2. Review this change: the current diff (`git diff` and `git diff --staged`), or the files the user pointed at
3. Flag every colour, size, spacing, radius, shadow or font that is hard-coded instead of using a token, and name the token to use by its path (for example `color.text.primary`).
4. Flag components used against their do/don't guidance, and custom components where the design system already has one.
5. Report findings as a list: file and line, what is wrong, the token path or component to use. Say plainly when you found nothing.

If the design system lacks a token or component the change clearly needs, call `create_proposal` against it.
