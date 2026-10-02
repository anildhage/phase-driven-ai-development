---
name: begin-next-phase
description: Use when the user asks to begin, start, continue, or move to the next project phase. Checks completed phase documents in docs/phases/, resolves unfinished work, and prepares the next phase.
---

# Begin Next Phase

## When to use

Use this skill when the user asks to:
- Start the next phase
- Continue the project
- Move to the next milestone
- Check whether the current phase is complete

## Required location

Find and read all files in:

```text
docs/phases/
```

Each file represents a project phase. Determine completion status from the file contents.

## Steps

1. List all files in `docs/phases/`.
2. Read each phase file in chronological or numbered order.
3. Identify phases marked complete, incomplete, blocked, or awaiting review.
4. If an earlier phase is incomplete, summarize the missing work and ask whether to resolve it before proceeding.
5. If all earlier phases are complete, identify the next phase.
6. Read any requirements, dependencies, tools, files, or setup steps needed for the next phase.
7. Propose a short plan before making changes.
8. After approval, begin the next phase and update the relevant phase document as work progresses.

## Rules

- Never skip an incomplete earlier phase without explicit user approval.
- Do not assume a phase is complete based only on its filename.
- If `docs/phases/` does not exist, ask the user where phase documents are stored.
- Keep phase status clear: `Completed`, `In Progress`, `Blocked`, or `Not Started`.