# Antigravity Setup

Antigravity works best when you treat your repository as durable memory and each chat as a disposable worker.

## Recommended workflow

### 1) Pin the source-of-truth files
Pin these in your workspace (or keep them open in tabs):

- `AI_RULES.md`
- `AI_CONTEXT.md`
- `ARCHITECTURE.md`
- `TASKS.md`

Only pin additional files that are directly relevant to the current task.

### 2) Start every new chat with a one-liner
Paste this at the top of each new session:

> Read and strictly follow `AI_RULES.md`, `AI_CONTEXT.md`, and `ARCHITECTURE.md`.  
> Apply changes as unified diffs. If context is missing, ask before coding.

### 3) Work task-by-task (avoid long chats)
- Add or update a single task in `TASKS.md`
- Complete the task in one session
- Summarize outcomes into `DECISIONS.md` if needed
- Start a new chat for the next task

## Best practices
- Prefer unified diffs (smaller, safer, less token usage)
- Don’t paste entire files unless requested
- If the assistant starts guessing, stop and provide the missing context file
