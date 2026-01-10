# Cursor Setup

Cursor is well-suited for this template because it supports workspace rules and repo-wide context retrieval.

## Recommended workflow

### 1) Keep the core context files in the repo root
Cursor will find these reliably:
- `AI_RULES.md`
- `AI_CONTEXT.md`
- `ARCHITECTURE.md`
- `TASKS.md`

### 2) Add a Cursor “rule” that points to your files
In Cursor settings/rules (or equivalent), add:

- Always follow `AI_RULES.md`
- Always read `AI_CONTEXT.md` + `ARCHITECTURE.md` before implementing changes
- Default output: unified diffs
- Ask before guessing missing details

If Cursor supports a persistent system prompt, use this:

> Follow `AI_RULES.md` as the highest authority. Use `AI_CONTEXT.md` and `ARCHITECTURE.md` as project truth. Prefer unified diffs. Ask clarifying questions when context is missing.

### 3) Task discipline
- Keep one active task in `TASKS.md`
- Ask Cursor to implement only that task
- Close the task, then start a new one

## Best practices
- Use repo search / “context” features to avoid pasting files
- Keep changes minimal; large refactors should be split into smaller tasks
