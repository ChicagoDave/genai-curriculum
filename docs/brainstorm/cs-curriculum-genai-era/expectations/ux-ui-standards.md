# Expectation: UX/UI standards

**Status**: IN (two-sided; confirmed 2026-09-27)
**Time box**: quarter (proposed 2026-09-24)
**Named discipline**: — (the design system is the organization's stated form; no named method)
**Dived**: 2026-09-27

## What the corporate acceptor holds the graduate to

The brainstorm's first-pass row: which CSS, component, and control standards the system must conform to. Expanded 2026-09-27 into three sub-areas, which turn out to be three layers stated by different parties:

1. **Information architecture** (wireframes). What screens exist, what is on each, and in what order people move through them. This comes from the scenario: the workflows say it, and the wireframe is the business's expectation stated visually. Acceptor: **the business**, next to candidate 1.
2. **Graphic design** (colors, shapes, type, spacing). A corporation has a brand and usually a design system. The cohort inherits it: **the professor supplies the design system per cohort as part of the stack guardrail** (decision college-0003, amended 2026-09-27), the way the database is supplied. Acceptor: **the organization**, through the guardrail.
3. **App design** (UI toolkit, navigation, layout templates, and the rest). Where the two meet: the toolkit is fixed by the organization, the navigation and layout are derived from the wireframes. The rest, filled in 2026-09-27: the states every screen has beyond the happy path (empty, loading, error, partial permission); form behavior and how validation feedback reads; responsive behavior across phone and desktop; the words on the controls, since microcopy is design. **Design tokens** bridge layers 2 and 3: color and spacing decisions become values the toolkit consumes, which is how a design system is enforced rather than described.

Two things the acceptor does not hold the graduate to:

- **Producing the styling.** The graduate writes no CSS, as they write no loops. Graphic design under this degree is stating the tokens and standards the agent must conform to and reading the result against them.
- **Authoring the design system.** It is inherited. A cohort has no more say in its design system than in its database.

## What the graduate must be able to state

- **Wireframes for the slice's scenario**: the screens, their contents, and the path through them, traceable to the workflow they realize. This is a requirement artifact, not a drawing exercise; a screen with no workflow behind it is scope nobody asked for.
- **Conformance to the design system**: which tokens, components, and controls the slice uses, stated so the agent can be held to them and so the reading step (candidate 18) can check the result. Deviations are requested from the organization, not made.
- **App design decisions in a decision record**: navigation model, layout template, the state set each screen must handle, form and validation feedback behavior, responsive behavior. Recorded because later slices inherit them and because the professor's design system will not have decided all of them.
- **The words**: the labels, messages, and error text of the slice, as part of the behavior statement rather than left to the agent. An error the user cannot act on is a REJECTS WHEN the student did not finish writing.

## What proves it in a slice

- **A wireframe traced to a workflow.** Every screen in the slice maps to a step or hand-off in the scenario, and nothing is on a screen that the scenario does not need. Proves layer 1.
- **A build read against the design system.** At the reading step, the cohort checks the agent's output against the tokens and components the guardrail names; an off-system color, a hand-rolled control where a toolkit one exists, or a token bypassed is a misalignment. Proves layer 2 without the student styling anything.
- **A non-happy-path state that was stated.** A slice where the empty, error, or partial-permission state of a screen is in the behavior statement and the acceptance demonstration exercises it. The failure case: a build whose happy path is perfect and whose empty state the agent invented. Proves layer 3.
- **A deviation requested, not made.** A slice where the scenario genuinely needs something the design system lacks, and the student takes it to the organization (the professor, as owner of the guardrail) instead of building around it. Same shape as the testing unit's scope push-back.

## Collisions

- **Scenarios / requirements / workflows**: wireframes are derived from workflows; a screen with no workflow is a scenario gap surfacing as UI.
- **Stack guardrail (decision college-0003)**: the design system is now part of what the professor fixes per cohort.
- **Reading code (candidate 18)**: conformance to the design system is checked at the reading step, at the level of tokens and components rather than classes and interfaces. The reading step gains a second kind of structure to read.
- **Data validation (candidate 7)**: validation feedback is where that unit meets this one; which side owns the message is for candidate 7's dive.
- **Authorization (candidate 5)**: the partial-permission state is authorization made visible. What an unauthorized user sees is a UI decision derived from an authorization rule.
- **Accessibility (candidate 14)**: may fold into this unit as a property of the design system and the toolkit, or stand alone as a standard set outside the room (like OWASP). Left to candidate 14's dive.

## Membership verdict

**Expectation, two-sided** (confirmed 2026-09-27). The business states it through wireframes derived from the scenario; the organization states it through the design system in the stack guardrail; app design is where the graduate joins the two and records the decisions neither side made. There is no named discipline; the design system is the form. The **skill** is stating conformance and states for the agent, and reading the result against a standard the student did not author and cannot restyle.

## Expansion budget

**Quarter, as sized, expanded in some slices.** Slice 1 has one screen, the design system applied, and its states stated. Wireframes grow with each scenario; app design decisions accumulate in the record; the quarter is where responsive behavior, navigation models, and the full state set get their concentrated attention on a system that already has many screens.

## Decisions produced

- Amendment to `decisions/college-0003-first-slice-is-one-thing-boundaries-follow-complexity.md`: the professor's stack guardrail includes the design system.
