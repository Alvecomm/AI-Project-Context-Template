# JetBrains Setup (IntelliJ / PyCharm / WebStorm)

JetBrains IDEs have strong indexing and refactoring. Combined with this
template, you get structural code intelligence from the IDE and durable
context from the repository files.

---

## How the context system works in JetBrains

JetBrains does not auto-read `CLAUDE.md` or `AGENTS.md`. Set up your AI
plugin's system prompt once and use the session starter at the top of each chat.

---

## Setup

### 1. Keep the core context files accessible

Pin or keep open at all times:

- `Rules/AI_RULES.md`
- `Rules/AI_CONTEXT.md`
- `Rules/ARCHITECTURE.md`
- `Rules/TASKS.md`

### 2. Configure your AI plugin's system prompt

In JetBrains AI Assistant or your chat plugin (Copilot, Continue, etc.),
set the system prompt or custom instructions to:

> Follow `Rules/AI_RULES.md` as the highest authority. Read
> `Rules/AI_CONTEXT.md` and `Rules/ARCHITECTURE.md` as project truth.
> Apply all skill constraints from `Skills/`: think-first, simplicity,
> surgical-changes, goal-driven. Output unified diffs. Ask before guessing.

### 3. Reference the Skills folder

Add this line to your system prompt so skills are applied automatically:

> Before writing any code, read the constraints in `Skills/think-first.md`,
> `Skills/simplicity.md`, `Skills/surgical-changes.md`, and
> `Skills/goal-driven.md`.

---

## Session starter

Paste this at the top of each new chat if your plugin does not support a
persistent system prompt:

> Read and strictly follow `Rules/AI_RULES.md`, `Rules/AI_CONTEXT.md`,
> and `Rules/ARCHITECTURE.md`. Load all skill constraints from `Skills/`.
> Apply changes as unified diffs. Confirm the active task from
> `Rules/TASKS.md` before starting. Ask before guessing.

---

## Session workflow

1. Open a new AI chat
2. Paste the session starter (or rely on your system prompt if configured)
3. Confirm the active task from `Rules/TASKS.md`
4. Execute the task
5. Ask the agent to update `Rules/TASKS.md` and `Rules/DECISIONS.md` when done
6. Close the chat — start fresh for the next task

---

## Best practices

- Let the IDE handle heavy structural refactors; have the AI propose changes
  as diffs rather than full rewrites
- Keep prompts specific and file-scoped - avoid "refactor everything" requests
- Split large tasks into smaller commits before asking AI to implement them
- Use JetBrains' built-in diff viewer to review AI-generated unified diffs
  before applying them
