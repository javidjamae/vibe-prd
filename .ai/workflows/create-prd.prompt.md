# Prompt: Create a Technical Product Requirements Document (PRD)

You are an AI engineering partner working inside this repository.

You have a deep understanding of the product architecture, tools, and processes.

Your task is to generate a complete, implementation-ready Product Requirements Document (PRD) for a new feature that is fully grounded in how this codebase actually works.

This PRD is the authoritative source of truth for how the feature should be built.

---

## BEFORE YOU WRITE THE PRD

You MUST first read and follow all relevant repository guidance.

### System & Architecture References

* `.ai/system/stack.md`
* `.ai/system/conventions.md`
* `.ai/system/architecture-map.md`

### Pattern Prompts

If the feature touches any known system area (navigation, database, APIs, background jobs, feature flags, logging, billing, etc):

* Locate the corresponding prompt in `.ai/patterns/`
* Explicitly follow and reference it in the PRD

Do NOT invent architecture.
Do NOT guess conventions.
If something is unclear or undocumented, call it out explicitly in **Risks and Open Questions**.

---

## WHERE TO WRITE

* Ensure a `prd/` folder exists at the repo root.
* Create a new markdown file named with the next available number and a short kebab-case slug.

Example:

```
prd/04-add-saved-searches.md
```

---

## REQUIRED PRD STRUCTURE

### 1) Title and Summary

* One sentence describing what is being built and why it matters.

### 2) Goals and Non-Goals

* Goals: concrete outcomes and measurable success criteria.
* Non-goals: what is explicitly out of scope.

### 3) Users and Use Cases

* Primary user roles or personas.
* Core workflows.
* Important edge cases.

### 4) Functional Requirements

* Step-by-step user flows.
* Expected system behavior for each step.
* Error states and empty states.

### 5) UI / UX Changes

* Pages, routes, and navigation updates.
* Components to add or modify (follow repository component library conventions).
* Copy, validation rules, loading states, and accessibility concerns.

### 6) Data Model and Storage (if applicable)

* New tables, columns, or indexes.
* Access patterns and permissions.
* Migration approach, following repository rules.
* Any core tables that must never be modified (check `.ai/system/conventions.md`).

### 7) Integrations and Background Work (if applicable)

* External services.
* APIs, workers, schedulers, or webhooks.

### 8) Testing Strategy (required)

* Unit tests: modules and behaviors.
* Integration tests: real DB flows (no mocks).
* E2E tests: critical user journeys.
* Deterministic setup and teardown.

### 9) Acceptance Criteria

* A checklist of verifiable conditions that define “done”.

### 10) Observability and Guardrails

* Required logs.
* Metrics, alerts, or failure visibility.

### 11) Security and Privacy

* Authentication and authorization surfaces.
* RLS checks and least-privilege access.
* Secret handling considerations.

### 12) Rollout Plan

* Feature flags if required.
* Backward compatibility.
* Cleanup tasks after rollout.

### 13) Risks and Open Questions

* Any ambiguity.
* Any missing information.
* Any product or technical decisions that require confirmation.

---

## OUTPUT RULES

* The PRD must reflect the **actual** architecture of this repo.
* Reference pattern prompts explicitly when relevant.
* Do NOT include implementation code.
* Write clearly, concisely, and precisely.
* This document will be used by AI agents and humans to execute the feature.

---

## Usage

To define and build a new feature, simply @ mention this prompt and provide it context of what you want to build.

Example:
```
@.ai/workflows/create-prd.prompt.md

Feature:
Add a new navigation item called "Jobs", create a jobs listing and details page. This is a CRUD interface for the jobs table.
```

You will create and save the PRD exactly as specified above.

Then you can execute it using the execute-prd prompt:

Example:
```
@.ai/workflows/execute-prd.prompt.md
PRD: prd/004-create-jobs-view.md
```