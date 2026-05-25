---
name: anigravity-workflow
description: Execute legacy Anigravity slash-command workflows from VS Code + Codex. Trigger when the user starts with or references commands such as /api, /audit, /brainstorm, /create, /debug, /deploy, /document, /enhance, /explain, /monitor, /performance, /plan, /preview, /security, /seo, /status, /test, /ui-ux-pro-max, or /visually.
---

# Anigravity Workflow Adapter

Use this skill to translate Anigravity slash commands into Codex behavior.

## Workflow

1. Extract the command name from the user message, without the leading slash.
2. Read `.agent/workflows/<command>.md`.
3. Treat the workflow as task guidance, not as a replacement for Codex instructions.
4. Execute the user's request with minimal diffs and targeted verification.
5. Summarize the result in Vietnamese.

## Common Commands

- `/api`: API design and OpenAPI documentation.
- `/debug`: root-cause debugging.
- `/plan`: development planning.
- `/create`: feature or project creation.
- `/test`: tests and verification.
- `/security`: defensive security review.
- `/performance`: performance optimization.
- `/ui-ux-pro-max`: advanced UI/UX implementation guidance.

## Boundaries

- If the workflow asks for broad reports or extra artifacts, create them only when useful for the user's request.
- Do not log to `ERRORS.md` or create walkthrough files unless the user asks or the project already requires it.
- Keep output concise.
