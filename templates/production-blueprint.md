# Production Blueprint Template

## 1. Product thesis
- Product:
- One-line thesis:
- Primary user:
- Core problem:
- Why now:
- Build-Right Gate result:

## 2. Hackathon fit
- Track:
- Sponsor technology:
- Judging criteria:
- Required submission artifacts:
- Native sponsor dependency:

## 3. Product boundary
### Core proof

### Supporting UX

### Stretch

### Explicit non-goals

## 4. Canonical user journey
Document the exact end-to-end flow and observable state transitions.

## 5. System architecture
- Frontend:
- Backend/services:
- Database/storage:
- External providers:
- Chain/contracts:
- Agent/AI layer:
- Deterministic control layer:
- Deployment:

## 6. Data and state model
Define schemas, provenance, timestamps, identifiers, lifecycle, retention, and migrations.

## 7. Trust and security boundaries
List invariants, authorization boundaries, spend/permission limits, replay/concurrency controls, secrets, failure recovery, and admin surfaces.

## 8. External dependency matrix
| Dependency | Purpose | Status | Verification | Fallback |
|---|---|---|---|---|

Statuses: VERIFIED / AVAILABLE BUT UNVERIFIED / GATED / UNSUPPORTED / UNKNOWN.

## 9. Quantitative/AI methodology
If applicable: point-in-time rules, training/evaluation split, OOS methodology, baselines, confidence, abstention, reproducibility, and model-vs-deterministic responsibility.

## 10. Implementation milestones
For each milestone define deliverable, acceptance criteria, tests, and audit checkpoint.

## 11. Testing strategy
- Unit:
- Integration:
- Negative paths:
- Database/migrations:
- Provider/network:
- E2E:
- Security invariants:
- Live opt-in tests:

## 12. Deployment plan
Public URL, environments, CI/CD, database/services, secrets, observability, health checks, rollback.

## 13. Demo proof plan
Define the shortest judge-visible path proving the thesis, including at least one meaningful rejection/failure path where relevant.

## 14. Evidence ledger
Track transactions, logs, screenshots, metrics, test runs, deployment identifiers, and other proof used in submission claims.

## 15. Claim boundaries
State what can and cannot be truthfully claimed at the current milestone.

## 16. Risks and gates
Rank by impact and dependency. Include external gates separately from implementation work.

## 17. Definition of done
Concrete, verifiable conditions for calling the public MVP complete.

## 18. Handover protocol
Record current commit, deployed version, verified tests, unresolved gates, next dependency-ordered tasks, and prohibited shortcuts.
