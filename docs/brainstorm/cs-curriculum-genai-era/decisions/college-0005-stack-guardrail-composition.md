# college-0005 — The stack guardrail is an approved store per kind, plus the design system and a stand-in data lake

**Status**: ACCEPTED
**Date**: 2026-09-27

## Context

Decision college-0003 introduced the stack guardrail as "the professor sets the tech stack per cohort as a hard guardrail; a cohort lives in one shop (Postgres, SQL Server, whichever the professor chose)." The UX/UI dive amended it to include the design system, and the security dive noted the identity source may be fixed in it when the semester runs short. The guardrail's contents were accumulating as amendments to a decision about the first slice and boundaries.

The data persistence dive (2026-09-27) established that the graduate must know every kind of store (relational, document, graph, key/value, cache, text search, blob and object, time series, event streams) and must exercise the choice of kind as a design judgment with cost as a factor. A guardrail that fixes one database cannot carry that: a real shop is an approved stack with a product per kind, usually with some kinds missing, and the missing kinds are where a corporate persistence judgment is actually made. The same dive established that analytics is an inherited obligation, which the cohort can only practice if the organization's lake and data standard exist to inherit.

## Decision

The stack guardrail the professor sets per cohort consists of the items below, each carried at the weight the cohort's **company posture** sets (size and velocity, stated at cohort start; [decision college-0010](college-0010-company-posture-scales-the-guardrail.md), _amendment of 2026-09-27_):

- **An approved store per kind the shop has, silent on the kinds it does not.** The professor names the product for each kind the cohort may use (for example Postgres for relational, Redis for cache, OpenSearch for text search, S3-compatible for blob, a stream product for events) and deliberately omits some kinds. When a scenario wants an omitted kind, the cohort does it in an approved kind and defends the cost, or writes a request to the professor as the guardrail's owner. An unapproved store appearing in a build is a failing result.
- **The design system**: tokens, components, controls, UI toolkit, as the UX/UI dive placed it. Deviations are requested, not made.
- **A stand-in data lake and a written company data standard.** The standard says what every context publishes into the lake and in what shape. This exists so the analytics obligation is real: a build that passes every scenario test and publishes nothing fails the standard.
- **Approved transports and the shop's API standard** (REST, gRPC, events on the stream, file drop; versioning rules), inherited per integration the way stores are inherited per kind. _Added 2026-09-27 (integration contracts dive)._
- **The observability standard and an approved telemetry stack** (log shape, metrics and traces collected, health endpoint, alerting channel, runbook form), inherited by every slice the way stores and transports are. A build that emits nothing fails the standard. _Added 2026-09-27 (operability dive)._
- **The resilience standard** (a timeout on every outbound call, retries with a ceiling and backoff, a degraded mode instead of a crash, idempotent handling of anything retried, fail-closed on anything that guards access). An outbound call with no timeout is a failing result. _Added 2026-09-27 (resilience dive)._
- **The performance budget and the load tool** (a response-time budget per kind of call, a load the platform must sustain, the tool that measures both). Thin by design. _Added 2026-09-27 (performance and scale dive)._
- **An agent budget per slice** (the runs and tokens a cohort may spend on one slice's accuracy cycle), the project-cost lever's standard side. _Added 2026-09-27 (cost dive, decision college-0009)._
- **The compliance standard**, citing the regulation the professor chose the domain to be under (decision college-0011): data classification, retention and deletion, minimum necessary access, notice, breach notification, no regulated data in logs, de-identified data to the lake. Not scaled by posture. _Added 2026-09-27 (privacy and compliance dive)._
- **The accessibility standard** the company's records cite (a published standard or the law that adopts it), met by the design system's conformance; every screen is built from the design system. Floored by law where one applies. _Added 2026-09-27 (accessibility dive)._
- **Optionally, the identity source**, fixed only when the security semester does not have time for the cohort to decide it (security dive).

Choosing which kinds the shop has, which to omit, and which scenarios will want the omitted ones is part of the professor's slice design, alongside the scripted first collision from decision college-0003.

## Consequences

- Decision college-0003's guardrail bullet is superseded by this record. Its text is left in place with a pointer here; the design-system and identity-source amendments it carried are restated above.
- The persistence dive's slice proofs depend on this: one kind per slice, a considered-and-rejected kind, a kind the shop lacks, and an inherited analytics obligation are only exercisable against a guardrail of this shape.
- The professor's per-cohort setup grows: a product per approved kind, a design system, a stand-in lake, a data standard. This is the classroom's cost of manufacturing corporate constraints, and it is the same cost decision college-0003 already accepted for the platform.
- The cohort system's developer-side markdown (README, cohort-system table) gains the company data standard as an inherited file, the observability standard after the operability dive, the resilience standard after the resilience dive, the performance budget after the performance and scale dive, the agent budget per slice after the cost dive, and the change standard (release process, approvals, windows, rollback rule, change record) after the change management dive, at the posture's weight, the compliance standard after the privacy and compliance dive, at the regulation's, and the accessibility standard after the accessibility dive, met by the design system.
- Everything this record lists is a business standard in the sense of decision college-0007; a stakeholder who wants to change one inside a scenario writes a request to the professor, not a requirement.

## Session

Session 45bafc, 2026-09-27, branch `college-curriculum`.
