<p align="center">
  <a href="https://alvecomm.com">
    <img src="./assets/brand/logo.svg" alt="Alvecomm logo" width="120">
  </a>
</p>

<h1 align="center">AI Project Context Template</h1>

<p align="center">
  <strong>
    A production-ready repository template for context-aware, AI-assisted software development.
  </strong>
</p>

<p align="center">
  <a href="https://github.com/sponsors/Alvecomm">Sponsor</a>
  ·
  <a href="https://alvecomm.com">Website</a>
  ·
  <a href="https://github.com/Alvecomm">GitHub</a>
</p>

---

## Why this exists

Modern AI models are powerful - but they are **stateless**.

They forget:
- architectural decisions
- conventions
- constraints
- context across sessions

This leads to:
- repeated explanations
- token waste
- accidental rewrites
- architectural drift
- frustration at scale

This template solves that by turning your **repository into the source of truth**, not the chat.

Framework-agnostic and compatible with Claude Code, Cursor, Windsurf, Opencode, Codex, Gemini CLI, VS Code, JetBrains IDEs, Zed, and any local or cloud AI model.

---

## What this template gives you

This repository provides a minimal but powerful structure that:

- Externalizes project context into versioned files
- Enforces consistent AI behavior across tools and models
- Reduces prompt size and repetition
- Improves reliability of AI-generated code
- Scales across teams, repos, and time

It works with:
- Agentic coding tools (Claude Code, Codex, Opencode, Gemini CLI)
- IDE-based assistants (Cursor, Windsurf, VS Code, JetBrains, Zed)
- Chat-based models
- Cloud or local LLMs
- Any language or framework

---

## Included files

| File | Purpose |
|-----|--------|
| `CLAUDE.md` | Claude Code entry point — auto-read at every session start |
| `AGENTS.md` | Universal agent entry point for all other tools |
| `Rules/AI_RULES.md` | Mandatory rules every AI assistant must follow |
| `Rules/AI_CONTEXT.md` | Short, always-relevant project context |
| `Rules/ARCHITECTURE.md` | Long-term structural and architectural truth |
| `Rules/TASKS.md` | Execution control and task state |
| `Rules/DECISIONS.md` | Record of important decisions (recommended) |
| `Skills/think-first.md` | Skill: reason before acting, surface ambiguity early |
| `Skills/simplicity.md` | Skill: write minimal, clean code — nothing speculative |
| `Skills/surgical-changes.md` | Skill: touch only what the task requires |
| `Skills/goal-driven.md` | Skill: define success criteria before executing |
| `LICENSE` | Open-source license (MIT) |

Together, these replace fragile chat memory with durable project memory.

---

## How to use this template

The repository itself becomes the **source of truth** for both humans and AI assistants.

---

### 1. Create a new project

- Click **Use this template** on GitHub  
  or  
- Clone the repository manually

---

### 2. Customize the core context files

Edit these early and keep them up to date:

- `Rules/AI_RULES.md` — defines how the AI must behave
- `Rules/AI_CONTEXT.md` — project overview, tech stack, invariants
- `Rules/ARCHITECTURE.md` — module boundaries, data flow, constraints

These files replace repeated explanations in chat.

---

### 3. Use it with your AI tools

**If you use Claude Code or opencode** — no setup needed.  
`CLAUDE.md` and `AGENTS.md` are read automatically at session start.
The agent will load your context files, confirm the active task, and apply
the coding skills without any manual instruction.

**All other tools** — at the start of every new AI-assisted session, instruct the model:

> Read and strictly follow `Rules/AI_RULES.md`, `Rules/AI_CONTEXT.md`, and `Rules/ARCHITECTURE.md`.  
> Apply all skills from the `Skills/` folder.  
> Apply changes as unified diffs. If context is missing, ask before coding.

Pin these files in your IDE if supported.

---

### 4. Work task-by-task

- Define one active task at a time in `TASKS.md`
- Complete the task in a focused session
- Close the task when done
- Start a fresh AI session for the next task

This keeps context tight, predictable, and cheap.

---

### 5. Separate planning from execution

**Planning**
- Use a strong reasoning model
- Produce plans, file lists, and decisions
- Write outcomes into `TASKS.md` or `ARCHITECTURE.md`

**Execution**
- Use faster or cheaper models
- Request diff-based changes only
- Let the repository provide context, not the chat

This separation dramatically improves output quality and reduces token limits.

---

### 6. Apply coding skills

The `Skills/` folder contains four focused constraint files that address
the most common AI coding failure modes:

| Skill | What it prevents |
|---|---|
| `think-first.md` | Silent wrong assumptions, hidden confusion |
| `simplicity.md` | Overengineering, bloated abstractions, unrequested features |
| `surgical-changes.md` | Scope creep, reformatting, drive-by refactoring |
| `goal-driven.md` | Vague execution, missing success criteria |

Agents are instructed to apply all four to every task via `CLAUDE.md`, `AGENTS.md`,
and `Rules/AI_RULES.md`. No extra setup required.

> The skills were inspired by: https://github.com/forrestchang/andrej-karpathy-skills - (Forrest Chang). Please check out his repository for more information.

---

### IDE-specific guides

Detailed setup instructions for popular editors are available here:

- [Antigravity](./IDEs/Antigravity.md)
- [Cursor](./IDEs/Cursor.md)
- [VS Code](./IDEs/VSCode.md)
- [JetBrains](./IDEs/JetBrains.md)
- [Zed](./IDEs/Zed.md)

The same principles apply to any IDE or AI tool that supports persistent context or custom instructions.

---

## Who this is for

This template is especially useful if you:

- Build non-trivial applications
- Rely heavily on AI-assisted coding
- Work across multiple projects
- Care about correctness and maintainability
- Want predictable AI behavior over time

Solo developers, consultants, and small teams benefit the most.

---

## Supporting the project

This project is free and open source.

If it saves you time, reduces frustration, or helps you ship better software,
consider supporting its ongoing development via GitHub Sponsors.

Even **$1/month** helps keep it maintained, improved, and available to everyone.

👉 https://github.com/sponsors/Alvecomm

---

## License

This project is licensed under the MIT License.
You are free to use, modify, and distribute it in personal or commercial projects.

---

## About Alvecomm

Alvecomm builds tools and systems at the intersection of
software engineering, automation, and AI-assisted workflows.

Learn more at https://alvecomm.com
