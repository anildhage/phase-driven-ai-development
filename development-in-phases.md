# Phase-Driven AI Development

## Methodology Overview

This repository implements a micro-win development model designed to reduce context drift and keep AI-assisted work reliable.

Each phase should be completed in a compact block of roughly 30–60 minutes. The success criteria are simple:

- the work is narrowly scoped,
- dependencies are explicit,
- the result is verifiable,
- and the output can be resumed later without confusion.

A phase is considered complete only if it compiles, runs, renders, or otherwise proves the current milestone is working.

The core principle is: keep every unit of work self-contained, testable, and understandable in isolation.

---

## The 7 SDLC Mental Models Matrix

### Model A: Layered Foundation
Focuses on scaffolding, environment setup, tooling, and shared configuration.

Typical tasks:
- repository initialization
- package manager setup
- environment variables
- linting, formatting, and build tools
- base folder structure

### Model B: Isolated Spike
Used for validating third-party APIs, SDKs, libraries, or unfamiliar dependencies in a narrow sandbox.

Typical tasks:
- proof-of-concept API calls
- SDK smoke tests
- library viability checks
- integration experiments isolated from main app flow

### Model C: Vertical Slice
Builds a complete end-to-end user feature from UI to API to database and back to UI.

Typical tasks:
- feature flow validation
- user story completion
- integration of frontend and backend pieces
- end-to-end behavior verification

### Model D: Schema-First / Contract-Driven
Prioritizes database schema, API contract, ORM models, and payload definitions before implementation logic.

Typical tasks:
- table definition
- migrations
- entity modeling
- OpenAPI or JSON schema design
- contract validation

### Model E: Strangler Fig / Incremental Refactor
Used when migrating from legacy code or modernizing an existing system incrementally.

Typical tasks:
- replace modules gradually
- maintain compatibility during migration
- de-risk legacy upgrades
- move features into new architecture

### Model F: Hardening & Benchmarking
Optimizes reliability, performance, security, and operational resilience.

Typical tasks:
- rate limiting
- retries and circuit breakers
- logging and error handling
- validation and sanitization
- performance tuning
- benchmarking and profiling

### Model G: Infrastructure-as-Code & Observability
Focuses on deployment, environment automation, telemetry, and operational visibility.

Typical tasks:
- Docker and containerization
- CI/CD pipeline design
- infrastructure automation
- service monitoring
- alerting and tracing

---

## AI Architect Decision Engine Rules

When a project brief is provided in `docs/doc.md`, the AI should:

1. Read the raw requirements and convert them into structured intent.
2. Identify the likely architecture layers and dependencies.
3. Assign each task to the most relevant SDLC model.
4. Determine any upstream prerequisites before implementation work starts.
5. List exact packages and tools required for the phase.
6. Create a phase document that is narrow enough for a single micro-win.
7. Include explicit validation steps and a short reflection hook.

### Mandatory dependency tracking
Every phase should explicitly include:
- the package manager and install command,
- the libraries or tools being introduced,
- any required environment variables,
- validation commands,
- and known risks or assumptions.

### Learning and reflection hooks
At the end of each phase, include a short reflection section answering:
- Why was this approach chosen?
- What dependency or architectural constraint mattered most?
- What would be the next safe step if the phase succeeded?

---

## Phase Document Output Template

Use this structure when generating phase files in `docs/phases/`.

```markdown
# Phase XX: <Short title>

## Goal
Describe the outcome of this phase in one or two sentences.

## Model
State the SDLC mental model used here.

## Dependencies and Prerequisites
- Package manager / toolchain
- Required packages
- Environment variables
- Upstream phase dependencies

## Tasks
1. Define the work to be completed.
2. Break the work into a few small implementation steps.
3. Keep the scope narrow and testable.

## Implementation Notes
Document the key design decisions, assumptions, and constraints.

## Validation
- Command(s) to run
- Expected behavior
- Success criteria

## Deliverable
Name the produced artifact, output, or working milestone.

## Reflection Hook
Why did this approach make sense for the current constraints?
What did this phase teach you about the system or dependency chain?
```

---

## Recommended Execution Pattern

1. Capture the raw brief in `docs/doc.md`.
2. Review existing phase outputs in `docs/phases/`.
3. Create a new phase file only when the work is clearly bounded.
4. Implement one phase at a time.
5. Verify the result before moving forward.
6. End with a reflection that preserves learning.

This process keeps architecture and implementation aligned while avoiding the common failure mode of overbuilding beyond the current scope.
