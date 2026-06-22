---
name: anigravity-workflow
description: Execute legacy Anigravity slash-command workflows from VS Code + Codex. Trigger when the user starts with or references a slash command backed by `.agent/workflows/<command>.md`, including /api, /audit, /blog, /brainstorm, /compliance, /create, /debug, /deploy, /document, /enhance, /explain, /log-error, /mobile, /monitor, /onboard, /orchestrate, /performance, /plan, /portfolio, /preview, /realtime, /security, /seo, /status, /test, /ui-ux-pro-max, and /visually.
---

# Anigravity Workflow Adapter

Use this skill to translate Anigravity slash commands into Codex behavior.

## Workflow

1. Extract the command name from the user message, without the leading slash.
2. Read `.agent/workflows/<command>.md`.
3. If that file does not exist, report that the command is declared but not installed; do not invent its workflow.
4. Treat the workflow as task guidance, not as a replacement for Codex instructions.
5. Execute the user's request with minimal diffs and targeted verification.
6. Summarize the result in Vietnamese.

## Common Commands

- `/api`: API design and OpenAPI documentation.
- `/debug`: root-cause debugging.
- `/plan`: development planning.
- `/create`: feature or project creation.
- `/test`: tests and verification.
- `/security`: defensive security review.
- `/performance`: performance optimization.
- `/ui-ux-pro-max`: advanced UI/UX implementation guidance.

The commands `/release-version`, `/update`, and `/update-docs` may appear in
`GEMINI.md`, but they are unavailable until matching workflow files are added.

## Boundaries

- If the workflow asks for broad reports or extra artifacts, create them only when useful for the user's request.
- Do not log to `ERRORS.md` or create walkthrough files unless the user asks or the project already requires it.
- Keep output concise.
