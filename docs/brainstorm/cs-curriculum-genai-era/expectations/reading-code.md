# Expectation: Reading code (eyes on the results)

**Status**: IN (held by the cohort as one)
**Time box**: every slice (a step from slice 1 onward, not a unit with a budget; confirmed 2026-09-27)
**Named discipline**: — (the corporate form is code review; the curriculum's form is the cohort review, decision college-0004)
**Dived**: 2026-09-27

## What the corporate acceptor holds the graduate to

Origin (2026-09-27): the brainstorm's Q-1 held that reading code is pointless as the verdict on the agent's output, because the guardrails judge. Amended the same day: **students must still learn to read code, as eyes on the results.** LLMs are non-deterministic, and the graduate is taught never to trust the output completely, including output that passed every guardrail.

The corporate form of eyes on the results is **code review**: nothing merges unread by a second person, whatever the tests said. In the curriculum the acceptor is **the cohort acting as one**. At the reading step the cohort drops its personas (developer, product owner, stakeholder; decision college-0002) and works together on one question: does the structure the agent built align with the design the cohort stated?

Two things the acceptor does not hold the graduate to:

- **Inner code.** Loops, branches, and conditionals are where non-determinism produces the defects a test catches. The test is the verdict on behavior; the eyes are not.
- **Writing code.** No code is written to make the reading possible. The graduate reads the agent's structure against something they authored: the boundary, the invariant, the behavior statement, and the decision records the cohort system carries.

## What the graduate must be able to state

The reading is at the level of **classes and interfaces**, and it serves two purposes, each with a statable result:

1. **Bounded context and complexity.** Read the structure to decide whether a boundary is present, whether it was warranted, or whether it was drawn only to look diligent (decision college-0003). The result is a statement: this is one thing, or this is two things and here is the complexity that makes it so.
2. **Design against intent.** Read the structure to verify that what was built matches what the cohort meant, including what was never stated: an unrequested public method, a dependency pointing the wrong way, a type leaking across a boundary. The result is an **alignment verdict**: aligned, or misaligned with the specific structure named and the design statement it contradicts.

Both are read against the cohort system's developer-side markdown (decision records, plans, profile, stack guardrail). The design the code is compared to is a written artifact the cohort owns, not a memory.

## What proves it in a slice

Every slice has a reading step between the agent's build and the acceptance demonstration. The cohort reads the classes and interfaces the agent produced, compares them to the design statements, and records the alignment verdict in the cohort system's markdown. Three moments the slice sequence needs:

- **Aligned, correctly.** The structure matches the design and the cohort says so. This proves the reading is being done.
- **Misaligned, caught.** The agent's build passed its tests and still contains structure nobody asked for. The cohort names it. This is the moment the unit exists for, and the professor can provoke it by letting a build through that satisfies every verdict and violates a decision record.
- **Trusted wrongly.** A misaligned build the cohort passed. Graded as a miss on this expectation, not on testing, because the tests were right and the eyes were not.

## Collisions

- **Modularization**: purpose 1 is modularization's own acceptance step. The reading is where the student decides whether decision college-0003's "not complex, build one thing" was honored or whether a boundary was warranted.
- **Testing**: the two are deliberately disjoint. Tests own behavior and inner code; eyes own structure. A student who reads inner code to check behavior is doing the test's job by hand, which the amendment to Q-1 rules out.
- **Scenarios / requirements / workflows**: an intent the code does not match is sometimes an intent the cohort never wrote down. Those misalignments become the scenarios unit's next refinement questions.
- **Role cycling (decision college-0002)**: the reading step suspends it. The cohort reviews as one, then resumes its personas for the acceptance demonstration.

## Membership verdict

**Expectation, held by the cohort as one** (confirmed 2026-09-27). The corporate acceptor states it as a requirement (nothing merges unread), which is the expectation test. The **discipline** is the cohort review: structure read against written design, with a recorded alignment verdict. The **skill** is the refusal to trust the output completely, which is what the graduate carries into a shop whose review culture is thinner than the cohort's, and which the "trusted wrongly" moments grade.

## Expansion budget

**Every slice, unbudgeted** (confirmed 2026-09-27). Reading is a step of each slice, not a unit that expands. What grows is the size of the structure read and the depth of the design record it is compared to; by year four the cohort is reading a system three years old against decision records written by students in earlier roles.

## Decisions produced

- `decisions/college-0004-eyes-on-the-results-is-a-cohort-review.md`
