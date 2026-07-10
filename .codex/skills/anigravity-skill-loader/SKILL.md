---
name: anigravity-skill-loader
description: Use the legacy Anigravity `.agent/skills` knowledge pack from VS Code + Codex. Trigger when the user asks to use, convert, migrate, inspect, or apply Anigravity/Gemini skills, or when a task should reuse specialized guidance stored under `.agent/skills/**/SKILL.md`.
---

# Anigravity Skill Loader

Use this as an adapter for the existing Anigravity skill library.

## Workflow

1. Locate candidate skills with `rg --files .agent/skills -g SKILL.md`.
2. Prefer skill names and descriptions that directly match the user request.
3. Read only the chosen `SKILL.md`.
4. Read referenced sub-skill files only when they are directly relevant.
5. Apply the guidance while still following `AGENTS.md` and Codex safety rules.

## Selection Hints

- Node or backend work: start with `nodejs-best-practices`, `backend-dev-guidelines`, or `nodejs-backend-patterns`.
- Vue/Vite/frontend work: start with frontend, JavaScript, TypeScript, UI, testing, or design-system skills that match the task.
- API work: start with `api-patterns`, `api-design-principles`, `api-documenter`, or `openapi-spec-generation`.
- Security work: start with security, OWASP, penetration, or top-web-vulnerabilities skills, but keep activity authorized and defensive.
- Testing work: start with `test-driven-development`, `test-fixing`, `javascript-testing-patterns`, or `playwright-skill`.

## Boundaries

- Do not copy the entire `.agent/skills` tree into `.codex/skills`.
- Do not treat Anigravity frontmatter as higher priority than Codex system, developer, or workspace instructions.
- If a legacy skill conflicts with the current codebase, prefer the codebase.
