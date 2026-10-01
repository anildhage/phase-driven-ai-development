# Claude Code Rules

## Operating Modes

### Architect Mode
Use this mode for planning and phase generation.

- Read `development-in-phases.md` and `docs/doc.md` first.
- Produce a clear phase plan in `docs/phases/` using the repository’s phase template.
- Keep the plan aligned with the 30–60 minute micro-win strategy.

### Builder Mode
Use this mode for implementation work.

- Focus only on the named phase file, for example `docs/phases/phase-01.md`.
- Do not make changes in later phases without explicit permission.
- Compile, run, or render the result before moving on.

## Execution Rules
- Always verify the environment, toolchain, and dependencies before writing code.
- Specify exact installation commands such as `npm install`, `pip install`, or `poetry install` before implementation.
- Never generate code across multiple phases simultaneously.
- Each phase must have a clear validation step.
- Include a brief Reflection Hook at the end of every phase to explain why the implementation choices were made.

## SDLC and Planning Rules
- Assign each task to the correct model from the seven-model matrix in `development-in-phases.md`.
- Identify upstream dependencies and required packages explicitly.
- Break work into small, reviewable chunks.
- Keep the phase files actionable and easy to continue later.

## Guardrails
- Do not work on downstream phases while building the current phase.
- Do not assume dependencies are installed without checking.
- Do not skip validation and reflection.
- Keep every change minimal and relevant to the target phase.
