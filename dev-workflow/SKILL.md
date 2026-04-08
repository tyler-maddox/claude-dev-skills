---
name: dev-workflow
description: Guide the user through the full AI-driven development workflow chain: grill → PRD → issues → TDD → architecture review. Use when starting a new feature, kicking off a project, or wanting a repeatable end-to-end development process.
---

# AI-Driven Development Workflow

You are the orchestrator for a complete, repeatable development workflow. Walk the user through each stage in order, invoking the appropriate skill at each step. Do not skip stages unless the user explicitly asks to.

## The Chain

```
1. /grill-me              → Shared understanding
2. /write-a-prd           → Destination captured as GitHub issue
3. /prd-to-issues         → Work broken into vertical slices
4. /tdd                   → Each slice implemented test-first
5. /improve-codebase-architecture  → Architecture audited and improved
```

## Stage Guide

### Stage 1 — Grill Me
**Goal**: Reach shared understanding before any planning.
**When to invoke**: At the start of any new feature or problem.
**What it produces**: A resolved design tree — every major decision branch explored and settled.
**Invoke with**: `/grill-me`

### Stage 2 — Write a PRD
**Goal**: Capture the destination (not the journey) as a GitHub issue.
**When to invoke**: After shared understanding is established in Stage 1.
**What it produces**: A GitHub issue with problem statement, user stories, implementation decisions, and testing decisions.
**Invoke with**: `/write-a-prd`

### Stage 3 — PRD to Issues
**Goal**: Break the PRD into independently-grabbable vertical slices with explicit blocking relationships.
**When to invoke**: After the PRD issue exists.
**What it produces**: A set of GitHub issues — tracer bullets that cut through all integration layers, with HITL/AFK labels and dependency mapping.
**Invoke with**: `/prd-to-issues`

### Stage 4 — TDD
**Goal**: Implement each issue using red-green-refactor, testing behavior through public interfaces.
**When to invoke**: When picking up an issue from Stage 3. Repeat for each issue.
**What it produces**: Implemented, tested code. Tests describe behavior, not implementation.
**Invoke with**: `/tdd`

### Stage 5 — Improve Codebase Architecture
**Goal**: Periodically audit the codebase for shallow modules and coupling, and generate refactor RFC issues.
**When to invoke**: After a set of features lands, or when the codebase feels hard to navigate.
**What it produces**: A GitHub issue RFC with competing interface designs and a recommended refactor path.
**Invoke with**: `/improve-codebase-architecture`

---

## How to Run This Session

Ask the user: "Where are you in the workflow? Starting fresh, or picking up at a specific stage?"

- **Starting fresh**: Begin at Stage 1.
- **Have a rough idea but no PRD**: Begin at Stage 1.
- **Have shared understanding, no PRD**: Begin at Stage 2.
- **Have a PRD, no issues**: Begin at Stage 3.
- **Have issues, ready to implement**: Begin at Stage 4.
- **Code exists, want to improve it**: Begin at Stage 5.

Then invoke the appropriate skill and guide the user through each stage in sequence.
