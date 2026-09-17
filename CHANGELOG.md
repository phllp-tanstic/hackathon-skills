# Changelog

All material changes to the hackathon skill system should be recorded here.

## 2026-09-17 — Spec-driven and independent-evidence expansion

### Added
- `Spec-Driven Build` skill: constitution → specify → plan → tasks → implement → converge.
- Explicit assess → fix → test bug-fix subflow so diagnosis and verification remain separate from repair.
- `Evidence Audit` skill with claim ledger, candidate state, independent verification, negative-case checks, coverage critic, and submission-safe claim mapping.

### Methodology influences
- GitHub Spec Kit: separation of what/why from how, artifact-driven implementation, convergence, evidence-backed idea assessment, and assess/fix/test separation.
- Cloudflare Security Audit Skill: source-first investigation, explicit coverage, candidate-versus-confirmed distinction, independent verification, external-fact discipline, and separation of certainty from severity.

These principles were adapted for hackathon MVP development and judge-readiness rather than copied as general-purpose replacements for the upstream tools.

## 2026-09-17 — Initial repository baseline

### Added
- `Build-Right` skill for evidence-based concept validation before production blueprint lock.
- `Blueprint Audit` skill for continuous implementation, security, integration, deployment, demo, and claim verification.
- Production Blueprint template.
- Milestone Audit template.
- Final Submission Audit template.
- Canonical lifecycle: Ideation → Build-Right Gate → Production Blueprint → Build → Continuous Blueprint Audit → Judge/Demo Audit → Submission.

### Design principles
- Evidence over enthusiasm.
- Repository truth over presentation claims.
- No silent hardcoding or mock substitution for core proof.
- External gates identified early and kept distinct from implementation work.
- Public usability treated separately from local correctness.
- Deterministic enforcement for critical money/security/authorization controls.
- Quantitative projects require point-in-time discipline and out-of-sample validation.
