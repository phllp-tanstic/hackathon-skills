# Hackathon Evidence Audit Skill

## Purpose

Use this skill when a hackathon project needs a rigorous technical, security, or judge-readiness audit of implemented claims.

The goal is not to generate a long list of possible issues. The goal is to identify concrete claims, test them against real trust boundaries and runtime behavior, independently verify material findings, and produce evidence that can survive judge scrutiny.

This skill is inspired by source-first, independently verified audit methodology, adapted for hackathon MVPs where time is constrained but truthfulness and proof still matter.

## Core Principle

**A claim is not verified because one agent found supporting evidence. A material claim or finding should survive an independent second check.**

Use this chain:

**Claim → Candidate Evidence → Independent Verification → Verdict → Submission-safe wording**

## Operating Modes

### Focused Review
Use when investigating one claim, bug, risk, or integration.

### Full Evidence Audit
Use before final submission, judge review, or whenever the user explicitly asks for a comprehensive audit.

A full audit should cover the product's central claim, sponsor integration, money/risk/auth boundaries, deployment, live-data claims, and the final demo path.

## Phase 1 - Establish Audit Scope

Record:
- repository and branch/commit under review,
- production blueprint or authoritative requirements,
- deployed environment if applicable,
- core product claim,
- sponsor integrations,
- claims intended for README/pitch/demo,
- areas explicitly out of scope,
- known external gates.

Do not imply that an audit covered areas that were never inspected.

## Phase 2 - Build a Claim Ledger

Create a deterministic list of material claims.

For each claim record:
- `claim_id`
- exact claim text
- required implementation path
- expected observable result
- evidence source
- verification owner
- status

Use statuses:
- `PLANNED`
- `CANDIDATE`
- `VERIFIED`
- `REJECTED`
- `NEEDS_VALIDATION`
- `GATED`
- `OUT_OF_SCOPE`

A claim must not move directly from `PLANNED` to `VERIFIED` merely because implementation exists.

## Phase 3 - Source-First Investigation

Inspect the source path before relying on UI output or narration.

Trace:
- input,
- validation,
- authorization,
- business logic,
- external calls,
- persistence,
- error handling,
- output.

For security- or money-sensitive behavior, identify:
- lower-trust actor/input,
- intended control,
- protected resource,
- failure condition,
- concrete consequence.

Missing best practice alone is not a confirmed security finding.

## Phase 4 - Candidate Evidence

A first-pass investigator may produce a `CANDIDATE` only when it has concrete support.

Acceptable evidence can include:
- deterministic test result,
- integration test,
- live provider response,
- transaction receipt,
- database state transition,
- deployed endpoint behavior,
- reproducible error path,
- source trace showing an enforced boundary,
- source trace showing a bypass or missing enforcement.

A screenshot without a traceable backend path is weak evidence.

## Phase 5 - Independent Verification

Every material candidate should be checked again by a fresh verification pass that does not merely repeat the first investigator's conclusion.

The verifier should receive:
- the claim,
- the relevant scope,
- candidate evidence,
- reproduction steps,

but should independently inspect the decisive code or behavior.

The verifier may return:
- `VERIFIED`
- `REJECTED`
- `NEEDS_VALIDATION`
- `GATED`

For a negative finding, independent verification should confirm both the affected boundary and the observable consequence.

For a positive product claim, independent verification should confirm the actual end-to-end capability rather than only component existence.

## Phase 6 - Negative-Case Audit

For every core control, test at least one refusal or failure path where relevant.

Examples:
- unauthorized caller,
- overspend,
- stale price,
- missing provider,
- invalid signature,
- low confidence,
- duplicate request,
- failed settlement,
- missing credentials,
- malformed data,
- expired authorization.

A product that only works on the happy path is not fully evidenced.

## Phase 7 - External Facts and Gates

If the decisive fact is outside the repository or accessible runtime, do not guess.

Use `NEEDS_VALIDATION` or `GATED` for things such as:
- sponsor approval,
- production credentials,
- provider entitlements,
- public display rights,
- mainnet funding,
- environment policy,
- third-party configuration not visible in source.

Record exactly what fact is missing and how the owner can safely verify it.

## Phase 8 - Separate Severity from Certainty

Only verified defects receive severity.

Suggested severity:
- `CRITICAL` — invalidates the core product or creates catastrophic security/financial exposure.
- `HIGH` — major required capability fails or an explicit control can be materially bypassed.
- `MEDIUM` — meaningful weakness with limited blast radius or narrower conditions.
- `LOW` — non-core weakness, polish issue, or low-impact technical risk.

`NEEDS_VALIDATION` is not a low-confidence vulnerability and should not receive severity.

## Phase 9 - Submission Claim Verification

Extract material claims from:
- README,
- pitch deck,
- demo script,
- video narration,
- submission form,
- landing page,
- social announcement.

Map each one to the claim ledger.

Allowed final labels:
- `VERIFIED`
- `SUPPORTED WITH LIMITATION`
- `PLANNED`
- `GATED`
- `UNSUPPORTED`

Rewrite or remove `UNSUPPORTED` claims.

## Phase 10 - Coverage Critic

Before closing a full audit, perform a separate coverage pass that asks:
- Which blueprint requirements were never mapped to a claim?
- Which sponsor requirements were never tested?
- Which trust boundaries were never exercised?
- Which live/deployed claims rely only on static inspection?
- Which demo steps have no negative-case check?
- Which external gates are being silently ignored?

The critic should add missing work rather than automatically declaring the audit complete.

## Required Output

### Verified Claims
Capabilities with independently confirmed evidence.

### Verified Findings
Confirmed implementation/security defects with severity and smallest effective fix.

### Rejected Candidates
Suspected issues or claims that did not survive verification.

### Needs Validation
Source-grounded hypotheses blocked by unavailable evidence.

### External Gates
Dependencies outside the team's direct control.

### Coverage Gaps
What was not audited or could not be exercised.

### Submission-Safe Claims
Exact statements the team can responsibly make now.

### Forbidden Claims
Anything that would overstate current implementation.

## Rules

1. Do not equate installed SDKs with working integrations.
2. Do not equate deployed code with successful end-to-end execution.
3. Do not equate passing unit tests with production readiness.
4. Do not elevate guesses into findings.
5. Do not hide unresolved external dependencies.
6. Do not treat one agent's conclusion as final for material findings.
7. Prefer the smallest reproducible proof over dramatic testing.
8. Preserve exact evidence needed to reproduce decisive results.
9. Keep audit scope explicit.
10. Never change product claims to fit implementation without flagging the discrepancy.

## Final Audit Question

For every important statement, ask:

> **If a judge challenged this claim and asked us to prove it now, what exact evidence would we show?**

If there is no strong answer, the claim is not submission-ready.
