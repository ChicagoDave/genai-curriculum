# Expectation: Performance and scale

**Status**: IN (professor-driven: arrives only when the professor scripts a load or a growth event into a scenario, or sets a performance budget in the guardrail)
**Time box**: placed by slice design, not by calendar (was unplaced; settled 2026-09-27)
**Named discipline**: performance engineering as load testing against a stated budget. Tentative; confirm or replace.
**Dived**: 2026-09-27

Roster candidate 12. Arrives with hand-offs from operability (a stated service level, "the day list is up before the office opens," is a requirement there and a verdict here) and resilience (a timeout is a latency budget stated as a failure threshold; that dive owns what happens when it is missed, this one owns whether it is met). Settled 2026-09-27: **entirely professor-driven.** A receptionist's booking system has no scale problem of its own, so this expectation never arrives through the accuracy cycle. It arrives when the professor decides it should.

## What the corporate acceptor holds the graduate to

Two kinds of business decision, both the professor's:

1. **The performance budget** (a business standard, inherited). A response-time budget per kind of call, and a load the platform must sustain, set in the stack guardrail alongside the telemetry stack that measures it. Thin by design: most shops state one or two numbers and a tool. The graduate inherits it and is held to the build meeting it under the standard's load test.
2. **The numbers the scenario states** (process decisions, scripted). How many bookings a day. How fast the day list must appear, in the business's words. What "slow" costs. And, when the professor decides the cohort is ready, the growth event: the practice merges with three others, a hospital group adopts the system, January arrives. **The professor drives all of it.** Under decision college-0008 the cohort asks how many and how fast in early slices and gets small answers, because the scenario is small. The professor, as a mercurial stakeholder (decision college-0002), changes the answers later, on a schedule the cohort does not see.

**The distinctive obligation** runs the other way from every other dive: the graduate is held to **not** building for a scale nobody stated. Decision college-0003's one thing first means slice 1 serves one receptionist. A cohort that ships a cache, a read model, and a queue for ten bookings a day is graded on the cost, the same way an unapproved store is a failing result.

## What the graduate must be able to state

- **The numbers as requirements.** Volume, the response time the business feels, and what missing it costs, in the scenario's language, with the professor's answers recorded on the business side of the cohort system.
- **The budget as a verdict.** The standard's load test run against the real build and the real store, asserting the stated response time under the stated load. A test that measures a stub is scaffolding.
- **What changes at the growth event and what does not.** When the numbers jump, which persistence choices change (a read model for the day list, a cache for the schedule, a stream for bookings), which boundaries hold, and which would have been wasted a slice earlier. Defended in a decision record with a matrix (decision college-0006), cost as a row.
- **Why it was not built sooner.** The record that introduces a scale measure states the number that made it necessary. A measure with no number behind it is the misplacement this dive names.

## What proves it in a slice

- **Small numbers, small system.** The professor answers "one receptionist, forty bookings a day." The slice passes when the build has nothing in it that forty bookings do not need, and the reading step (decision college-0004) finds no structure whose only justification is scale.
- **The budget missed with the scenario met.** A build that passes every scenario test and fails the standard's load test on the day list. The slice passes when the harness fails it against the budget and the cohort states the measure that fixes it, with its number.
- **The growth event, scripted and unannounced.** The professor changes the numbers in a later scenario. The slice passes when the cohort states what changes, defends it in a matrix, and the load test asserts the new number is met on the real path. The failure case the professor can provoke either way: a system that falls over at the new number, or one that was built for it three slices early.

## Collisions

- **Data persistence and change**: read models, caches, and streams are the measures scale calls for, chosen from the approved kinds. The persistence dive owns the kinds; this one owns the number that justifies reaching for one.
- **Operability**: the stated service level is a requirement there; whether it is met is measured here, by the standard's telemetry.
- **Resilience**: a timeout is the boundary between the two: a latency budget until it is missed, a failure afterwards.
- **Modularization**: decision college-0003's boundaries follow found complexity, and a growth event is one of the ways complexity is found. A boundary drawn for scale before the number exists is the same premature split 0003 forbids.
- **Testing**: the load test is a verdict on the real path, and it is the standard's, not the scenario's, until the scenario states a number.
- **Cost (candidate 16)**: every scale measure is a cost row, and the cohort that builds early pays it for nothing. Sixth dive in a row to hand cost a data point; the case for a short, concrete cost dive is now overwhelming.
- **Option evaluation (candidate 19)**: which measure, when the number jumps, gets a matrix.
- **Decision college-0008**: the cohort asks how many; the professor answers small and does not hint at the growth event to come.
- **Stack guardrail (decision college-0005)**: the performance budget and the load tool join the guardrail. Recorded as an addition below.

## Membership verdict

**Expectation, professor-driven.** The budget is a business standard the graduate inherits; the numbers are process decisions the professor scripts and changes. The **discipline** is load testing against a stated budget, tentatively. The **skill** is restraint: building to the number the business stated, asking for the number when none was, and reaching for a scale measure only when a number demands it.

## Expansion budget

**Placed by slice design.** Slice 1 inherits the budget and serves the small number. The growth event is one scripted scenario, late enough that the cohort has boundaries and stores to reconsider, and it expands persistence and modularization more than it expands this dive. Whether a second growth event is worth a slice is the professor's call per cohort.

## Open in this dive

- **The named discipline.** Load testing against a budget is proposed. Replace if the acceptor names something else.

## Decisions produced

None new. Decision college-0005 extended: the performance budget and the load tool join the stack guardrail. The professor-driven arrival is an instance of decisions college-0002 (mercurial stakeholder) and 0008 (unprompted); slice design gains the scripted growth event alongside the scripted first collision (decision college-0003) and the per-slice gap (decision college-0008).
