# Getting Started

1. Download or clone this repo.
2. Open `docs/doc.md` and write your product brief, requirements, and constraints.
3. Read `development-in-phases.md` to understand the phase-based workflow.
4. Run the setup prompt in `prompts/01-generate-phases-and-setup.md`.
5. The AI creates phase files in `docs/phases/` for the next micro-win.
6. Work on only one phase at a time.
7. Validate the phase before moving on.
8. After a successful phase, create a completion record in `docs/completed/`.
9. Do not start the next phase until the previous one is documented and validated.
10. If you want extra discipline, enable the local Git safety check once:

```bash
git config core.hooksPath .githooks
```

This hook helps prevent moving to the next phase without recording the previous one. It is a small but powerful reminder to stay focused and avoid shallow, untracked work.

11. When you want a cleaner repo, use `prompts/02-cleanup-template-for-project.md` to remove optional template-only files.

## Recommended first run

```bash
# 1. Edit the brief
touch docs/doc.md

# 2. Read the workflow guide
test -f development-in-phases.md

# 3. Run the phase generator prompt in your AI tool
# Then begin with the first generated phase in docs/phases/
```

## Keep this workflow safe

- Preserve the AI workflow files: `.cursorrules`, `.clinerules`, `CLAUDE.md`, `development-in-phases.md`, `docs/doc.md`, `docs/phases/`, `docs/completed/`, `.gitignore`, `.githooks/`, and `prompts/`.
- Remove only optional template files when you explicitly want a leaner project starter and they are not required by the phase workflow.
