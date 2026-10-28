# Expectation: Resilience

**Status**: IN (two-sided: a resilience standard inherited from the guardrail, and process design decisions about what this system may lose, elicited from the stakeholder when asked)
**Time box**: quarter (proposed 2026-09-24)
**Named discipline**: stability patterns (Nygard, *Release It!*: timeouts, circuit breaker, bulkhead, fail fast, steady state). Tentative; confirm or replace.
**Dived**: 2026-09-27

Roster candidate 11. Arrives with two hand-offs: provider-down behavior, handed whole by the integration contracts dive, and the knowing-versus-surviving line drawn by the operability dive. Dived on the decision college-0007 split, confirmed 2026-09-27: a standard the company sets for every system, and process decisions the stakeholder makes about how much this system may lose.

## What the corporate acceptor holds the graduate to

Two kinds of business decision:

1. **The resilience standard** (a business standard, inherited). What the company requires of every system regardless of what it does: a timeout on every outbound call, retries with a ceiling and backoff, a degraded mode instead of a crash, idempotent handling of anything that may be retried, and fail-closed on anything that guards access. The professor owns it in the stack guardrail as a bullet of decision college-0005. The graduate inherits it and is held to the build satisfying it: an outbound call with no timeout is a failing result the way an unapproved store is.
2. **The process design decisions** (elicited, unprompted). How long the office can run without the system before it costs something. What the receptionist does by hand meanwhile. Whether a booking made during an outage is queued for later or refused now, and with what message. Which downstream failures the patient is allowed to feel, and which the system must hide. How much recent work may be lost if the store is restored from a copy. **This is the dive.** Each answer is a requirement in the scenario's language, and under decision college-0008 none of it is volunteered: the scenario is silent about outages until someone asks, and a cohort that never asks ships a system whose behavior under failure is whatever the agent guessed.

**The line with operability** (both dives cite it): operability states that the business is told the provider is down and what the person told does about it; resilience states what the system does about it. The manual fallback is a process decision stated here because it is the business's answer to "what do we lose"; the alert that triggers it is operability's.

**The line with integration contracts**: the contract says what crosses the boundary and the contract test judges it. Neither says anything about the provider being absent. That behavior is this dive's, per consumer, per dependency, as a stated tolerance.

## What the graduate must be able to state

- **The dependency list with a stated tolerance per entry.** For each thing the system calls or stores into, what the business said it can live without and for how long. A dependency with no stated tolerance is a question not yet asked.
- **The degraded mode as behavior statements.** DOES: holds the booking in a queue and tells the receptionist it is pending. WHEN: the calendar provider does not answer within the standard's timeout. BECAUSE: the business said a patient must never be turned away for a reason they cannot see. REJECTS WHEN: the queue is full, with the business's message. Queue-or-refuse is the process decision; the timeout that triggers it is the standard's.
- **Recovery, as a state the test can assert on.** What happens to queued work when the provider returns: replayed once, no duplicates, the receptionist told which pending bookings landed. Idempotency is the standard's obligation; what "landed" means is the scenario's.
- **The manual fallback, in the scenario's language.** What the office does by hand during the outage and how that work re-enters the system afterwards. A paper appointment book that is never keyed back in is a resilience decision the business made without knowing it.
- **Which decisions are the standard's and which are the scenario's.** A retry ceiling is the standard's; whether to queue is the scenario's. Restating the standard as a requirement and treating queue-or-refuse as "the agent's default" are the two misplacements, the same shape validation and operability named.
- **The message when the system refuses for a reason that is not a rule.** "We cannot book right now, please try in a few minutes" is not a validation rejection and must not read as one. The business owns its content; the design system owns its form.

## What proves it in a slice

- **The provider goes down and nobody asked.** The professor, as stakeholder, says nothing about outages. At the acceptance demonstration the professor takes the dependency down. The slice passes when the cohort had already asked what the business tolerates, stated the degraded mode as a behavior statement, and has a test that fails when the system crashes or silently drops the booking. Under decision college-0008 the professor sets the gap and waits; a cohort that finds out at the demonstration is graded on the miss and asks in the next slice.
- **A timeout the standard required and nobody stated.** A build whose outbound call has no timeout, or retries without a ceiling. The slice passes when the harness fails it against the resilience standard and the cohort recognizes the standard applies with no requirement saying so.
- **Queue versus refuse, defended.** A slice where both are viable. The decision record carries a matrix (decision college-0006): the business weights the rows (a turned-away patient, a double booking after recovery, the receptionist's time), the developer scores the cells, the professor may override a weight. Cost is a row.
- **Recovery asserted on the real path.** The test stops the real dependency and restarts it, then asserts on the store: every queued booking present once, none lost, the pending flag cleared. A stub that pretends to be down is scaffolding; the dependency the slice ships against is the one that goes down in the test.
- **The fallback keyed back in.** A slice in which the office ran on paper for an hour. The slice passes when the scenario states how that work re-enters and the test asserts the re-entered bookings collide correctly with the ones the queue replayed.

## Collisions

- **Operability**: knowing versus surviving, as above. Operability owns the alert and the runbook; resilience owns the degraded mode and the fallback the runbook points at.
- **Integration contracts**: the provider-down hand-off lands here whole. The anti-corruption layer is where the timeout and the degraded mode live, so the boundary that contract tests judge is also the seam resilience is built into.
- **Data persistence and change**: a queue for outage-time bookings is an event stream or a key/value store, chosen from the approved kinds and defended; a cache is a resilience tool as much as a performance one; recovery from a copy is the persistence dive's change concern with a tolerance from this one.
- **Testing**: a degraded mode is a DOES line with a test that asserts on the state after the failure and after recovery, not on the exception. Taking the real dependency down is the real path; a stub of "down" is not the verdict.
- **Modularization**: a bulkhead is a boundary doing its job: a failure inside one context does not take the next down. Decision college-0003's slice 1 has no dependency and therefore nothing to survive; resilience enters with the first boundary.
- **Scenarios / requirements / workflows**: the tolerances are requirements found by asking. Resilience's contribution is the list of questions, per dependency, that a scenario never volunteers.
- **Security and authorization**: fail-closed on anything that guards access is the standard's, and it overrides a scenario that would rather stay open; an authorization service that is down refuses, whatever the business tolerates elsewhere.
- **UX/UI standards**: a degraded mode has a face: the design system's pending, error, and empty states are the app-design layer, inherited; what they say is the business's.
- **Data validation**: a refusal because the system cannot, and a refusal because a rule says no, carry different messages and the reading step should find them as different named things.
- **Performance and scale (candidate 12)**: a timeout is a latency budget stated as a failure threshold. That dive owns whether the budget is met; this one owns what happens when it is not.
- **Change management (candidate 15)**: recovery from a bad deploy is resilience to a change, not to a failure. Left to that dive whole; if it declines, rollback returns here as the standard's.
- **Cost (candidate 16)**: redundancy, queues, and a second region are the most expensive rows the business will ever weight. The fifth dive in a row to hand cost a data point.
- **Option evaluation (candidate 19)**: queue versus refuse, and how much redundancy, get a matrix.
- **Stack guardrail (decision college-0005)**: the resilience standard joins the guardrail. Recorded as an addition below.
- **Decision college-0008**: every "nobody asked" proof above is read under it.

## Membership verdict

**Expectation, two-sided.** The resilience standard is a business standard the graduate inherits and must recognize applies. What this system may lose, for how long, and what the office does meanwhile are process decisions the graduate elicits, unprompted, and states as requirements. Stability patterns are the **discipline**, tentatively: they name what the standard requires and give the agent's realization a vocabulary the reading step can check. The **skill** is asking, per dependency, what the business tolerates before the first outage answers for them.

## Expansion budget

**Quarter, as sized, expanded in some slices.** Slice 1 has one thing, one invariant, and one store: the standard applies trivially and no tolerance is worth asking about. The first tolerance is asked at the first boundary, when there is a provider to lose. Queue-or-refuse arrives with the first scenario that accepts work the system cannot finish alone. Recovery and the fallback arrive with the first scripted outage. The quarter is where those expansions concentrate.

## Open in this dive

- **The named discipline.** Stability patterns, after Nygard, are proposed. Replace if the acceptor names something else.

## Decisions produced

None new. Decision college-0005 extended: the resilience standard (timeouts, retry ceilings, degraded mode, idempotency, fail-closed on access) joins the stack guardrail. The process side is an instance of decision college-0007; the unprompted asking is an instance of decision college-0008.
