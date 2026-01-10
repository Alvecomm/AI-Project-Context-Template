# VS Code Setup

VS Code can work great with this template using AI extensions (Copilot Chat, RooCode, Continue, KiloCode, AugmentCode etc.).
The key is ensuring the assistant consistently sees the core context files.

## Recommended setup

### 1) Keep core files open
Open these in editor tabs at all times:
- `AI_RULES.md`
- `AI_CONTEXT.md`
- `ARCHITECTURE.md`
- `TASKS.md`

### 2) Configure your AI extension’s system prompt (if supported)
Most extensions have a “system prompt”, “custom instructions”, or “rules” setting.
Add:

> Follow `AI_RULES.md` as the highest authority. Use `AI_CONTEXT.md` and `ARCHITECTURE.md` as project truth. Prefer unified diffs. Ask before guessing missing context.

If your extension supports referencing files automatically, include:
- Always include `AI_RULES.md`, `AI_CONTEXT.md`, `ARCHITECTURE.md`, `TASKS.md` in context.

### 3) Start each chat with the one-liner
> Read and strictly follow `AI_RULES.md`, `AI_CONTEXT.md`, and `ARCHITECTURE.md`.  
> Apply changes as unified diffs. If context is missing, ask before coding.

## Best practices
- Use small, scoped prompts (“Update X in file Y”) rather than “refactor everything”
- Keep tasks in `TASKS.md` and work one at a time
- Summarize key outcomes into `DECISIONS.md`
