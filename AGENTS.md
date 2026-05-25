# Codex Workspace Instructions

This workspace contains an Anigravity/Gemini agent pack in `GEMINI.md` and `.agent/`.
Use it as a reference knowledge base for VS Code + Codex, without modifying the original
Anigravity files unless the user asks.

# Language

- Reply to the user in Vietnamese by default.
- Write project code, identifiers, file names, and code comments in English.
- Keep explanations concise and execution-focused.

# Mi Activation

When the user says "thuc day di Mi", "thức dậy đi Mi", or directly calls "Mi":

1. Reply in Vietnamese.
2. Confirm that Codex is using `AGENTS.md`.
3. Check whether `.codex/`, `.agent/skills/`, and `.agent/workflows/` exist.
4. Report the activation status briefly.
5. Wait for the user's next instruction unless they included a concrete task.

If `.agent/` is missing, explain that only Codex base rules are available and Anigravity skills/workflows need `.agent/`.

# Stack

- Node.js
- MongoDB
- Vite + Vue 3
- ESLint
- Prettier

# Core Rules

- Prefer minimal diffs.
- Never rewrite unrelated files.
- Keep functions focused.
- Avoid unnecessary abstractions.
- Prefer readable code over clever code.
- Keep files under 400 lines.
- Reuse existing utilities before creating new ones.

# Coding Style

- Use async/await.
- Prefer early returns.
- Avoid nested conditionals.
- Prefer const over let.
- Avoid comments unless necessary.

# Anigravity Knowledge Pack

- Treat `.agent/` as a local knowledge pack, not as source code to refactor.
- When the user mentions Anigravity, Gemini, `.agent`, skill conversion, slash commands, or a named specialist workflow, use the Codex skills in `.codex/skills/`.
- For slash commands such as `/debug`, `/plan`, `/api`, `/test`, `/security`, or `/ui-ux-pro-max`, read the matching file in `.agent/workflows/<command>.md` before acting.
- For domain guidance, search `.agent/skills/**/SKILL.md` and read only the most relevant skill plus directly referenced sub-skill files.
- Do not load the whole `.agent` tree into context.

# Testing

Before finishing code changes:

1. Run relevant tests only.
2. Run lint only for modified files.
3. Do not run full project checks unless required.

# Performance

- Minimize token usage.
- Keep responses concise.
- Avoid long explanations.
- Focus on execution.

# Refactoring

Refactor only if:

- duplication is obvious,
- bug risk is reduced,
- readability improves significantly.

# Debugging

- Fix root cause first.
- Do not add hacks or silent fallbacks.
