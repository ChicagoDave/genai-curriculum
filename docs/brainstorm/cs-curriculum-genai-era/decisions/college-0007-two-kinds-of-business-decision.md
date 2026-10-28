# college-0007 — Two kinds of business decision: standards the company holds every system to, and process design decisions the scenario's stakeholder makes

**Status**: ACCEPTED
**Date**: 2026-09-27

## Context

The dives so far have named two acceptors and called them "the business" and "the organization." The business states things in the scenario: authorization, validation rules, wireframes, what crosses a boundary. The organization states things in its records and the stack guardrail: OWASP-citing security, the design system, the company data standard, approved stores and transports. The operability dive (2026-09-27) asked whether operability was the first candidate the organization owned entirely, with no business voice in it.

The answer was that the split is wrong as named. Everything is a business decision. What differs is the kind: a **business standard** is a decision the company has made once about every system it runs, and a **business process design decision** is a decision the stakeholder makes about this system in this scenario. An observability standard and a decision that the receptionist must be told when a booking fails are both business decisions; one is inherited and the other is elicited.

## Decision

- **Two kinds of business decision, by who decides and when.** A business standard is decided by the company for every system and is inherited by the slice unchanged. A business process design decision is decided by the scenario's stakeholder for this system and is elicited by the graduate as a requirement.
- **The stack guardrail carries business standards.** Everything decision college-0005 lists is a business standard. Later dives that find a standard (an observability standard, a privacy standard, an accessibility standard) add it there.
- **The scenario carries business process design decisions.** They are stated, accepted, and tested as requirements, and they arrive the way requirements do, often after a miss.
- **"Organization" in earlier dives means business standard.** The security, UX/UI, validation, persistence, and integration dives are read with that substitution; their placements stand. Their text is not rewritten.
- **The graduate's obligation differs by kind.** For a standard: know that it applies here and how the build satisfies it. For a process decision: know to ask, and state the answer before the agent guesses.

## Consequences

- Operability, resilience, performance, privacy, accessibility, and cost each get dived as a question of which parts are a standard and which are process decisions, rather than as a question of whether the business speaks at all.
- The professor sets standards through the guardrail and makes process decisions as the stakeholder (decision college-0002). The same person plays both; the two hats are different decisions and are recorded in different places.
- The overview's vocabulary gains both terms. The cohort-system table in `docs/brainstorm/cs-curriculum-genai-era/README.md` keeps its business-side and developer-side split by role, which is a different axis and is not changed by this record.
- A standard the stakeholder tries to change inside a scenario is a request to the guardrail's owner, not a requirement (decision college-0005's deviation rule, generalized).

## Session

Session e8a087, 2026-09-27, branch `college-curriculum`.
