# Hackathon Skills Index

Use this index to decide which canonical skill governs the current phase of a hackathon project.

Canonical repository: `phllp-tanstic/hackathon-skills`

## Fast Routing

| Situation | Skill | Path |
|---|---|---|
| Starting a new hackathon repo or bringing an existing repo under the workflow | Project Bootstrap | `skills/project-bootstrap/SKILL.md` |
| Evaluating/refining an idea before committing to build | Build-Right | `skills/build-right/SKILL.md` |
| Turning an approved product thesis into implementation work | Spec-Driven Build | `skills/spec-driven-build/SKILL.md` |
| Checking whether implementation still matches the blueprint | Blueprint Audit | `skills/blueprint-audit/SKILL.md` |
| Verifying technical/security/judge claims before submission | Evidence Audit | `skills/evidence-audit/SKILL.md` |

## Canonical Lifecycle

**PROJECT BOOTSTRAP → BUILD-RIGHT → PRODUCTION BLUEPRINT → SPEC-DRIVEN BUILD → BLUEPRINT AUDIT → EVIDENCE AUDIT → SUBMISSION**

Inside implementation:

**CONSTITUTION → SPECIFY → PLAN → TASKS → IMPLEMENT → CONVERGE**

For defects:

**ASSESS → FIX → TEST**

For material claims:

**CLAIM → CANDIDATE EVIDENCE → INDEPENDENT VERIFICATION → VERDICT → SUBMISSION-SAFE WORDING**

## Skill Selection Rules

### Use Project Bootstrap when
- the repo is new;
- agent instructions are missing;
- the project lacks a clear source of truth;
- multiple agents need aligned operating rules;
- an existing repo needs to adopt this methodology.

Do not use bootstrap as a substitute for product validation.

### Use Build-Right when
- the idea is vague;
- the target user is broad or unclear;
- differentiation is unproven;
- sponsor fit is uncertain;
- MVP scope is not locked;
- the team cannot clearly state the product as:
  `We help [specific user] do [specific job] without [specific pain].`

Do not write the production blueprint until this gate passes.

### Use Spec-Driven Build when
- the product thesis is approved;
- the blueprint exists;
- a new milestone/feature is ready to implement;
- tasks need to be decomposed before coding;
- implementation needs a convergence gate.

A code change is not complete until the planned acceptance criteria are checked.

### Use Blueprint Audit when
- a milestone has been implemented;
- the repo may have drifted from the blueprint;
- scope changed during development;
- sponsor integration needs verification;
- tests pass but production readiness is unclear;
- there may be mock/hardcoded or false-completeness issues.

Use repeatedly during development, not only at the end.

### Use Evidence Audit when
- preparing for judges or final submission;
- reviewing security/financial/authorization boundaries;
- validating claims for README, deck, demo, video, or submission form;
- a material finding or capability requires independent verification;
- the team needs submission-safe wording.

Material claims should survive a fresh verification pass where feasible.

## Typical Agent Commands

### ChatGPT / Codex

```text
Read the canonical hackathon skills repository and apply the Project Bootstrap skill to this repository.
```

```text
Use the Build-Right skill to evaluate this hackathon concept. Do not proceed to a blueprint until the gate passes.
```

```text
Use Spec-Driven Build for the next milestone. Read the current production blueprint first.
```

```text
Run Blueprint Audit against the current repo and milestone. Repository truth wins over claimed status.
```

```text
Run Evidence Audit on all final submission claims and produce verified, limited, gated, and unsupported claim sets.
```

### Claude / Claude Code

```text
Read `SKILLS_INDEX.md` from the canonical hackathon-skills repo, load the skill matching the current phase, and treat it as the governing methodology for this task.
```

Project-local `CLAUDE.md` should reference this repository rather than maintain divergent full copies of the skills.

## Source-of-Truth Rule

The private `hackathon-skills` repository is canonical.

If a project-local instruction conflicts with an updated canonical skill:
1. preserve project-specific requirements;
2. identify the conflict;
3. do not silently overwrite the project;
4. update the project-local instruction deliberately;
5. use the canonical methodology for general workflow and verification rules.

## Minimal Decision Tree

```text
New repo / no process?
  → Project Bootstrap

Still deciding what to build?
  → Build-Right

Thesis approved and ready to code?
  → Spec-Driven Build

Checking progress or milestone truth?
  → Blueprint Audit

Preparing judge/demo/submission claims?
  → Evidence Audit
```

## Core Operating Principle

**Build the right thing → define it precisely → implement against the definition → audit reality → prove every important claim.**
