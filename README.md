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
├── .githooks/
│   └── pre-commit
├── docs/
│   ├── doc.md
│   ├── completed/
│   │   └── phase-completion-template.md
│   └── phases/
│       └── .gitkeep
```

## How to use it

1. Open `docs/doc.md` and paste the raw project brief, user stories, architecture notes, or design ideas.
2. Read `development-in-phases.md` to understand the decision engine and the seven SDLC mental models.
3. Ask your AI assistant to generate or refine phase files in `docs/phases/`.
4. Work one phase at a time.
5. Validate each phase before moving to the next.
6. When a phase passes validation, document it in `docs/completed/` before the next phase or a git commit.

## Phase completion tracking

The repository now enforces a handoff checkpoint for each phase:

- Completed work should be captured in `docs/completed/<phase-name>.md`.
- The completion record must explain what was built, what was validated, and what the next step is.
- Before moving to the next phase, verify the previous phase is documented and archived.
- Before committing, check that the current phase has a matching completion summary.

To enable the git safety check:

```bash
git config core.hooksPath .githooks
```

## Quick start

For the shortest path, start with `GETTING-STARTED.md`.

## Optional cleanup for a lean project start

If a user wants a cleaner project template after downloading this repo, they can run the optional cleanup prompt in `prompts/02-cleanup-template-for-project.md`.

This cleanup is intentionally limited to template-only files and should never remove the workflow essentials:

- `.cursorrules`
- `.clinerules`
- `CLAUDE.md`
- `development-in-phases.md`
- `docs/doc.md`
- `docs/phases/`
- `docs/completed/`
- `.gitignore`
- `.githooks/`
- `prompts/`

The usual candidate files for removal are only optional repo metadata such as `CONTRIBUTING.md` and `LICENSE`, and only when the user wants a more minimal starter experience or a new project license.

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
