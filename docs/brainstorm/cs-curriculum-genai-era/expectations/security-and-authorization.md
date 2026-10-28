# Expectation: Security and authorization

**Status**: IN (two expectations in one unit; confirmed 2026-09-27)
**Time box**: semester (proposed 2026-09-24, together; confirmed at the roster-completion revisit, decision college-0013)
**Named discipline**: OWASP Top Ten (the industry's stated standard; secure coding practices as its application)
**Dived**: 2026-09-27

Roster candidates 4 and 5, dived together. The 2026-09-24 sizing put them in one semester because each collides with several other expectations and needs a system large enough to feel the trade-off. The dive keeps them together: authorization is the part of the standard the scenario states, security is the part the stack and the decision records state, and the graduate has to hold both at once.

## What the corporate acceptor holds the graduate to

Four paths, stated 2026-09-27, each with a different acceptor behind it:

1. **The concepts.** Authentication (who you are), authorization (what you may do), role-based security (the common way of stating the second), IAM policy (the form it takes when the platform enforces it rather than the application). A body of named knowledge the graduate must hold before any acceptor can hold them to anything. This is the first candidate on the roster whose content is vocabulary rather than judgment.
2. **Where identity comes from.** Corporate single sign-on (the users are employees; the organization owns their identity), social sign-on (the users are the public; someone else owns it), custom (the system owns it and inherits every obligation of storing credentials). The scenario decides which applies, because it says who the users are. A design judgment with a trade-off to defend.
3. **OWASP Top Ten and secure coding practices.** The industry's stated standard, and the one a corporate security team holds engineers to by name. It is the closest thing on the roster to an acceptor outside the room.
4. **Security as part of the tech stack in proposals, ADRs, and plans.** Whoever writes a decision record has to know what to say about security, and whoever inherits one has to know what it committed them to. So the product owner and the tech lead need the elements of application security, not only the developer. Tech lead is a **hat the developer wears** when writing the stack side of a decision record, not a fourth persona in the role cycle (settled 2026-09-27).

**Acceptor (confirmed 2026-09-27): the organization, through its recorded decisions, with OWASP as the external standard those decisions cite.** Authorization is stated by the business inside the scenario (who may book, who may cancel, who may see the day's list) and is accepted the way any requirement is. Security is stated in the cohort system's decision records and stack guardrail, cites OWASP, and is accepted by the harness holding the agent to what those records say. The graduate's distinctive skill here is recognizing an obligation they did not author.

## What the graduate must be able to state

- **The concepts of path 1**, in their own words, well enough to write and to read a decision record that uses them.
- **For authorization, in the scenario**: who the actors are, which capabilities each may exercise, and the rejection each unauthorized attempt produces. Stated as requirements and behavior statements (REJECTS WHEN is where authorization lives), then made verdicts by tests.
- **For identity, in a decision record**: which of the three identity sources the system uses, why the scenario's users make that the right one, and what the choice costs. By default the cohort makes this decision itself, with the professor guiding it; the professor may fix it in the stack guardrail when the semester does not have time for the angle (2026-09-27, below).
- **For OWASP, as guardrails**: the graduate does not write inner code, so secure coding cannot be a keyboard habit. Each OWASP category the system is exposed to must be stated as something the harness enforces, a test that makes it a verdict, or a structure the cohort's reading step checks (broken access control is caught at the interface level). "Secure coding practices" in this degree means knowing which category applies here and what guardrail resolves it, which is the brainstorm's original phrasing of the security row: is it needed here, and how is it resolved.
- **In any role**: the security section of a proposal, ADR, or plan. The product owner states what the business needs protected and from whom; the tech lead states how the stack resolves it; the developer holds the agent to it.

## What proves it in a slice

- **An authorization scenario with a rejection.** A slice whose scenario has two actors with different capabilities, a behavior statement whose REJECTS WHEN names the unauthorized attempt, and a test that fails when the agent lets it through. Slice 3 in the current slice diagram.
- **An identity decision record.** A slice where the cohort, in its roles, writes the ADR that picks corporate, social, or custom identity from the scenario's users and defends the cost.
- **An OWASP category made a guardrail.** A slice where a category applies (an injection surface, an access-control boundary) and the cohort states the guardrail that resolves it before the agent builds. The professor can provoke the failure case: a build that passes its behavior tests and is exposed on a category nobody stated.
- **A cross-role security statement.** A slice in which the student in the product owner or tech lead role writes the security section of a plan and a later slice inherits it. This proves path 4 and is graded on the record, not on the code.

## Collisions

- **Scenarios / requirements / workflows**: authorization is derived from the scenario's actors. A missing actor is a missing authorization rule, and it surfaces as a scenario refinement question.
- **Testing**: REJECTS WHEN is where authorization becomes a verdict. Security categories that can be tested are tested; those that cannot are harness rules or reading-step checks, and the dive must say which is which per category.
- **Reading code (candidate 18)**: broken access control and leaked types across boundaries are structural and are caught at the reading step, not by tests.
- **Modularization**: identity and authorization are the classic reason a boundary is warranted (a Scheduling context does not own who the receptionist is). Decision college-0003's "one thing first" means slice 1 has no identity at all, or a trivially fixed one.
- **Role cycling (decision college-0002)**: path 4 introduces the tech lead as the author of the stack side of a decision record. It is a hat the developer wears, not a fourth persona, so decision college-0002 stands unamended.
- **Stack guardrail (decision college-0003)**: the identity source is a cohort decision by default and a professor-fixed guardrail as the fallback. The professor is expected to touch every security angle they can, but the semester may not have room for all of them; fixing the identity source is how an angle is traded for time. Decision college-0003 stands unamended.

## Membership verdict

**Two expectations in one unit** (confirmed 2026-09-27). Authorization is an expectation stated by the business in the scenario; it is a requirement like any other, accepted by test. Security is an expectation stated by the organization in its decision records, citing an external standard; the graduate is held to knowing whether it applies and how it is resolved. OWASP is the **discipline**. The **skill** is recognizing an inherited obligation and turning it into a guardrail without writing the code that would have been the old way of meeting it.

## Expansion budget

**Semester, as sized, expanded in some slices.** Slice 1 has no identity and no second actor. Authorization enters with the second actor (slice 3 in the current diagram), identity when the scenario's users make the source matter, OWASP categories as the system grows a surface each applies to. The semester is where those expansions concentrate, not where they begin.

## Sizing revisit (2026-09-27)

Stays a semester (decision college-0013). Eight later dives attached something to this unit; nearly all of it is recognition of an inherited standard, checked per slice, and authorization's growth by actor is the scenarios strand's expansion, not this unit's. The semester's content is the four proofs above.

## Decisions produced

[college-0013 — The two semester units stay semesters](../decisions/college-0013-semester-units-stay-semesters.md). Otherwise none. Tech lead as a hat, not a persona, leaves decision college-0002 unchanged. The identity source as a cohort decision by default, professor-fixed only when time runs short, leaves decision college-0003 unchanged.
