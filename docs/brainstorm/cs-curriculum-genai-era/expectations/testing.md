# Expectation: Testing

**Status**: IN (self-imposed)
**Time box**: year (proposed 2026-09-24)
**Named discipline**: TDD
**Dived**: 2026-09-27

## What the corporate acceptor holds the graduate to

Stated 2026-09-27: testing is a **self-imposed responsibility**, and every engineer should accept it. The corporation does not hold the graduate to it up front. The graduate holds themselves to it, and then learns two further things in order:

1. **When to push back.** The moment to say that a change ships without its verdict, or that the schedule has no room for the test that would make a requirement a verdict, and to say so to the person who set the schedule.
2. **To accept being ignored, shut down, or changed.** The push-back will sometimes be overruled, and the graduate has to keep the responsibility without the authority: build what was decided, record what was not tested, and not take the overruling as permission to stop imposing the standard on themselves next time.

So the acceptor for this expectation is **the graduate**, and the corporation's role is to be the thing that sometimes says no. That makes testing the first expectation in the roster whose standard survives only if the person carries it, which is a different thing to teach from a standard the organization enforces.

The test-as-verdict guardrail (TDD, brainstorm Q-1) is the technical form: a failing test is the verdict on the agent's code, and the graduate is the one who decided there would be a verdict at all.

### The guardrail never relaxes; scope is what gets declined (2026-09-27)

The harness's test-as-verdict guardrail holds in every slice. The agent's build does not go through without a verdict, in slice 1 or slice 20. So when scope does not change, the student does not ship untested code. What was declined is a **requirement** the student wanted added (say, two receptionists cannot book the same slot), together with the verdict that would encode it. The software ships with verdicts for everything in scope and a recorded gap for the thing that was not. Push-back in this unit is therefore nearly always about the scenario, not about testing as such: the testing unit and the scenarios unit teach two halves of the same accuracy cycle.

## What the graduate must be able to state

- For each in-scope requirement: the **behavior statement** (DOES / WHEN / BECAUSE / REJECTS WHEN) and the **test that makes it a verdict** on the agent's build.
- For each requirement they asked to add and were declined: a **written record of what is out of scope and therefore unverified**, placed where the next slice will find it.
- The push-back itself, addressed to the product owner as a scope request, not to the stakeholder and not as a complaint.

### How push-back is decided: scope (2026-09-27)

The engineer does not negotiate with the stakeholder. The **product owner communicates with the stakeholder, and together they decide scope.** The engineer's push-back ("this needs its verdict before it ships") is a request to expand scope. Either it is listened to and scope expands, or it is not and scope does not change. That is the whole mechanism, and it is the same one a corporation runs. The student experiences being ignored not as a personal shutdown but as a scope decision made above them by people with the authority to make it.

## What proves it in a slice

The slice sequence needs three kinds of moment, and the harness supplies the first while the cohort's role structure supplies the other two:

- **The verdict is required and the student meets it.** Slice 1 onward: the developer harness holds the agent to a failing test as the verdict, and the student authors the test from the behavior statement. This proves the discipline.
- **The student pushes back and scope expands.** A slice where the student names an untested requirement, the product owner takes it to the stakeholder, and the answer is yes. This proves the student knows when to push back.
- **The student pushes back and scope does not change.** A slice where the same request is declined, by the product owner and the professor-as-stakeholder acting on the scope files. What proves the expectation is what the student does next: builds what was decided, records what is untested where the next slice will find it, and imposes the standard on themselves again in the following slice without being asked. A student who stops writing verdicts after being overruled once has failed the unit's actual test.

## Collisions

- **Scenarios / requirements / workflows**: every push-back is a scenario gap surfaced as a missing verdict, so this unit's declined requests are the scenarios unit's next refinement questions.
- **Modularization**: an invariant needs a verdict before it needs a boundary (decision college-0003), so the first test exists in slice 1 while the first bounded context waits for complexity.
- **Scope files** (cohort system markdown, business side): the product owner and stakeholder decide against them, and the student's recorded gaps should be traceable to a scope decision in those files.

## Membership verdict

**Expectation, self-imposed.** The corporation does not hold the graduate to it up front; the graduate does, and the corporation's role is to sometimes say no through a scope decision. TDD is the **discipline**. The **skill** is the self-imposition itself, which is what the graduate carries into a shop whose harness does not enforce a verdict, and which is the part the slice sequence grades through the scope-declined moments.

## Expansion budget

**Year, expanded in every slice.** Expansion is the growing number of verdicts per slice as scenarios accumulate, and the deliberate introduction of scope-declined moments once the discipline is established, so that the student practices keeping the standard without the authority.

## Decisions produced

None of its own. Relies on decision college-0002 (product owner and professor-as-stakeholder roles) and the 2026-09-27 amendment to decision college-0003 (business-side scope files).
