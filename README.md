# Phase-Driven AI Development Starter Template

This repository is a universal starter template for AI-assisted product development using a strict phase-based workflow.

It helps turn a raw idea or project brief into a sequence of small, testable, and reviewable milestones. The goal is to reduce context drift, make dependency tracking explicit, and keep each unit of work narrow enough to finish in a single session.

## Why this template exists

- Encourages 30–60 minute micro-wins
- Keeps work scoped to one phase at a time
- Forces dependency verification before coding
- Uses a seven-model SDLC framework to choose the right architecture strategy
- Adds reflection hooks so learning is retained across phases

## Repository structure

```text
.
├── .cursorrules
├── .clinerules
├── CLAUDE.md
├── development-in-phases.md
├── .gitignore
├── README.md
├── docs/
│   ├── doc.md
│   └── phases/
│       └── .gitkeep
```

## How to use it

1. Open `docs/doc.md` and paste the raw project brief, user stories, architecture notes, or design ideas.
2. Read `development-in-phases.md` to understand the decision engine and the seven SDLC mental models.
3. Ask your AI assistant to generate or refine phase files in `docs/phases/`.
4. Work one phase at a time.
5. Validate each phase before moving to the next.

## AI workflow rules

This repository defines different operational rules for different tools:

- ` .cursorrules ` for Cursor
- `.clinerules` for Cline / Roo Code / VS Code AI
- `CLAUDE.md` for Claude Code / Claude CLI

Each of these files tells the AI to:

- read `development-in-phases.md` and `docs/doc.md` when planning,
- focus only on the active phase during implementation,
- verify dependencies first,
- state exact install commands before writing code,
- and finish each phase with a short Reflection Hook.

## Quick start

```bash
# 1. Edit the project brief
# Fill in docs/doc.md

# 2. Generate the first phase
# Create docs/phases/phase-01.md

# 3. Validate the phase
# Run the commands required by the implementation and confirm the result
```

## Recommended development pattern

- Start with a foundation or dependency spike if the stack is unclear.
- Move to a vertical slice for core functionality.
- Use schema-first design when persistence or API contracts matter.
- Add hardening work only after the feature works.
- Use infrastructure and observability work when deployment is part of the goal.

## Notes

This template is intentionally stack-agnostic. It is designed to support frontend, backend, full-stack, data, mobile, automation, or AI-driven product work without locking you into a specific framework.
