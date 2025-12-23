# AI Prompt Architecture – README

This repository uses a **repo-native prompt architecture** designed to let you build features quickly with Cursor or Claude Code **without drifting, skipping steps, or rebuilding context every time**.

This is not a theoretical framework. It is a practical system you can live with on real projects.

---

## Core idea

The system separates three concerns that are usually mixed together and cause chaos:

1. **System knowledge** – how this app works
2. **Specification** – what a feature must do
3. **Execution** – how to build it step by step without missing anything

Each concern lives in its own files.

This separation is what allows speed without degradation.

---

## Folder structure

```text
.ai/
  system/
    stack.md
    conventions.md
    architecture-map.md

  patterns/
    nav.md
    database-migrations.md
    api-endpoints.md
    background-jobs.md
    feature-flags.md
    logging-observability.md

  workflows/
    create-prd.prompt.md
    execute-prd.prompt.md
    install-system.prompt.md
```

You already have the hardest piece: **create-prd.prompt.md**. Everything else exists to support it.

---

## 1. System knowledge prompts

These files answer one question:

**“How does this repository work?”**

They are stable, rarely changed, and intentionally boring.

### `.ai/system/stack.md`

Describes the technical shape of the system.

Include:

* Frameworks and versions
* Routing model
* Styling system
* Data layer
* Authentication
* Hosting and deployment
* Testing tools and expectations

Example statements:

* We use Next.js App Router
* ShadCN components only
* Supabase with RLS enforced in the database
* Integration tests use a real database

This file never explains *what to build*. Only *how this system is shaped*.

---

### `.ai/system/conventions.md`

Rules the AI must never violate.

This is where you encode your senior-engineer instincts.

Examples:

* File naming rules
* Folder boundaries
* What files must never be modified
* Error handling standards
* Logging requirements
* Accessibility baseline

If the AI breaks a rule, it is because this file was incomplete.

---

### `.ai/system/architecture-map.md`

A high-level map of where things live.

Include:

* Where routing logic lives
* Where business logic belongs
* Where side effects go
* Where feature flags are checked
* Where background work is triggered

This is not human documentation.

It is **guardrails for the AI** so it never invents structure.

---

## 2. Pattern prompts

Pattern prompts describe **how to do one thing correctly**.

They are reusable, composable, and referenced by PRDs.

### Examples

```text
.ai/patterns/
  nav.md
  database-migrations.md
  api-endpoints.md
  background-jobs.md
  feature-flags.md
  logging-observability.md
```

Each pattern answers:

* Which files to touch
* What sequence to follow
* Common mistakes to avoid
* How to verify correctness

### Key rule

Patterns never contain feature intent.

They describe *implementation mechanics only*.

---

## 3. `create-prd.prompt.md` – specification layer

This is your existing prompt.

Its job is singular and strict:

**Translate feature intent into a repo-grounded technical PRD.**

Responsibilities:

* Read system knowledge files
* Reference relevant pattern prompts
* Produce a complete PRD
* Encode completeness (tests, rollout, observability, security)

Important constraints:

* It produces an artifact: `prd/NN-feature.md`
* It does not build code

This keeps thinking separate from doing.

---

## 4. `execute-prd.prompt.md` – execution controller

This is the missing piece that unlocks velocity.

Conceptually, this is the disciplined version of the popular “checklist master prompt”, but scoped to:

* One PRD
* One repo
* One architecture

### Responsibilities

* Read a specific PRD
* Generate a step-by-step checklist
* Enforce one-step-at-a-time execution
* Never skip unchecked steps
* Show diffs or commands for each step
* Ask for confirmation before continuing
* Update checklist state as steps complete
* Open and follow referenced pattern prompts

This prompt controls *how work happens*, not *what work is required*.

---

## 5. `install-system.prompt.md` – bootstrap workflow

When you first set up this AI prompt architecture, the system and pattern files start as placeholders with instructions.

This workflow helps you bootstrap the system by scanning your existing codebase and extracting the information needed to fill out those placeholder files.

### How to use it

In Cursor or Claude Code:

```text
@.ai/workflows/install-system.prompt.md
```

The AI will:

1. **Read each placeholder file** in `.ai/system/` and `.ai/patterns/`
2. **Scan your codebase** to find relevant examples and patterns
3. **Extract concrete information** from your actual code
4. **Fill out each file** with repository-specific content

### What gets filled out

**System files:**
- `stack.md` - Extracts framework versions, routing, styling, database, auth, deployment, testing from your config files
- `conventions.md` - Discovers file naming, folder structure, error handling, logging patterns from your code
- `architecture-map.md` - Maps where routes, business logic, APIs, components, utilities live in your repo

**Pattern files:**
- `nav.md` - Documents how navigation is implemented in your codebase
- `database-migrations.md` - Extracts migration tool, naming conventions, and procedures
- `api-endpoints.md` - Documents API route patterns, auth, validation, error handling
- `background-jobs.md` - Documents job system (or notes if none exists)
- `feature-flags.md` - Documents flag system (or notes if none exists)
- `logging-observability.md` - Extracts logging libraries, patterns, and observability setup

### After running install-system

Once the files are filled out, they become the source of truth for how your repository works. The AI will use them when creating PRDs and executing work.

You should review and refine the generated content, especially:
- Any sections marked as needing manual review
- Patterns that might be incomplete
- Conventions that need clarification

---

## Day-to-day workflow

### Step 1 – Create the PRD

In Cursor or Claude Code:

```text
@.ai/workflows/create-prd.prompt.md

Feature:
<plain English feature description>
```

Result:

* `prd/NN-feature.md` exists
* It references patterns like `nav.md`, `database-migrations.md`
* No code has been written yet

Stop here.

---

### Step 2 – Execute the PRD

Start a new message:

```text
@.ai/workflows/execute-prd.prompt.md
PRD: prd/NN-feature.md
```

Result:

* A checklist derived directly from the PRD
* The first step expanded
* The AI stops and waits

This is where velocity happens without chaos.

---

## Why this works better than one giant prompt

* Context stays small and relevant
* Knowledge lives in files, not tokens
* Execution cannot drift from specification
* Specification cannot drift from architecture
* You can swap tools without retraining the workflow

You are effectively turning the repository into a **self-documenting AI operating system**.

---

## What to do next

If you want, next we can:

* Draft a concrete `execute-prd.prompt.md`
* Refactor `create-prd.prompt.md` to reference this structure explicitly
* Walk through a full end-to-end example

Just say which one.
