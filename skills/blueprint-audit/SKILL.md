# Blueprint Audit Skill

## Purpose

Act as a continuous technical/product auditor for hackathon MVPs. Verify that the repository, deployment, tests, demo, and submission remain faithful to the locked production blueprint and to what is actually implemented.

This is an evidence-based audit, not a motivational review.

## Audit philosophy

Judge the project as an MVP that should survive technical scrutiny, not merely as a staged prototype.

Never infer completion from filenames, UI copy, TODOs, test names, README claims, or intended architecture. Verify implementation and evidence.

Core rule:

**Repository truth > documentation claims > presentation claims.**

If they disagree, report the disagreement.

## Required inputs

Use as available:

- Locked production blueprint.
- Build-Right Gate.
- Repository and commit/branch under review.
- Deployment URL.
- CI/workflow results.
- Test outputs.
- Contract addresses/transaction evidence where relevant.
- Sponsor/hackathon rules and submission criteria.
- Demo script and submission copy.

Mark missing evidence explicitly.

## Continuous audit checkpoints

Run this skill at meaningful milestones, not only at submission:

1. Architecture/scaffold complete.
2. First real integration.
3. Core end-to-end flow.
4. Security/risk controls.
5. Public deployment.
6. Pre-demo freeze.
7. Final submission.

## Phase 1 — Blueprint traceability

Extract blueprint requirements into a traceability matrix.

For each requirement record:

- Requirement.
- Intended implementation.
- Actual code/evidence location.
- Status.
- Test/proof.
- Drift or caveat.

Statuses:

- VERIFIED COMPLETE
- PARTIAL
- GATED
- NOT IMPLEMENTED
- DEVIATED
- UNVERIFIED
- NOT APPLICABLE

Do not mark complete without direct evidence.

## Phase 2 — Architecture truth

Verify that architecture described in docs exists in code and that boundaries are real.

Check:

- Components/services/packages actually exist.
- Data flows match architecture.
- Trust boundaries are enforced in code.
- Persistence is real where promised.
- External providers are actually invoked where claimed.
- Chain/network/environment configuration is correct.
- Production and test behavior are not accidentally conflated.
- Sensitive operations are server-side or otherwise properly protected.

Flag dead architecture: documented components with no operative path.

## Phase 3 — Core journey proof

Trace the canonical user journey end-to-end from entry to final outcome.

Verify each state transition and identify where the flow depends on:

- Manual intervention.
- Hardcoded values.
- Mock responses.
- Local-only services.
- Hidden credentials.
- Unimplemented branches.
- Non-public infrastructure.

The demo must prove the thesis, not merely navigate screens.

## Phase 4 — Integration authenticity

For every important sponsor/provider integration determine whether it is:

- LIVE/REAL
- TESTNET/SANDBOX REAL
- MOCKED
- STUBBED
- GATED
- DEAD CODE
- UNVERIFIED

Inspect request construction, authentication boundaries, response handling, persistence, error handling, retries, rate limits, and environment selection.

Never describe sandbox/testnet evidence as mainnet/production evidence.

## Phase 5 — Hardcoding and mock audit

Search specifically for:

- Fixed prices/balances/metrics.
- Fake timestamps.
- Hardcoded transaction hashes/addresses presented as dynamic.
- Demo-only branches.
- Static API responses.
- Fixture data leaking into production paths.
- Placeholder success states.
- Client-side-only security checks.
- Suppressed errors.

Classify each occurrence:

- Legitimate constant/configuration.
- Test fixture.
- Clearly labeled demo fixture.
- Production-risk shortcut.
- Misleading/fatal shortcut.

## Phase 6 — Security and invariant audit

Prioritize invariants over generic security checklists.

Examples:

- Spend limits cannot be bypassed.
- Authorization cannot exceed user intent.
- Replay is prevented where required.
- Expiry/TTL is enforced.
- Concurrent requests cannot violate caps.
- Secrets are not exposed client-side or committed.
- Admin endpoints require authorization.
- Failure recovery does not double-spend or corrupt reservations.
- User-controlled input cannot silently change protected execution parameters.

For AI/agent systems, critical controls must live in deterministic code, not solely in model instructions.

## Phase 7 — Test quality

Do not report only test count.

Evaluate:

- Unit coverage of core logic.
- Integration tests for real boundaries.
- Negative/rejection paths.
- Concurrency/race behavior where relevant.
- Database/migration tests.
- Network/provider contract tests.
- End-to-end coverage.
- Determinism and reproducibility.
- Skipped tests and why.
- Whether tests would still pass if the core integration were broken.

Record exact verified test results and environment.

## Phase 8 — Quantitative integrity

For trading, forecasting, ranking, pricing, anomaly detection, or ML systems verify:

- Point-in-time data discipline.
- No lookahead leakage.
- Market/session time separated from ingestion time where relevant.
- OOS/holdout evaluation.
- Baseline comparison.
- Reproducible metrics.
- Corporate actions/data corrections handling where relevant.
- Confidence/abstention behavior.

Do not accept attractive backtests without leakage controls.

## Phase 9 — Deployment and public usability

Verify the product as a user/judge would encounter it.

Check:

- Public URL resolves.
- Critical routes/APIs work in deployed environment.
- No localhost dependencies.
- Environment variables are configured.
- Production database/services are reachable.
- Authentication/onboarding is usable.
- Failure states are understandable.
- Mobile/browser compatibility if relevant.
- Deployment corresponds to the audited commit.

A locally working build is not a publicly usable MVP.

## Phase 10 — Claim audit

Compare README, website, pitch, demo narration, social copy, and submission text against verified implementation.

Flag claims that are:

- VERIFIED
- TECHNICALLY TRUE BUT MISLEADING
- UNPROVEN
- OUTDATED
- FALSE

Especially inspect words such as:

- live
- production
- autonomous
- AI-powered
- audited
- secure
- real-time
- decentralized
- private
- mainnet
- fully tested
- permissionless

Replace inflated claims with precise evidence-backed wording.

## Phase 11 — Judge-readiness audit

Determine whether a judge can understand and verify within minutes:

- The problem.
- Why this product is different.
- Why the sponsor technology matters.
- The canonical workflow.
- The core technical proof.
- A real failure/rejection path.
- Evidence of implementation quality.
- What remains gated or incomplete.

Do not hide limitations. Precise limitations increase credibility.

## Severity model

Use:

- **P0 — Submission blocker:** core claim false, unsafe, broken, inaccessible, or impossible to demonstrate.
- **P1 — Major:** materially weakens thesis, security, sponsor fit, or end-to-end proof.
- **P2 — Moderate:** meaningful quality/reliability/documentation gap but core proof survives.
- **P3 — Minor:** polish, cleanup, non-critical UX/docs issue.

Severity is based on impact, not implementation effort.

## Required output

### Executive status
State the audited commit/deployment and evidence boundary.

### Blueprint traceability
Requirement-by-requirement status.

### Verified strengths
Only evidence-backed strengths.

### Findings
For each finding include:

- Severity.
- Requirement/invariant affected.
- Evidence.
- Why it matters.
- Exact remediation.
- Verification step after remediation.

### External gates
Credentials, funds, licensing, provider access, network restrictions, or other blockers that code alone cannot solve.

### Test/CI status
Exact results, skipped tests, and important coverage gaps.

### Deployment status
Public usability and commit/deployment correspondence.

### Claim corrections
Any README/demo/submission statements that must change.

### Next actions
Order strictly by dependency and severity. Do not optimize for ease or time pressure if that compromises correctness.

### Audit state
Use factual states rather than a score:

- CORE PROOF VERIFIED
- CORE PROOF PARTIAL
- BLOCKED BY EXTERNAL GATE
- IMPLEMENTATION DRIFT DETECTED
- SUBMISSION BLOCKED

Multiple states may apply.

## Final submission rule

Before final submission, require evidence for every headline claim. Anything not verified must be either completed, explicitly labeled as gated/future work, or removed from the pitch.

The goal is not to make the project look complete. The goal is to make the strongest possible project whose claims remain true under judge scrutiny.
