# Expectation: Integration contracts

**Status**: IN (derived from the business flow across a boundary, in the ubiquitous language; transport is the organization's)
**Time box**: quarter (proposed 2026-09-24)
**Named discipline**: DDD context mapping and published language; consumer-driven contract tests as the verdict
**Dived**: 2026-09-27

Roster candidate 9. The persistence dive handed this one the integration purpose whole (data another context or system needs) and shares event streams with it. The dive's finding, stated 2026-09-27: **integrations evolve with the ubiquitous language and with the examination of business flow between boundaries, whether the boundary is contextual or internal to a monolith.** A contract is not stated up front by the business or the organization. It is found by walking the flow across the boundary and noticing what crosses and in whose words, and it keeps moving as the language does.

## What the corporate acceptor holds the graduate to

Three parts, each with a different owner:

1. **The flow across the boundary.** The scenario says which systems or contexts a workflow crosses; the graduate walks it step by step and finds what actually crosses: which facts, in which direction, triggered by what. Owned by the business through the scenario, found through the accuracy cycle rather than stated in advance.
2. **The language at the boundary.** On each side of a boundary the same word can mean a different thing (an appointment in Scheduling is a slot and a patient; in Billing it is a chargeable visit). The contract is the published language: the terms that cross, defined once for the crossing. This is DDD's context map, and the relationship it names (customer and supplier, conformist, anti-corruption layer, open host, shared kernel) is the graduate's design judgment. Owned by the two sides of the boundary, recorded in the cohort's decision records.
3. **Transport and standard.** REST, gRPC, an event on the stream, a file drop; versioning rules; the API standard the shop enforces. The organization's, fixed in the stack guardrail (decision college-0005) the way the approved stores are. The graduate inherits it and does not pick it per integration.

**Boundaries inside a monolith count.** The discipline does not begin when there is a network. A module boundary inside one deployable has a contract, stated at its interface in the published language, and the same flow walk finds it. This is what makes the expectation exercisable from the first boundary in slice 2 or 3 (decision college-0003), long before the cohort system has a second deployable.

**Contracts evolve.** Because the contract is derived from the language, it changes when the language does. Versioning a contract is part of the expectation, not a change-management afterthought: what the consumer sees while the shape moves, and how long the old shape is honored.

**External systems** the cohort does not own (a payment processor, a public API) are integrated behind an anti-corruption layer. Their language is never allowed to become the context's.

## What the graduate must be able to state

- **The flow walk**, across each boundary the scenario crosses: the steps in business language, the fact that crosses at each, and the direction.
- **The context map relationship** for each boundary, and why: who conforms to whom, where the anti-corruption layer sits, what is shared.
- **The published language**: the terms that cross, defined for the crossing, with the words that mean something different on each side named as such.
- **The contract as an interface**, at the level the reading step reads (decision college-0004): what is exposed, what is not, which direction the dependency points. The contract is literally the interface, so eyes on the results is where it is checked.
- **The transport**, as inherited: which of the shop's approved transports this crossing uses and which standard governs it. Not a per-integration choice.
- **The evolution**: when a term changes, what the contract's next version is, who consumes the old one, and how long it is kept.

## What proves it in a slice

- **The first boundary carries the first contract.** In the slice where the second scenario collides with the first and the cohort draws a boundary (decision college-0003), the slice also states what crosses it, in the published language, at the interface. A boundary with no stated contract is an incomplete boundary.
- **A word that changes meaning.** The professor scripts a scenario in which a term the cohort has been using means something else on the far side of a boundary. The slice passes when the cohort finds it in the flow walk and the published language names both meanings.
- **An internal contract enforced.** Inside the monolith, a module reaches across a boundary in a way the contract does not allow. The reading step catches it; a contract test makes it a verdict.
- **A contract test as the verdict.** A consumer-driven contract test that fails when the provider changes the shape. This is how testing holds the agent to the contract without anyone reading the transport code.
- **An external system behind a layer.** A scenario that integrates a system the cohort does not own. The slice passes when the external language stops at the anti-corruption layer and the context's language is unchanged.
- **A contract that evolves.** A later scenario changes a crossing term. The slice passes when the new version is stated, the old consumers keep working through the change, and the decision record says how long.

## Collisions

- **Modularization**: a contract exists because a boundary does. Decision college-0003's first boundary in slice 2 or 3 is also the first contract; slice 1 has none.
- **Scenarios / requirements / workflows**: the flow walk is scenario work applied across a boundary. What crosses is found by the accuracy cycle, not stated ahead of it.
- **Data persistence and change**: no shared database is the rule this dive enforces; event streams are the transport both dives share; the analytics obligation is an integration with the lake under the company data standard.
- **Testing**: consumer-driven contract tests are the verdict. The provider is held by the consumer's expectation, which is the same shape as a behavior statement.
- **Reading code (candidate 18)**: the contract is the interface, so the reading step is where a leaked type or a wrong-direction dependency across a boundary is found.
- **Security and authorization**: authentication between systems and authorization at a crossing are stated by the organization's records; identity does not cross a boundary unexamined.
- **Resilience (candidate 11)**: what the consumer does when the provider is down is handed to that dive whole.
- **Change management (candidate 15)**: contract versioning stays here as intrinsic; the approval and rollout of a breaking change may move there.
- **Option evaluation (candidate 19)**: the context map relationship, when two are viable, gets a matrix.
- **Stack guardrail (decision college-0005)**: approved transports and the API standard join the guardrail alongside the approved stores. Recorded as an addition below.

## Membership verdict

**Expectation, owned by the two sides of a boundary, derived from the business flow in the ubiquitous language, with transport inherited from the organization.** Context mapping and published language are the **discipline**; contract tests are how it becomes a verdict. The **skill** is hearing the language change at a boundary while walking the flow, and refusing to let one side's words leak into the other.

## Expansion budget

**Quarter, as sized, expanded in some slices.** Enters with the first boundary (slice 2 or 3) as an internal contract; the first external system and the first evolved contract come later, one each. The quarter is where the external and evolving cases concentrate.

## Decisions produced

None new. Decision college-0005's stack guardrail gains **approved transports and the shop's API standard** as an addition, recorded in that file the same day; the guardrail's shape is unchanged.
