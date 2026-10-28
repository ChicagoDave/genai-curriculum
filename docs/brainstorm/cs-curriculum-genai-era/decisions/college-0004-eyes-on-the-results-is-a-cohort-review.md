# college-0004: Eyes on the results is a cohort review, with personas dropped

**Date**: 2026-09-27
**Status**: DECIDED (local record, not an ADR; decision college-0001)

## Context

Q-1 was amended on 2026-09-27: reading code is not the verdict on the agent's output, but students must still learn to read it, at the level of classes and interfaces, because the model is non-deterministic and its output is never trusted completely. That left the dive for candidate 18 with the template's first question unanswered: who holds the graduate to it? The cohort's role structure (decision college-0002) assigns every other acceptor to a persona: the business for scenarios, the organization through its harness for modularization, the graduate alone for testing. The corporate form of eyes on the results is code review, which is a second person reading, and the cohort had no second-person role.

## Decision

- **The reading step is a cohort act.** After the agent's build and before the acceptance demonstration, the cohort drops its personas (developer, product owner, stakeholder) and works as one: reading the classes and interfaces the agent produced, comparing them to the design the cohort stated, and validating that the two align.
- **The design is the written record.** The comparison is against the cohort system's developer-side markdown: decision records, plans, profile, stack guardrail, together with the slice's behavior statements and stated boundaries. Not against anyone's memory of what was meant.
- **The result is recorded.** The cohort writes an alignment verdict into the cohort system's markdown: aligned, or misaligned with the structure and the contradicted design statement named. A later slice inherits it.
- **Inner code is out of scope.** Loops, branches, and conditionals are the test's domain. The reading is structural.

## Consequences

- Decision college-0002's role cycling gains an explicit exception: it is suspended for the reading step of every slice and resumes for the acceptance demonstration.
- The cohort system's developer-side markdown gains a new file kind, the alignment verdict, alongside decision records, plans, profile, and stack guardrail. Its form is undesigned, like the others.
- The professor has a lever: a build that passes every test and violates a decision record is the provocation this unit needs, and the professor can arrange one.
- A student who has never written a loop reads structure against a design they authored. Fluency in inner code is not required and is not taught.

## Session

Session 17d860, 2026-09-27, branch `college-curriculum`. Produced by the candidate 18 dive (`expectations/reading-code.md`).
