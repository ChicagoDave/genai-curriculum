# Expectation: Data validation

**Status**: IN (stated by the business in the scenario; format rules inherited from the design system)
**Time box**: quarter (proposed 2026-09-24)
**Named discipline**: DDD chapter 9, Making Implicit Concepts Explicit (Explicit Constraints and Specification)
**Dived**: 2026-09-27

Roster candidate 7. The brainstorm's original row says the graduate must state "what input is acceptable, and what happens to the rest." The dive found that the first half splits across three layers with different owners, and that the second half is answered by the behavior statement's REJECTS WHEN line rather than by this expectation on its own.

## What the corporate acceptor holds the graduate to

Three layers, stated 2026-09-27, each with a different acceptor:

1. **Format.** Is this a date, is this an email, is it within length, is the field required. Constraints with no domain content. The organization states them through the design system's form controls and validation feedback, which the professor owns in the stack guardrail (decision college-0003, as amended by the UX/UI dive). The graduate inherits them and does not author them.
2. **Business rule.** An appointment must be in the future; a walk-in is not booked more than a day out; a cancellation inside an hour is refused. The business states these in the scenario, usually in passing, and often not until the agent has built something that allows the thing nobody said was forbidden. **This layer is the dive.** The acceptor is the business, through the scenario, and the rule is accepted the way any requirement is.
3. **Invariant.** A slot holds at most one appointment. Already claimed by modularization (the invariant is what the boundary protects) and by testing (the invariant is what the test makes a verdict). The validation dive names the collision and does not own it.

**The message** (confirmed 2026-09-27): **the business owns what the message says; the design system owns how it appears.** A rejection is stated in the scenario's language ("walk-ins are booked for today or tomorrow only") because it is a requirement, and the graduate authors it as one. Placement, tone conventions, and microcopy standards are the design system's app-design layer (UX/UI dive) and are inherited.

**Why chapter 9 is the discipline.** Evans's point is that a rule buried in a setter or a conditional is invisible, and the fix is to pull it out as a named thing in the model. For a graduate who writes no inner code that is the whole skill: the agent will scatter checks through the code if allowed to, and the constraint only exists as a design object if the student named it first. Two of the chapter's three patterns are validation by another name:

- **Explicit Constraints**: the rule is named, in the ubiquitous language, and stated where it can be seen rather than where it happens to be checked.
- **Specification**: a named predicate stated once and used three ways, validation, selection, and building to order. The rule that rejects a bad booking is the same rule that selects today's walk-ins for the day list.

The third pattern, processes as domain objects, is a workflow concern and is left to the scenarios unit.

## What the graduate must be able to state

- **The rule as a named constraint**, in the scenario's language, before the agent builds. Not the check. "Walk-in booking window: today or tomorrow" is a constraint; an `if` on a date difference is the agent's realization of it.
- **The rejection**, as the REJECTS WHEN line of the behavior statement, carrying the business's message. This is where "what happens to the rest" is answered for this expectation: rejected input is refused with a stated message. What is done with it afterwards (logged, held for correction, discarded) is not this expectation's concern; see the operability collision below.
- **Which layer a given rule belongs to**, and therefore who owns it. A required field is the design system's; a booking window is the business's; a one-appointment-per-slot rule is the invariant. Misplacing a business rule as a format rule hides it from the scenario; misplacing a format rule as a business rule invents a requirement nobody stated.
- **When one rule is a specification**, because the scenario uses it to select as well as to reject, so it is stated once and the agent is held to reusing it.
- **The implicit rule they just surfaced.** When acceptance catches a booking the business would never allow, the student states the rule that was always there, adds it to the scenario, and names it. Chapter 9's digging (listen to the language, scrutinize awkwardness, contemplate contradictions) is the vocabulary for what the accuracy cycle already does.

## What proves it in a slice

- **A rule stated in passing.** The professor, as stakeholder, mentions a constraint in conversation and leaves it out of the written scenario. The slice passes when the student surfaces it as a named constraint with a REJECTS WHEN and the business's message, and a test that fails when the agent accepts the input. This is the failure case the professor can provoke: a build that passes every stated test and books a walk-in for next month.
- **A specification used twice.** A slice whose scenario both rejects on a rule and selects on it (the day list shows today's walk-ins). The slice passes when the rule is stated once, the two uses cite it, and the reading step finds one named thing rather than two checks.
- **A format rule left where it belongs.** A slice in which the student is tempted to state a required field or a length limit as a requirement. The passing answer is that the design system already holds it and the scenario says nothing.
- **A constraint at the interface, not in the loop.** At the reading step (decision college-0004) the cohort checks that the named constraint is visible at the level of classes and interfaces. A constraint that exists only as a conditional inside a method is a structural miss no test catches.

## Collisions

- **Scenarios / requirements / workflows**: business rules come from the scenario's language and most of them arrive as refinement questions after a miss. Surfacing one is the accuracy cycle at its smallest.
- **Testing**: REJECTS WHEN is where a validation rule becomes a verdict, the same place the security dive put authorization. Every named constraint has a rejection test.
- **Modularization**: a specification is a domain object and lives inside the boundary that owns the rule. Invariants are the boundary's; constraints are the scenario's; the student has to say which is which. Decision college-0003's slice 1 has one invariant and no business rule.
- **UX/UI standards**: format rules and message form are the design system's. The validation dive adds nothing to what the UX/UI dive placed in the app-design layer.
- **Reading code (candidate 18)**: a constraint buried in inner code is the structural miss the reading step exists to find. Chapter 9 gives the cohort the word for it.
- **Security and authorization**: OWASP's injection category is input validation as a security guardrail. It is the organization's, stated in the decision records, and is not a business rule. The two must not be confused: sanitizing input is a security obligation; refusing a booking is a requirement.
- **Operability**: the fate of rejected input beyond refusal (logging, quarantine, correction queues) is left to the operability dive. If that dive declines it, the question comes back here.

## Membership verdict

**Expectation, stated by the business in the scenario, with the format layer inherited from the organization.** DDD chapter 9 is the **discipline**: explicit constraints and specification are the named way of meeting it without writing the check. The **skill** is hearing an implicit rule in the stakeholder's language and making it explicit before the agent guesses.

## Expansion budget

**Quarter, as sized, expanded in some slices.** Slice 1 has one invariant and whatever format rules the design system supplies; no business rule. The first named constraint arrives when a scenario states one in passing, likely slice 2 or 3 alongside the first collision. Specification reuse arrives with the first selection scenario. The quarter is where those expansions concentrate.

## Decisions produced

None. Message content to the business and message form to the design system fits the UX/UI dive's existing placement, so decision college-0003's stack-guardrail note stands unamended.
