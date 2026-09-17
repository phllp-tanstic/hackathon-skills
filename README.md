# Hackathon Skills

Private, version-controlled skill library for hackathon ideation, production planning, implementation control, audit, demo readiness, and submission quality.

## Current skills

- `skills/build-right/SKILL.md` — validates the problem, user, differentiation, MVP boundary, proof plan, demand evidence, and demo-first development before a production blueprint is written.
- `skills/blueprint-audit/SKILL.md` — continuously checks blueprint alignment, implementation truth, scope drift, false completeness, mocks/hardcoding, testing, demo readiness, and submission claims.

## Working model

**Ideation → Build-Right Gate → Production Blueprint → Build → Continuous Blueprint Audit → Judge/Demo Audit → Submission**

## Repository policy

This repository is the canonical source of truth for these skills. Improvements discovered during real hackathon projects should be folded back into the relevant skill, template, or example rather than maintained as isolated project-specific instructions.

## Structure

```text
hackathon-skills/
├── README.md
├── CHANGELOG.md
├── skills/
│   ├── build-right/
│   │   └── SKILL.md
│   └── blueprint-audit/
│       └── SKILL.md
├── templates/
│   ├── production-blueprint.md
│   ├── milestone-audit.md
│   └── submission-audit.md
└── examples/
```
