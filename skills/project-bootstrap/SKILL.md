# Hackathon Project Bootstrap Skill

## Purpose

Use this skill at the start of a new hackathon project or when an existing repository needs to be brought under the canonical hackathon workflow.

The goal is to establish a consistent operating system for ChatGPT, Codex, Claude, and other coding agents before significant implementation begins.

This skill does not replace the other skills. It determines which skills apply, creates the minimum project-control artifacts, and points every agent back to the canonical methodology.

## Canonical Source

Use the private repository `phllp-tanstic/hackathon-skills` as the source of truth.

Do not duplicate full skill bodies into project repositories unless explicitly required by the target agent or environment. Prefer lightweight project-local instruction files that reference the canonical skill paths.

## Core Principle

**Initialize the project process before scaling implementation.**

A new hackathon project should begin with:

**BOOTSTRAP → BUILD-RIGHT → BLUEPRINT → SPEC-DRIVEN BUILD → BLUEPRINT AUDIT → EVIDENCE AUDIT → SUBMISSION**

## Phase 1 - Discover Project State

Inspect the repository and available project context before writing control files.

Determine:
- hackathon and track,
- sponsor requirements,
- judging criteria,
- repository status,
- current branch,
- existing architecture,
- whether code already exists,
- current deployment target,
- external dependencies and credentials,
- existing docs such as `AGENTS.md`, `CLAUDE.md`, README, blueprint, handover, or ADRs,
- known deadlines or submission constraints,
- whether the project is greenfield or existing.

Do not overwrite useful existing process documents blindly.

## Phase 2 - Select Applicable Skills

Use the following routing logic:

- New idea or unclear thesis → `skills/build-right/SKILL.md`
- Approved product moving into development → `skills/spec-driven-build/SKILL.md`
- Existing implementation requiring milestone control → `skills/blueprint-audit/SKILL.md`
- Final technical/judge/security verification → `skills/evidence-audit/SKILL.md`
- New repository or existing repo without project controls → this bootstrap skill

If several apply, establish the full lifecycle but invoke only the phase needed now.

## Phase 3 - Establish Project Constitution

Create or confirm a short project constitution covering non-negotiable rules.

Default constitution principles:

1. No hardcoded or mocked core capability may be represented as live.
2. No shortcut should be taken merely because of time pressure if it invalidates the product claim.
3. Sponsor technology must be materially integrated where required.
4. Critical money, authorization, compliance, or risk controls should be deterministic where practical.
5. Implemented does not mean verified.
6. Passing unit tests does not mean production-ready.
7. External gates must be recorded, not hidden.
8. Public deployment claims require a publicly reachable deployment.
9. Production claims must match the actual environment and data source.
10. Evidence should be preserved for material capabilities and failures.
11. Scope changes that alter the product thesis require explicit approval.
12. Submission wording must never exceed verified capability.

Project-specific constraints may be added, but these defaults should not be weakened silently.

## Phase 4 - Create Minimum Project-Control Artifacts

Create the following only when useful and absent:

```text
AGENTS.md
CLAUDE.md
docs/
  PRODUCT.md
  PRODUCTION_BLUEPRINT.md
  DECISIONS.md
  MILESTONE_STATUS.md
  EVIDENCE_LEDGER.md
```

Do not create empty documents for appearance alone. Each artifact should have a defined role.

### `AGENTS.md`

Purpose: operating instructions for Codex, ChatGPT coding agents, and other agentic builders.

Include:
- canonical skill repository reference,
- skill routing,
- project constitution,
- current source-of-truth documents,
- implementation rules,
- verification requirements,
- prohibited claims/shortcuts,
- delegation conventions if relevant.

### `CLAUDE.md`

Purpose: Claude/Claude Code project instructions.

Keep behavior aligned with `AGENTS.md` while using concise Claude-specific wording where useful.

### `docs/PRODUCT.md`

Purpose: concise product contract.

Include:
- specific target user,
- job to be done,
- pain,
- canonical sentence: `We help [specific user] do [specific job] without [specific pain].`,
- core claim,
- differentiation,
- sponsor dependency,
- explicit non-goals.

Do not invent these if Build-Right has not yet resolved them.

### `docs/PRODUCTION_BLUEPRINT.md`

Purpose: implementation source of truth after product validation.

Use the canonical Production Blueprint template from the skills repository.

### `docs/DECISIONS.md`

Purpose: record meaningful product and technical decisions.

For each decision record:
- date,
- context,
- decision,
- alternatives considered,
- reason,
- consequences,
- status.

Avoid logging trivial implementation details.

### `docs/MILESTONE_STATUS.md`

Purpose: current verified state, not optimistic progress reporting.

For each milestone record:
- intended capability,
- actual capability,
- tests/evidence,
- blockers,
- external gates,
- next highest-leverage step.

### `docs/EVIDENCE_LEDGER.md`

Purpose: track material claims and their proof.

Suggested fields:

| Claim | Required Evidence | Current Evidence | Status | Limitation |
|---|---|---|---|---|

Use statuses compatible with Evidence Audit where useful:
- PLANNED
- CANDIDATE
- VERIFIED
- REJECTED
- NEEDS VALIDATION
- GATED

## Phase 5 - Wire Agent Instructions to Canonical Skills

Project-local files should reference, not redefine, the canonical methodology.

Recommended instruction block:

```md
Canonical methodology repository:
https://github.com/phllp-tanstic/hackathon-skills

Before a major project phase, read the relevant canonical skill:
- Ideation/refinement: `skills/build-right/SKILL.md`
- Build execution: `skills/spec-driven-build/SKILL.md`
- Milestone audit: `skills/blueprint-audit/SKILL.md`
- Final evidence/judge audit: `skills/evidence-audit/SKILL.md`

The canonical repository wins if local copies drift.
```

If the agent cannot access the private repository, materialize only the required skill into the project or provide it directly for that session. Mark any local copy with its source path/version so it can be refreshed later.

## Phase 6 - Existing Repository Bootstrap

For an existing codebase:

1. Inspect current source and docs before generating anything.
2. Identify the implied product thesis from actual implementation.
3. Compare it with stated README/submission claims.
4. Flag inconsistencies rather than rewriting history.
5. Preserve valid existing architecture and conventions.
6. Create only missing control artifacts.
7. Run Blueprint Audit after bootstrap to establish the truthful current state.

Do not force a greenfield structure onto a mature repository.

## Phase 7 - Greenfield Bootstrap

For a new project:

1. Run Build-Right first.
2. Do not produce a production blueprint until the product thesis passes the Build-Right gate.
3. Create PRODUCT.md from the approved thesis.
4. Create PRODUCTION_BLUEPRINT.md using the canonical template.
5. Create AGENTS.md and CLAUDE.md.
6. Seed DECISIONS.md, MILESTONE_STATUS.md, and EVIDENCE_LEDGER.md with real initial state.
7. Move implementation into Spec-Driven Build.

## Phase 8 - Team Role Mapping

When the team uses multiple agents, define clear responsibilities.

Suggested default:
- Technical lead / orchestrator: owns product decisions, blueprint, milestone acceptance, and final claims.
- Primary builder: implements scoped tasks from the approved plan.
- Debugger/fixer: diagnoses and fixes bounded defects using ASSESS → FIX → TEST.
- Auditor/verifier: independently checks important claims and findings.

Avoid using the same agent as both sole implementer and sole final verifier for material claims when an independent pass is feasible.

## Phase 9 - Initial Bootstrap Report

After bootstrap, report:

### Project Identity
Hackathon, track, repo, deployment target.

### Product State
Whether thesis is approved, unclear, or drifting.

### Canonical Documents
Which files now govern the project.

### Active Skill
Which skill should be used next and why.

### Known Gates
Credentials, providers, funds, licensing, deployment, or sponsor constraints.

### Immediate Next Step
Exactly one highest-leverage action.

## Stop Conditions

Stop or flag before implementation if:
- target user/problem is still vague,
- sponsor requirement is misunderstood,
- core claim cannot be stated,
- existing project claims materially contradict implementation,
- the requested bootstrap would overwrite authoritative project documents,
- required private skill access is unavailable and the user has not supplied the needed skill content.

## Bootstrap Completion Gate

A project is considered bootstrapped when:

- canonical methodology is referenced,
- applicable skill routing is explicit,
- product source of truth is identified,
- project constitution exists,
- agent instruction files exist where relevant,
- blueprint state is known,
- milestone/evidence tracking has a home,
- the next active skill is unambiguous.

## Final Question

Before coding begins, ask:

> **Does every agent know what we are building, which rules are non-negotiable, which document is authoritative, which skill governs the current phase, and what evidence will prove completion?**

If not, bootstrap is incomplete.
