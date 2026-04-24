# VS Code Setup

VS Code works well with this template using AI extensions such as GitHub
Copilot Chat, Continue, RooCode, KiloCode, AugmentCode, and others.
The key is ensuring the assistant consistently sees the core context files.

---

## How the context system works in VS Code

VS Code extensions do not auto-read `CLAUDE.md` or `AGENTS.md`. Configure
your extension's system prompt once, then use the session starter at the
top of each new chat.

---

## Setup

### 1. Keep core files open

Keep these in editor tabs at all times:

- `Rules/AI_RULES.md`
- `Rules/AI_CONTEXT.md`
- `Rules/ARCHITECTURE.md`
- `Rules/TASKS.md`

### 2. Configure your extension's system prompt

Most extensions have a "system prompt", "custom instructions", or "rules"
setting. Set it to:

> Follow `Rules/AI_RULES.md` as the highest authority. Read
> `Rules/AI_CONTEXT.md` and `Rules/ARCHITECTURE.md` as project truth.
> Apply all skill constraints from `Skills/`: think-first, simplicity,
> surgical-changes, goal-driven. Output unified diffs. Ask before guessing.

If your extension supports automatic file inclusion, add:

> Always include `Rules/AI_RULES.md`, `Rules/AI_CONTEXT.md`,
> `Rules/ARCHITECTURE.md`, and `Rules/TASKS.md` in context.

### 3. GitHub Copilot users

Add a `.github/copilot-instructions.md` file to your repo with this content:

```
Follow Rules/AI_RULES.md as the highest authority.
Read Rules/AI_CONTEXT.md and Rules/ARCHITECTURE.md before every task.
Apply constraints from Skills/: think-first, simplicity, surgical-changes, goal-driven.
Output unified diffs. Ask before guessing. Confirm active task from Rules/TASKS.md.
```

Copilot reads this file automatically across your workspace.

---

## Session starter

Paste this at the top of each new chat if your extension does not support
a persistent system prompt:

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
6. Close the chat - start fresh for the next task

---

## Best practices

- Use small, scoped prompts ("fix X in file Y") rather than broad requests
- Keep one active task in `Rules/TASKS.md` and work through it fully
- If the assistant starts drifting or ignoring rules, start a new chat
- Record key decisions in `Rules/DECISIONS.md` after each session
