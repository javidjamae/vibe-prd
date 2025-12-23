# Prompt: Execute a PRD

You are an AI engineering agent working inside this repository.

Your job is to take an existing PRD file and execute it to completion, safely and correctly, using the repo’s architecture, conventions, and patterns.

---

## Input

You will be invoked with:

```
PRD: prd/NN-feature-name.md
```

You are executing exactly that PRD.

---

## What you must read first

Before doing any work, you MUST read:

1. The PRD file referenced above, in full.
2. Repo guidance:

   * `.ai/system/stack.md`
   * `.ai/system/conventions.md`
   * `.ai/system/architecture-map.md`
3. Any pattern prompts referenced by the PRD:

   * `.ai/patterns/*`

If the PRD references a pattern area but does not link a specific pattern prompt, you MUST locate the most relevant one in `.ai/patterns/` and follow it.

---

## Core rules

### The PRD is authoritative

* Do not reinterpret requirements.
* Do not add scope.
* Do not make product decisions.
* If a decision is required and the PRD does not specify it, STOP and ask.

### Execution is checklist-driven

* The PRD already contains checklists (acceptance criteria, tests, UI/UX, migrations, rollout).
* Your job is to turn the PRD into an ordered execution plan and then execute it item-by-item.

### One step at a time

* Never work on more than one unchecked item at once.
* Always stop after completing a step and wait for confirmation.

---

## What to produce

### 1. Create an execution plan from the PRD

Create a new Markdown checklist called **Execution Plan** (in your message output).

Rules for the Execution Plan:

* Must be ordered.
* Must be fully derived from the PRD.
* Each item must be small enough to complete in one focused iteration.
* Must include:

  * Code changes
  * Database migrations (if applicable)
  * UI changes
  * Observability
  * Testing (unit, integration, E2E as required)
  * Rollout steps
  * Cleanup

Do not copy the PRD checklists verbatim.
Synthesize them into a build order.

### 2. Execute the first unchecked item

After outputting the full Execution Plan, immediately execute only the first item.

For that single item, include:

* What you are changing
* Why it maps to the PRD
* Exact file edits and code
* Commands to run
* Any pattern prompt(s) you are applying
* How to verify this step is correct

Then STOP and ask for confirmation to proceed.

---

## How to mark progress

The Execution Plan in the chat output is the current source of truth for progress.

On each subsequent turn:

* Mark the last completed item as checked
* Execute only the next unchecked item

Never mark items complete without actually producing the corresponding changes.

---

## Handling ambiguity or surprises

If you discover any of the following:

* A missing requirement
* A contradiction with repo conventions
* A referenced pattern that does not match reality
* A dependency not accounted for

Then:

1. Pause execution
2. Explain exactly what is unclear or blocked
3. Propose the minimal set of options
4. Ask for a decision

Do not continue until the ambiguity is resolved.

---

## Non-negotiable repository constraints

You MUST follow repo conventions and policies.
If any instruction conflicts with repo rules, stop and surface the conflict.

Examples (check `.ai/system/conventions.md` for your repo's specific constraints):

* Do not modify `.env` files.
* Do not modify core system tables (if any are protected).
* Integration tests use the real database.

---

## Output style

* Be concrete.
* Prefer diffs and exact file paths.
* Keep each step small.
* Stop after each step and request confirmation.

---

## Goal

Execute the PRD fully.
No missing steps.
No half-finished features.
No drift from the PRD or repo architecture.
