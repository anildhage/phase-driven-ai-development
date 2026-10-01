# Phase-Driven AI Development Starter Template

A lightweight starter for building products with an AI-assisted, phase-based workflow.

## What this repo helps with

- Turn a rough idea into small, testable milestones
- Keep work scoped to one phase at a time
- Require validation before moving forward
- Record completed work in `docs/completed/` for handoff and future context

## Start here

1. Read `GETTING-STARTED.md`
2. Update `docs/doc.md` with your project brief
3. Run the phase-generation prompt in `prompts/01-generate-phases-and-setup.md`
4. Build one generated phase at a time
5. Document the result in `docs/completed/` before continuing

## Key files

```text
.
├── GETTING-STARTED.md
├── README.md
├── development-in-phases.md
├── docs/
│   ├── doc.md
│   ├── phases/
│   └── completed/
├── prompts/
│   ├── 01-generate-phases-and-setup.md
│   └── 02-cleanup-template-for-project.md
├── .cursorrules
├── .clinerules
├── CLAUDE.md
├── .githooks/
│   └── pre-commit
├── .gitignore
├── CONTRIBUTING.md
├── LICENSE
```

## Phase completion rule

After a phase passes validation, create a matching summary in `docs/completed/`.

Before you begin the next phase or make a commit, confirm the previous phase is documented.

```bash
git config core.hooksPath .githooks
```

## Optional cleanup

If you want a cleaner project after cloning the template, use `prompts/02-cleanup-template-for-project.md`.

This cleanup is limited to optional template files, and it avoids removing the workflow essentials.

This repo is intentionally stack-agnostic and meant to be a clean starting point before real coding begins.
