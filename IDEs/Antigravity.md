# Antigravity Setup

Antigravity works best when you treat your repository as durable memory and
each chat as a disposable worker. One task per session, fresh context every time.

---

## How the context system works in Antigravity

Antigravity does not auto-read `CLAUDE.md` or `AGENTS.md`. Use the session
starter below to load the context system at the start of every new chat.

---

## Setup

### 1. Pin the core context files

Keep these visible or pinned in your workspace at all times:

- `Rules/AI_RULES.md`
- `Rules/AI_CONTEXT.md`
- `Rules/ARCHITECTURE.md`
- `Rules/TASKS.md`

Only add task-specific files when directly relevant to the current session.

### 2. Reference the Skills folder

At the start of each session, make the `Skills/` folder available so the
agent can apply coding constraints. You do not need to paste the files -
just reference them by path and instruct the agent to read them.

---

## Session starter

Paste this at the top of every new chat:

> Read and strictly follow `Rules/AI_RULES.md`, `Rules/AI_CONTEXT.md`,
> and `Rules/ARCHITECTURE.md`. Load all skill constraints from `Skills/`:
> think-first, simplicity, surgical-changes, goal-driven.
> Apply changes as unified diffs. If context is missing, ask before coding.
> Confirm the active task from `Rules/TASKS.md` before starting.

---

## Session workflow

1. Paste the session starter above
2. Agent confirms the active task from `Rules/TASKS.md`
3. Execute the task
4. Agent updates `Rules/TASKS.md` on completion
5. Log any architectural decision in `Rules/DECISIONS.md`
6. Close the chat - start a new one for the next task

---

## Best practices

- Use unified diffs - smaller, safer, fewer tokens
- Do not paste entire files unless the agent specifically needs them
- Keep sessions short and task-focused - context degrades over long chats
- If the agent starts guessing or drifting, stop immediately and provide
  the missing context file rather than letting it continue
- After major changes, update `Rules/AI_CONTEXT.md` or `Rules/ARCHITECTURE.md`
  so the next session starts with accurate context
