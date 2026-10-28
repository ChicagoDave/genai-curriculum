# Expectation: Accessibility

**Status**: IN (privacy's twin: an accessibility standard in the guardrail citing a published standard or a law, met by the design system; a thin process side about the users the scenario forgot)
**Time box**: in every slice through the design system, unbudgeted; expanded only when the scenario names a user the design system's assumptions do not cover (was unplaced; settled 2026-09-27)
**Named discipline**: the published standard the company's records cite (WCAG or the law that adopts it), as the regulation is for privacy and OWASP for security
**Dived**: 2026-09-27

Roster candidate 14. Considered for folding into UX/UI standards and kept separate (agreed 2026-09-27): the UX/UI dive placed the mechanics in the design system and could inherit them without a word, but the reason those mechanics exist is an acceptor outside the company, and recognizing an external obligation is a distinct skill from conforming to a design system. Accessibility is the roster's third external acceptor, after OWASP and the regulation (decision college-0011).

## What the corporate acceptor holds the graduate to

**A published standard or a law, through the company's records, met by the design system.** Depending on the domain the professor chose (decision college-0011) and the company posture (decision college-0010), the acceptor is either a law that applies to the domain or a standard the company's records cite. Either way it reaches the slice as a business standard (decision college-0007) the company did not write and, where it is a law, cannot thin. The company meets it once, in the design system: accessible components, controls, contrast, focus, labelling, keyboard paths, and the toolkit's conformance are the design system's job, which is why the UX/UI dive inherited them silently.

Then the two kinds of business decision:

1. **The accessibility standard** (a business standard, inherited, floored by law where one applies). The conformance level the design system meets and the company's records cite; the rule that every screen is built from the design system's conforming components and nothing else; the checks the harness runs against a built screen. The graduate inherits it and is held to the build satisfying it: a screen assembled from unapproved controls, or a design-system component used in a way that breaks its conformance, is a failing result.
2. **The process design decisions** (elicited, unprompted, thin). Who the scenario's users actually are, named. Whether any of them the business names cannot use a screen the way the design system assumes: a receptionist who works by keyboard, a patient booking by phone with a screen reader, a clinician who needs the day list large on a wall. What the business wants for them beyond the floor. Almost none of it volunteered (decision college-0008), because a stakeholder describes the work, not the people's bodies.

## What the graduate must be able to state

- **That the standard applies here and what meets it.** The sentence a graduate must be able to say on day one: this system is under this standard, the design system conforms to it, and every screen is built from the design system.
- **The scenario's users, named as people, not roles.** Who uses each screen, elicited from the stakeholder, with the question asked whether any of them uses it differently from the way the design system assumes.
- **When a named user needs more than the floor**, as a requirement in the scenario's language: the day list readable from across the room; every booking action reachable without a mouse. Content from the business, form from the design system, the same split as validation messages and the notice.
- **When a screen leaves the design system**, and therefore leaves conformance, and that this is a request to the guardrail's owner rather than a decision the slice may make.
- **Which of the standard's checks are the harness's and which are the reading step's.** Automated conformance checks catch most of it; a keyboard path that exists but makes no sense is structural and is found by eyes, at the reading step (decision college-0004), or by the user the cohort named trying it.

## What proves it in a slice

- **Every screen from the design system.** The harness's conformance check runs on every slice's built screens from slice 1. A screen that fails it, or uses a control outside the design system, is graded on the failure, and the cohort states which standard the failure was against.
- **The users asked about, unprompted.** The stakeholder describes the booking desk and never mentions how the receptionist works. The slice passes when the cohort asks who uses each screen and how, records the answers, and states any requirement above the floor (decision college-0008).
- **A named user tries it.** The professor scripts a user the design system's defaults do not serve well. The slice passes when the requirement was stated before the build and the acceptance demonstration includes that user's path, walked by a cohort member in that role.
- **A request, not a deviation.** A scenario wants a screen the design system cannot build conformantly. The slice passes when the cohort writes the request to the professor as the guardrail's owner and ships within the design system meanwhile, rather than building outside it.

## Collisions

- **UX/UI standards**: the design system is where accessibility is met; this dive supplies the reason it must be, and the acceptor behind it. The UX/UI dive's three layers stand; conformance is a property of the graphic-design layer the professor supplies and a constraint on the app-design layer the cohort assembles.
- **Privacy and compliance**: the twin. Two external acceptors reaching the slice through the guardrail, one floored by law where it applies, and neither requestable away. Decision college-0011's pattern, applied a second time.
- **Security and authorization**: the third and first external acceptors; the company's records cite all three.
- **Scenarios / requirements / workflows**: naming the users as people is scenario work, and the question about how they use the system is the gap a stakeholder never fills unasked.
- **Reading code (candidate 18)**: a keyboard path that exists and makes no sense is structural, found by the reading step or by a named user, not by the conformance check.
- **Data validation**: validation feedback is the design system's form and conforms by construction; the business's message content must still be readable to the user it reaches.
- **Company posture (decision college-0010)**: a company standard's conformance level scales with posture; a law's does not (decision college-0011's floor, applied here).
- **Cost (decision college-0009)**: the design system makes accessibility nearly free at the slice; a requirement above the floor for a named user is a project row the business weights.
- **Change management**: a screen change is absorbed by a named user too, and the process decision about when it lands includes them.
- **Stack guardrail (decision college-0005)**: the accessibility standard, cited from outside and met by the design system, is recorded as an addition below.
- **Decisions college-0007 and 0008**: inherited standard; thin process side asked, unprompted.

## Membership verdict

**Expectation, standard-dominant, privacy's twin.** The accessibility standard is a business standard citing an acceptor outside the company, met once in the design system and inherited by every slice. The process side is the users the scenario forgot. The **discipline** is the published standard the records cite. The **skill** is recognition, that the floor applies and the design system meets it, plus asking who the users are as people, which no stakeholder volunteers.

## Expansion budget

**Every slice, unbudgeted, through the design system.** Slice 1's one screen is built from conforming components and checked. The only expansion is a scripted slice in which a named user needs more than the floor, and it is small. Kept as its own roster row for the acceptor it recognizes, not for the time it takes.

## Open in this dive

- **Which standard or law**, per cohort, following the domain and posture the professor chose. Not fixed here.

## Decisions produced

None new. Decision college-0005 extended: the accessibility standard joins the guardrail, met by the design system. Decision college-0011's external-acceptor pattern is applied a second time and its record is amended by pointer to count three external acceptors: OWASP, the regulation, the accessibility standard.
