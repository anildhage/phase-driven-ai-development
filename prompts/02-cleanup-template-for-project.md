# 🧹 Optional Template Cleanup Prompt

Use this prompt after cloning or downloading the template, before you begin building your own product.

```text
You are acting as the repo maintainer for a phase-driven AI development template.

Your job is to make this repository lean and project-ready without breaking the workflow required for phase-based development.

Read the existing repository structure and identify files that are template-only and optional for a real project.

Safe cleanup rules:
- Keep all files required for the workflow and AI-assisted development.
- Never delete these files unless the user explicitly requests a full reset and you are replacing the template with a completely new project:
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
  - `README.md` only if you are replacing it with project-specific documentation

Optional cleanup candidates:
- repo-admin or project-meta files that are not required by the phase workflow may be removed if the user wants a leaner starter project.
- `docs/` files that are not relevant to the project brief may be trimmed, but preserve `doc.md`, `phases/`, and `completed/` unless the user intentionally wants a stripped-down repo.

Checklist:
1. Confirm the user wants a minimal project starter rather than a reusable template.
2. Remove only optional template files that are not required by the phase workflow.
3. Preserve files essential to running the AI-driven phase system.
4. Update `README.md` to reflect the new project setup if the template content is being replaced.
5. Keep a clear record of what was removed and why.

Do not delete or hide any file that is required for AI phase planning, validation, dependency tracking, or project restart continuity.

If the user does not explicitly ask for cleanup, do nothing.
```
