# Build-Right Skill

## Purpose

Prevent a technically impressive hackathon project from becoming a polished solution to a weak, generic, unproven, or badly scoped problem.

Use this skill after initial ideation and before locking the production blueprint. Re-run it whenever the product thesis materially changes.

## Core principle

**Validate what deserves to be built before optimizing how to build it.**

The output is not encouragement. It is a decision-quality artifact that exposes assumptions, evidence gaps, differentiation risk, implementation risk, and the smallest credible proof that can win judge confidence.

## Required inputs

Gather, research, or explicitly mark unknown:

- Hackathon name, tracks, sponsor technologies, rules, judging criteria, deadline, submission requirements.
- Proposed product thesis in one sentence.
- Target user and the exact painful job/problem.
- Why the problem exists now.
- Existing alternatives and adjacent products.
- Required sponsor/platform integration.
- Team capabilities, credentials, funds, infrastructure, licensing/data constraints.
- Intended public demo and proof surface.

Never silently invent missing constraints.

## Phase 1 — Problem validation

Test the problem before the solution.

Answer:

1. Who experiences the problem?
2. What exact event triggers it?
3. What do they do today instead?
4. What does the failure cost: money, time, risk, conversion, reliability, privacy, compliance, or opportunity?
5. Is the pain frequent or severe enough to justify a product?
6. Is there evidence of demand from credible sources: sponsor docs, developer requests, ecosystem gaps, user discussions, issue trackers, YC/RFS-style requests, research, market behavior, or existing workaround adoption?
7. Is the problem materially connected to the hackathon rather than retrofitted to a sponsor API?

Classify evidence separately from assumptions.

## Phase 2 — User and workflow truth

Write the current workflow and proposed workflow step-by-step.

Reject vague personas such as “crypto users,” “developers,” or “AI agents” unless narrowed to a concrete operator and job.

Identify:

- Primary user.
- Economic buyer, if different.
- System/agent acting on the user's behalf.
- Trust boundary.
- Failure boundary.
- Moment where the product creates measurable value.

## Phase 3 — Competitive and novelty stress test

Research direct competitors, primitives, open-source projects, sponsor-native capabilities, and obvious substitutes.

For each, determine:

- What already exists.
- What the proposed product adds.
- Whether that addition is a feature, workflow improvement, infrastructure primitive, or genuinely new capability.
- Whether the differentiation survives if competitors add one obvious feature.

Do not claim novelty because branding or UI differs.

Produce a concise differentiation statement:

> Existing systems do X. This project uniquely proves/enables Y under Z constraint.

If that sentence cannot be defended, the concept is not locked.

## Phase 4 — Sponsor and hackathon fit

Map every relevant judging criterion to concrete product evidence.

Distinguish:

- **Native dependency:** the product meaningfully requires the sponsor technology.
- **Useful integration:** sponsor technology improves the product but is replaceable.
- **Decorative integration:** the sponsor is present mainly for eligibility.

Prefer native dependency where reasonable. Flag decorative integrations.

Do not optimize for speculative judge preferences; optimize for published criteria and demonstrable technical/product merit.

## Phase 5 — Feasibility and external gates

Before blueprint lock, identify every external dependency:

- API credentials.
- Paid plans or funds.
- Testnet/mainnet availability.
- Data licensing/display rights.
- Rate limits.
- Geographic/account restrictions.
- SDK maturity.
- Smart-contract/network constraints.
- Deployment constraints.
- Hardware or OS constraints.

Probe critical dependencies early when safe and permitted.

Classify each as:

- VERIFIED
- AVAILABLE BUT UNVERIFIED
- GATED
- UNSUPPORTED
- UNKNOWN

A critical GATED dependency requires an explicit fallback that preserves the thesis, or the concept must be reconsidered.

## Phase 6 — Proof-first MVP boundary

Define the smallest end-to-end artifact that proves the core claim.

The MVP must contain:

- One canonical user journey.
- Real integration where the core claim depends on it.
- Deterministic controls around money, permissions, security, or irreversible actions.
- Observable evidence: receipts, logs, state transitions, transactions, metrics, tests, or reproducible outputs.
- Explicit failure/abstention behavior.
- Publicly usable deployment when the hackathon expects a usable product.

Separate:

- **Core proof** — must work.
- **Supporting UX** — improves comprehension.
- **Stretch** — only after proof is green.

## Phase 7 — No-shortcut test

Challenge every proposed shortcut:

- Hardcoded live-looking data.
- Mocks presented as real integrations.
- UI-only workflows without backend truth.
- Manual steps hidden from the demo.
- Claims that exceed implementation.
- Security enforced only in prompts/UI.
- Tests that assert mocks rather than production behavior.
- “AI” where deterministic logic is actually doing the work, or deterministic behavior falsely described as AI.

Mocks are acceptable only when clearly labeled and when they do not substitute for the core proof.

## Phase 8 — Measurement plan

Define success before implementation.

Examples:

- End-to-end task completion.
- Latency.
- Cost.
- Accuracy/calibration.
- Rejection/failure correctness.
- Backtest/OOS performance.
- Security invariant coverage.
- Transaction/settlement proof.
- Public availability.

For quantitative systems, require point-in-time discipline, no lookahead, explicit train/validation/test or OOS separation, and reproducible evaluation.

## Phase 9 — Kill criteria

State conditions that should cause pivot, rescope, or abandonment, for example:

- Core provider inaccessible.
- Required integration cannot be demonstrated.
- Differentiation collapses after research.
- Core proof cannot be completed safely.
- Data cannot legally/publicly be displayed.
- Product requires fabricated evidence to appear complete.

Do not continue merely because implementation has already started.

## Required output

Produce a **Build-Right Gate** with:

### 1. Locked thesis
One sentence.

### 2. User/problem
Concrete user, trigger, current workaround, measurable pain.

### 3. Evidence
Verified evidence vs assumptions.

### 4. Differentiation
Competitor/substitute comparison and defensible novelty statement.

### 5. Hackathon fit
Criteria-to-evidence mapping and sponsor dependency classification.

### 6. Feasibility matrix
Critical dependencies with VERIFIED / AVAILABLE BUT UNVERIFIED / GATED / UNSUPPORTED / UNKNOWN status.

### 7. Core proof
The smallest end-to-end demonstration that validates the product claim.

### 8. MVP boundary
Core / supporting / stretch.

### 9. Measurement
Exact evidence required to call the MVP successful.

### 10. Risks and kill criteria
Unresolved risks and conditions requiring pivot/rescope.

### 11. Gate result
Use one of:

- **PROCEED TO BLUEPRINT** — core thesis and proof are sufficiently validated.
- **PROCEED WITH EXPLICIT GATES** — concept is viable but named external dependencies remain unresolved.
- **RESEARCH REQUIRED** — evidence is insufficient to lock architecture.
- **RESCOPE REQUIRED** — valuable problem, but current solution/MVP boundary is wrong.
- **DROP / PIVOT** — the concept cannot presently support a credible winning build.

The gate result must follow from evidence, not enthusiasm.

## Handoff to production blueprint

Only after the gate permits progress, write the production blueprint. Carry forward all verified constraints, unresolved gates, proof requirements, security boundaries, metrics, and prohibited shortcuts. Do not silently relax them during implementation.
