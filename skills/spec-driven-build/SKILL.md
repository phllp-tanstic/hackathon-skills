# Hackathon Spec-Driven Build Skill

## Purpose

Use this skill after an idea passes the Build-Right gate and before or during implementation.

It converts the approved product thesis into a controlled chain of specifications, implementation tasks, verification, and convergence so AI coding agents do not gradually invent a different product while building.

This is a hackathon-focused adaptation of spec-driven development: lightweight enough for rapid builds, strict enough to preserve product intent and evidence.

## Core Principle

**Define WHAT and WHY before HOW. Break HOW into verifiable tasks. Implement. Then converge the implementation back against the specification.**

Canonical loop:

**CONSTITUTION → SPECIFY → PLAN → TASKS → IMPLEMENT → CONVERGE**

Repeat:

**IMPLEMENT → CONVERGE**

until the required MVP capabilities are verified or explicitly gated.

## Phase 0 - Project Constitution

Create once per project.

The constitution defines non-negotiable engineering and product rules that implementation agents may not silently override.

Include only rules that materially matter, such as:
- no fake live data,
- no hidden mocks in core claims,
- no hardcoded success paths,
- deterministic controls for money/risk/auth,
- explicit user authorization,
- public deployment when required,
- no unverified completion claims,
- tests required for core behavior,
- preserve raw evidence/provenance where relevant,
- fail closed for critical controls,
- external gates must remain visible.

Avoid filling the constitution with generic style preferences.

## Phase 1 - Specify

Write the feature/product specification without choosing implementation details prematurely.

Define:
- target user,
- job and pain,
- user-visible capability,
- required inputs,
- expected outputs,
- core state transitions,
- failure/refusal behavior,
- acceptance criteria,
- sponsor-specific requirement,
- evidence required to prove completion.

Every requirement should be testable or observable.

Bad requirement:

> Build a robust trading engine.

Better requirement:

> When confidence falls below the configured threshold, the system must abstain from producing an executable action and return the reason and evidence used for abstention.

## Phase 2 - Clarify

Before planning, identify ambiguities that would cause architectural or behavioral divergence.

Prioritize questions about:
- trust boundaries,
- irreversible actions,
- money movement,
- source of truth,
- live vs simulated data,
- user authorization,
- external APIs,
- persistence,
- time/session semantics,
- deployment environment,
- sponsor requirements.

Do not ask questions whose answers can safely be deferred to implementation.

Record unresolved external questions as explicit gates rather than inventing assumptions.

## Phase 3 - Plan

Choose the technical approach only after the specification is stable enough to implement.

The plan should define:
- architecture,
- components,
- data flow,
- trust boundaries,
- persistence,
- APIs/contracts,
- provider integrations,
- deployment topology,
- validation strategy,
- observability,
- migrations,
- testing layers.

For every major technical decision, connect it to a specification requirement.

Do not introduce infrastructure that has no requirement-level justification.

## Phase 4 - Tasks

Turn the plan into bounded tasks.

Each task should include:
- objective,
- files/components likely affected,
- dependency/precondition,
- behavior to implement,
- tests to add/run,
- completion evidence,
- prohibited scope changes.

A task should end in a capability that can be verified.

Avoid vague tasks such as:
- build backend,
- finish frontend,
- integrate API,
- improve security.

Prefer:

> Add authenticated provider client for historical candles, persist raw response plus normalized candles, reject malformed timestamps, and prove with unit + integration tests and one bounded live probe.

## Phase 5 - Implement

The coding agent implements one bounded task or coherent task group at a time.

During implementation:
- preserve existing verified behavior,
- avoid unrelated refactors,
- do not silently modify product semantics,
- add tests with implementation,
- document external gates,
- do not replace unavailable production integrations with undisclosed mocks,
- do not claim completion until verification runs.

If implementation discovers the specification is wrong, stop and propose a spec change instead of silently coding around it.

## Phase 6 - Converge

After implementation, compare reality back against the specification and plan.

Convergence is not code review alone.

Check:

### Requirement Coverage
Does every required behavior exist?

### Behavioral Match
Does implementation behave as specified, including failure cases?

### Evidence Match
Do tests and runtime evidence actually prove the acceptance criteria?

### Architecture Match
Did implementation preserve required trust boundaries and data flows?

### Scope Match
Did unrelated features or shortcuts enter the MVP?

### Documentation Match
Do README/demo/submission claims reflect current behavior?

Return one verdict:
- `CONVERGED`
- `PARTIAL`
- `BLOCKED`
- `DRIFTED`

`CONVERGED` requires all required in-scope acceptance criteria to be verified or explicitly accepted as external gates.

## Change Control

Specifications are allowed to evolve, but changes must be deliberate.

Use:

**Discovery → Proposed Spec Change → Reason → Product Impact → Technical Impact → Approval → Updated Spec/Plan/Tasks**

Do not rewrite history so a failed implementation appears to have always matched the specification.

## Bug-Fix Subflow

When an implemented feature breaks, do not immediately patch the symptom.

Use:

**ASSESS → FIX → TEST**

### Assess
- reproduce the symptom,
- identify expected behavior,
- trace likely cause,
- bound affected scope,
- define regression test.

### Fix
- change the smallest responsible layer,
- avoid unrelated refactoring,
- preserve product semantics.

### Test
- rerun original reproduction,
- run regression test,
- run relevant neighboring tests,
- verify deployed/runtime behavior when appropriate.

Verdict:
- `VERIFIED`
- `PARTIAL`
- `FAILED`

A code change without verification is not a successful bug fix.

## Feature Completion Contract

A feature is complete only when this chain exists:

**Requirement → Implementation → Test → Evidence → Demo behavior**

If any link is missing, classify the feature accordingly rather than calling it done.

## Agent Delegation Contract

When delegating to Codex, Claude Code, Cline, or another builder, provide:
- authoritative spec,
- current task only,
- relevant constraints,
- allowed files/scope where useful,
- required tests,
- evidence expected,
- known gates,
- explicit instruction not to invent missing requirements.

The builder should report:
- files changed,
- behavior implemented,
- tests run and exact result,
- blockers/gates,
- deviations from plan,
- unverified claims.

## Hackathon Time Discipline

Spec-driven does not mean document-heavy.

Use the smallest artifact that prevents ambiguity.

Spend documentation effort where mistakes are expensive:
- product thesis,
- sponsor integration,
- financial behavior,
- authorization,
- data integrity,
- external provider assumptions,
- demo-critical paths.

Do not produce paperwork that does not improve implementation or proof.

## Required Output Before Building

At minimum, the project should have:
- constitution,
- approved product specification,
- technical plan,
- bounded task list,
- acceptance/evidence criteria.

## Final Rule

Never allow the coding agent to redefine success after implementation.

Success is defined before the task begins, then checked afterward.

**SPECIFY → BUILD → PROVE → CONVERGE.**
