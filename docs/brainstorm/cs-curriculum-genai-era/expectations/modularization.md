# Expectation: Modularization

**Status**: IN (conditional on complexity)
**Time box**: year (proposed 2026-09-24)
**Named discipline**: DDD
**Dived**: 2026-09-27

## What the corporate acceptor holds the graduate to

Stated 2026-09-27: modularization is where the student learns about **context**, meaning purely technical latitude. What can I get done given the environmental constraints? The contexts named (political, platform, management, budget, personnel, scope, ownership) are the sources of those constraints, and the graduate reads them to answer four questions before placing a boundary:

| Question | What it decides |
|---|---|
| If I'm handed a set of work, do I have any say in its implementation, or is that baked into the markdown I'm handed? | Whether the boundary is mine to draw or already drawn in the decision records, plans, and profile the harness carries |
| Will I ever run a brainstorm or a proposal, and under what previously decided guidance? | Which level of ownership I hold: originator of decisions, or executor of someone else's |
| Is the tech stack a hard guardrail? | Whether the platform is fixed (a pure SQL Server shop, a pure Postgres shop) and therefore which boundaries are already placed by it |
| What do the constraints leave open? | The actual design space, which is usually much smaller than the DDD textbook assumes |

The acceptor is the **organization as encoded in its harness**: the markdown files a graduate inherits (decision records, plans, profile, stack guardrails) are the organization's prior decisions made readable. A boundary is accepted when it sits inside those decisions, and a graduate who redraws a boundary the organization already fixed has failed the expectation even if the new boundary is better DDD.

The DDD bounded context is the technical form of a boundary; context in this unit's sense is what tells the graduate how much of the boundary is theirs to decide. The curriculum's claim is that a student who can read the inherited constraints and place boundaries inside them is day-one useful, and one who has only learned the DDD vocabulary will redraw things they were not asked to.

### DDD is a set of principles, not a solution (2026-09-27)

Modularity is not applied by default. The student learns about **complexity**: how to identify it, and when something is not complex, to skip the modularity test and **build one thing**. A boundary is the response to complexity that has been found, not a shape every system starts with. A student who draws bounded contexts around a system that has one thing in it has misread the context as surely as one who redraws a boundary the organization fixed.

## What the graduate must be able to state

Three things, in order, before any boundary exists:

1. **The constraints.** Given this harness's prior decisions (decision records, plans, profile, stack guardrail), what is closed and what is open, and what level of ownership I hold over the open part.
2. **The complexity verdict.** Whether the work in front of me is complex enough to warrant a boundary at all, with the evidence: more than one language for the same thing, more than one owner, more than one rate of change, more than one reason to fail. If none of those hold, the statement is "this is one thing" and the unit's answer is to build it.
3. **The boundary, if warranted.** Where it goes, inside the open part, at the ownership level I hold, and which of the complexity signals it answers.

The DDD vocabulary (bounded context, ubiquitous language, aggregate, invariant) is how item 3 is expressed. Items 1 and 2 are the judgment DDD assumes and does not teach.

## What proves it in a slice

Two proofs, and the slice sequence needs both:

- **A slice where the right answer is one thing.** The student states "not complex" and builds one thing, and the acceptance demonstration passes without a boundary. Modularity skipped correctly is a passing result, and the curriculum has to make that legible or students will draw boundaries to look diligent.
- **A slice where a new scenario introduces complexity.** The boundary appears in response: the student names the signal, places the boundary inside the inherited constraints, and the next scenario lands without the system resisting. The delayed verdict of the organization is simulated by the next slice.

**Consequence for the first slice** (decided, decision college-0003): slice 1 is **one thing with one invariant**, not one bounded context. The first boundary arrives in slice 2 or 3 when the second scenario collides with the first. The invariant and the behavior statement survive; the bounded context is deferred until complexity is found.

_Mechanism (confirmed 2026-09-27, decision college-0003):_ the shared cohort system accumulates its own markdown across slices, so later slices inherit constraints earlier slices decided, some by other students in other roles; the professor sets the tech stack per cohort as a hard guardrail; role cycling includes both executor slices (handed a plan) and originator slices (running the brainstorm or proposal).

## Collisions

- **Scenarios / requirements / workflows**: the second scenario is what introduces the first complexity, so the boundary is always a response to something the scenarios unit produced.
- **Testing**: an invariant is stated before any boundary exists (slice 1), so the test-as-verdict guardrail is in place before the first bounded context and does not depend on it.
- **Data persistence and change**: the professor's stack guardrail fixes the persistence platform, which pre-places some boundaries the student would otherwise draw.
- **Integration contracts, authorization**: each arrives as a complexity signal (more than one owner, more than one consumer) and is a common reason the "not complex" verdict flips.

## Membership verdict

**Expectation, held conditionally.** The organization holds the graduate to modularization only when complexity is present, and holds them equally to *not* modularizing when it is not. DDD is the **discipline** for meeting the expectation once it applies. Complexity identification is the **skill** underneath, exercised across the whole roster, and is the part of this unit the graduate carries into every other expectation.

## Expansion budget

**Year, expanded in every slice, starting at the first boundary.** The year sizing proposed 2026-09-24 stands. Expansion begins in slice 2 or 3 rather than slice 1 (decision college-0003), and each later slice either adds a boundary in response to a new signal or, deliberately, adds none. The unit's expansion is as much about the growing set of inherited constraints the student must read as about the boundaries themselves.

## Decisions produced

- `../decisions/college-0003-first-slice-is-one-thing-boundaries-follow-complexity.md` — slice 1 has no bounded context; inherited markdown, professor-set stack, executor and originator slices.
