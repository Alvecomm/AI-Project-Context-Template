# Template Usage (IDE Guides)

This repository is designed to make AI-assisted development more reliable by storing project context in versioned files.

Core files (in the rules folder):
- `AI_RULES.md` (authoritative rules)
- `AI_CONTEXT.md` (short pinned context)
- `ARCHITECTURE.md` (structural truth)
- `TASKS.md` (task state)

Recommended: keep these files visible to your AI tool at all times.

## IDE-specific setup

- [Antigravity](./IDEs/Antigravity.md)
- [Cursor](./IDEs/Cursor.md)
- [VS Code](./IDEs/VSCode.md)
- [JetBrains](./IDEs/JetBrains.md)

## One-liner to start every AI session

Copy/paste this as the first message in a new AI chat:

> Read and strictly follow `AI_RULES.md`, `AI_CONTEXT.md`, and `ARCHITECTURE.md`.  
> Apply changes as unified diffs. If context is missing, ask before coding.
