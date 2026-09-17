# Hackathon Skills

Private, version-controlled skill library for hackathon ideation, production planning, implementation control, audit, demo readiness, and submission quality.

## Current skills

- `skills/build-right/SKILL.md` — validates the problem, user, differentiation, MVP boundary, proof plan, demand evidence, and demo-first development before a production blueprint is written.
- `skills/spec-driven-build/SKILL.md` — converts an approved thesis into constitution → specification → plan → tasks → implementation → convergence, with a separate assess → fix → test path for bugs.
- `skills/blueprint-audit/SKILL.md` — continuously checks blueprint alignment, implementation truth, scope drift, false completeness, mocks/hardcoding, testing, demo readiness, and submission claims.
- `skills/evidence-audit/SKILL.md` — source-first audit methodology with a claim ledger, candidate evidence, independent verification, coverage criticism, and submission-safe claim control.

## Working model

**Ideation → Build-Right Gate → Production Blueprint → Spec-Driven Build → Continuous Blueprint Audit → Evidence Audit → Judge/Demo Audit → Submission**

Inside implementation, use:

**CONSTITUTION → SPECIFY → PLAN → TASKS → IMPLEMENT → CONVERGE**

For defects, use:

**ASSESS → FIX → TEST**

For material audit claims, use:

**CLAIM → CANDIDATE EVIDENCE → INDEPENDENT VERIFICATION → VERDICT → SUBMISSION-SAFE WORDING**

## Repository policy

This repository is the canonical source of truth for these skills. Improvements discovered during real hackathon projects should be folded back into the relevant skill, template, or example rather than maintained as isolated project-specific instructions.

External methodologies may inform this library, but skills here should be adapted to our hackathon workflow rather than copied wholesale. Preserve attribution and license obligations if source material is ever incorporated directly.

## Structure

```text
hackathon-skills/
├── README.md
├── CHANGELOG.md
├── skills/
│   ├── build-right/
│   │   └── SKILL.md
│   ├── spec-driven-build/
│   │   └── SKILL.md
│   ├── blueprint-audit/
│   │   └── SKILL.md
│   └── evidence-audit/
│       └── SKILL.md
├── templates/
│   ├── production-blueprint.md
│   ├── milestone-audit.md
│   └── submission-audit.md
└── examples/
```

## Methodology influences

The library is informed by practical patterns from strong agent workflows, including spec-driven development and independently verified source-first auditing. The objective is to extract useful principles and rework them for fast, evidence-heavy hackathon development.
