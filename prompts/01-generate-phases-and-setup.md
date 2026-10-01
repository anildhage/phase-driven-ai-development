# 🚀 Master Phase Generator & Repository Setup Prompt

> **Instructions for the developer:** 
> 1. Paste your raw project ideas, specifications, or requirements into `docs/doc.md`.
> 2. Copy the entire prompt block below and paste it into your AI assistant (Cursor, Claude Code, Cline, etc.).
> 3. Let the AI generate your development roadmap and transform this repository into your application's home!

---

### Copy & Paste This Prompt into Your AI Assistant:

```text
You are acting as the Lead Systems Architect. Perform the following setup, cleanup, and phase generation process based on this project repository:

---------------------------------------------------------------
STEP 0: OPTIONAL TEMPLATE CLEANUP
---------------------------------------------------------------
If the user wants a minimal project-ready repository instead of a reusable template, perform a safe cleanup before building the project.

Allowed cleanup actions:
- Remove optional repo-admin or project-meta files only if the user explicitly wants a leaner starter project.
- Keep all files required for the phase-driven workflow and project continuity.
- Never delete the following files unless the user explicitly wants a full reset and is replacing the template with a completely new app:
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
  - `README.md` if it is being rewritten for the new app

If the user does not ask for cleanup, do not remove anything.

---------------------------------------------------------------
STEP 1: ANALYZE REQUIREMENTS & ARCHITECTURE
---------------------------------------------------------------
1. Read `docs/doc.md` to understand the full application goals, technical stack, and target features.
2. Read `development-in-phases.md` to review the 7 SDLC Mental Models:
   - Model A: Layered Foundation (Scaffolding / Environment)
   - Model B: Isolated Spike (3rd-Party SDKs / Unfamiliar APIs)
   - Model C: Vertical Slice (User-facing feature flows)
   - Model D: Schema-First / Contract-Driven (Database / ORM / API schemas)
   - Model E: Strangler Fig / Incremental Refactor (Refactoring / Migrations)
   - Model F: Hardening & Benchmarking (Performance / Security / Errors)
   - Model G: Infra-as-Code & Observability (CI/CD / Docker / Hosting)

---------------------------------------------------------------
STEP 2: GENERATE INDIVIDUAL PHASE DOCUMENTS
---------------------------------------------------------------
Break down the requirements in `docs/doc.md` into sequential, 30-to-60-minute micro-win phases inside `docs/phases/`.

For EVERY phase created (e.g., `docs/phases/phase-01-setup.md`, `docs/phases/phase-02-db-schema.md`), ensure the document contains:
1. Phase Goal & Applied SDLC Mental Model (with rationale for why that model was chosen).
2. Upstream Dependencies & Prerequisites (what phase/config must exist first).
3. Tech Development Stack & Packages (exact `npm install` or `pip install` commands needed).
4. Step-by-Step Implementation Checklist (bite-sized, sequential tasks).
5. Local Verification & Commands (terminal commands or actions to confirm the phase works).
6. Reflection & Learning Hook (a brief explanation of key technical choices made).

---------------------------------------------------------------
STEP 3: CAPTURE COMPLETED PHASE OUTPUTS
---------------------------------------------------------------
For every phase that is completed and validated, create a matching completion summary file in `docs/completed/`.

Each completion summary should be named after the phase, such as:
- `docs/completed/phase-01-setup.md`
- `docs/completed/phase-02-db-schema.md`

Each completion file must include:
1. Phase name and completion date
2. Goal and outcome of the phase
3. SDLC model used and why it was chosen
4. Files changed or created
5. Commands executed and validation result
6. Risks, assumptions, and remaining blockers
7. The next recommended phase or milestone
8. A brief reflection hook summarizing the learning

Important rules:
- Do not start the next phase until the previous phase is documented in `docs/completed/`.
- Do not commit code to a remote repository without a matching phase completion summary.
- If the completion record is missing, stop and create it before proceeding.

---------------------------------------------------------------
STEP 4: REWRITE ROOT README.MD FOR THE NEW APPLICATION
---------------------------------------------------------------
Now that all phase files are created in `docs/phases/`, OVERWRITE the root `README.md` file so it becomes the official documentation for the application defined in `docs/doc.md`.

Remove all previous template/setup rules from `README.md` and replace them with:
1. Application Name & Overview (derived from `docs/doc.md`).
2. Tech Stack & Environment Setup instructions.
3. How to Run & Test the Application locally.
4. Project Development Roadmap (listing the phase files created in `docs/phases/` and how to execute them step-by-step).
5. A note that completed work should be archived in `docs/completed/` before moving to the next phase.
6. A note about optional cleanup of non-essential template files if the user wants a leaner repo.

Keep the execution engines intact (`development-in-phases.md`, `.cursorrules`, `.clinerules`, `CLAUDE.md`, and `docs/phases/`).

Confirm when all phase files are generated in `docs/phases/`, completion summaries are added to `docs/completed/`, any optional cleanup is complete, and `README.md` has been successfully updated!