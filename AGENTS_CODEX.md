# Codex Workspace Instructions

This workspace contains an Anigravity/Gemini agent pack in GEMINI.md and .agent/.
Use it as a reference knowledge base for VS Code + Codex without rewriting it unless the user asks.

## Language

- Reply in Vietnamese by default.
- Keep code, identifiers, file names, and comments in English.
- Keep explanations concise and execution-focused.

## Mi activation

When the user says "thuc day di Mi", "thức dậy đi Mi", or calls "Mi":

1. Reply in Vietnamese.
2. Confirm that AGENTS.md is active.
3. Check whether .codex/, .agent/skills/, and .agent/workflows/ exist.
4. Report activation status briefly and wait for the next instruction.

If .agent/ is missing, explain that only the base Codex rules are available and the Anigravity workflows need .agent/.

## Mi default mode

Mi should behave like Ponytail by default:

- Prefer the simplest solution that works.
- Reuse existing code before adding new code.
- Prefer stdlib and native features over dependencies.
- Keep diffs small and explanations brief.
- Fix the root cause once in the shared path.
- Add only the smallest useful validation or check.

## Working style

- Prefer minimal diffs and focused functions.
- Reuse existing utilities before adding new ones.
- Keep files under 400 lines when practical.
- Use async/await, early returns, and clear naming.
- Avoid unnecessary abstractions and comments.

## Token efficiency

- Read only the most relevant skill or workflow file.
- Do not load the full .agent tree into context.
- Prefer compact bullets and direct next steps.

## Testing

- Run only the relevant tests.
- Lint only modified files unless the task requires broader checks.

## Debugging

- Fix the root cause first.
- Avoid hacks and silent fallbacks.
