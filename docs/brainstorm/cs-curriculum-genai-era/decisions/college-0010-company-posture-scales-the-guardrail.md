# college-0010 — The professor sets the company posture, size and velocity, and it scales the guardrail

**Status**: ACCEPTED
**Date**: 2026-09-27

## Context

Decision college-0005 lists what the stack guardrail contains and has grown a bullet per dive: stores, transports, the design system, the lake and data standard, the observability standard, the resilience standard, the performance budget, the agent budget. Decision college-0007 named all of it business standards. Nothing said how heavy those standards are, and the change management dive (2026-09-27) found the dimension that decides it: what kind of company the cohort's shop is. In a company in startup mode, speed is the priority and standards are thin. In a larger company, standards and deadlines become the priority and the standards are thick. The same slice lands differently in the two, and a graduate who knows only one way is prepared for one kind of employer.

## Decision

- **The professor states the company posture at cohort start**: its size and its velocity, in a sentence the cohort can quote. Startup mode: speed first, few gates, learn from what shipped. Larger company: standards and deadlines first, a release process, approvals, windows, versioning, and dates the business was promised.
- **The posture scales every standard in the guardrail**, not only the change standard. _Amended 2026-09-27 by [decision college-0011](college-0011-domain-chosen-for-regulation-floor-not-scaled.md): except the regulatory floor, which no posture thins._ A startup's guardrail is thin everywhere: fewer approved kinds, a lighter observability standard, no change record. An enterprise's is thick everywhere. Decision college-0005's list is what a guardrail may contain; the posture says how much of it this cohort carries and at what weight.
- **The posture is a business standard in the sense of decision college-0007**, decided once for the shop. A stakeholder who wants a faster or slower change than the posture allows is making a request to the guardrail's owner, not a requirement.
- **The graduate is held to naming the posture and landing every change the way that company does**, and to naming the cost when a habit from the other kind of company is carried in.

## Consequences

- Decision college-0005 is amended by pointer: the guardrail is set within a stated company posture, which scales it.
- Slice design gains a first decision the professor makes before any scenario: which company this cohort works for. Two cohorts on the same scenario in different postures produce different systems, and a professor may run both.
- Open: whether the posture shifts mid-degree, a startup becoming a larger company, as a scripted obligation alongside the first collision (0003), the gap per slice (0008), the override (0006), and the growth event (performance dive). Proposed by the change management dive; not decided.
- The project-cost lever (decision college-0009) reads differently by posture: speed is what a startup buys with operational risk; predictability is what an enterprise buys with project time.

## Session

Session e8a087, 2026-09-27, branch `college-curriculum`.
