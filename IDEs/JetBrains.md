# JetBrains Setup (IntelliJ / PyCharm / WebStorm)

JetBrains IDEs have strong indexing and refactoring. Combined with this template, you get:
- structural code intelligence from the IDE
- durable context from repo files

## Recommended setup

### 1) Keep the core context files accessible
Pin/open:
- `AI_RULES.md`
- `AI_CONTEXT.md`
- `ARCHITECTURE.md`
- `TASKS.md`

### 2) If using JetBrains AI Assistant or a chat plugin
Set your “instructions” / system prompt (if available) to:

> Follow `AI_RULES.md` as the highest authority. Use `AI_CONTEXT.md` and `ARCHITECTURE.md` as project truth. Prefer unified diffs. Ask before guessing missing context.

### 3) Work task-by-task
- Track active work in `TASKS.md`
- Implement one task per session
- Use the IDE’s refactor tools for large structural changes
- Write major decisions into `DECISIONS.md`

## Best practices
- Let the IDE do heavy refactors; have AI propose changes as diffs
- Keep prompts specific and file-scoped
- Avoid mega-prompts; split work into smaller commits/tasks
