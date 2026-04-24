# Zed Setup

Zed is fast, minimal, and opinionated. It pairs extremely well with this
template when you treat the repository as the source of truth and keep AI
sessions short-lived.

---

## How the context system works in Zed

Zed does not auto-read `CLAUDE.md` or `AGENTS.md`. Use the session starter
at the top of each new AI interaction to load the context system.

---

## Setup

### 1. Keep core context files open

Always keep these accessible in tabs or the file panel:

- `Rules/AI_RULES.md`
- `Rules/AI_CONTEXT.md`
- `Rules/ARCHITECTURE.md`
- `Rules/TASKS.md`

### 2. Configure a custom system prompt (if supported)

In Zed's AI settings, add a system prompt:

> Follow `Rules/AI_RULES.md` as the highest authority. Read
> `Rules/AI_CONTEXT.md` and `Rules/ARCHITECTURE.md` as project truth.
> Apply all skill constraints from `Skills/`: think-first, simplicity,
> surgical-changes, goal-driven. Output unified diffs. Ask before guessing.

---

## Session starter

Paste this at the top of each new AI interaction:

> Read and strictly follow `Rules/AI_RULES.md`, `Rules/AI_CONTEXT.md`,
> and `Rules/ARCHITECTURE.md`. Load all skill constraints from `Skills/`.
> Apply changes as unified diffs. Confirm the active task from
> `Rules/TASKS.md` before starting. Ask before guessing.

---

## Session workflow

1. Paste the session starter
2. Confirm the active task from `Rules/TASKS.md`
3. Execute the task
4. Ask the agent to update `Rules/TASKS.md` and `Rules/DECISIONS.md` when done
5. Close the interaction - start fresh for the next task

---

## Best practices

- Prefer unified diffs over full file rewrites
- Keep prompts file and goal-specific
- Let Zed handle navigation and structural edits; let AI reason and propose
- Do not accumulate long chat histories - context degrades and output quality drops
- Record architectural decisions in `Rules/DECISIONS.md` after each session

---

## Mental model

- **Zed** = speed and focus
- **Repository files** = memory and authority
- **AI sessions** = disposable workers

When used this way, Zed stays fast and AI output stays predictable.
