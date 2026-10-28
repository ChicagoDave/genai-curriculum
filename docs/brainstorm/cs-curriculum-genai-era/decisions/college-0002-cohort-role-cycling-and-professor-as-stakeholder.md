# college-0002 — Cohorts cycle roles, including product owner; the professor plays the stakeholder

**Status**: ACCEPTED
**Date**: 2026-09-27

## Context

The scenarios unit does not work without someone on the business side who does not know exactly what they want (brainstorm TE-1, gap G-4, recorded as Q-6). The 2026-09-27 dive on workflows/requirements/scenarios established that the business side of the accuracy cycle can run its own harness, a product owner harness on the same spine as the developer harness, so the question became who runs it.

## Decision

- Students work in **cohorts on a shared system**, and **cycle roles** across slices. The roles include developer (under the developer harness) and **product owner** (under the product owner harness). A student may also take the stakeholder role.
- By default the **professor acts as the stakeholder**, to supply the mercurial nature real stakeholders have: changing their mind, wanting something adjacent to what they said, not knowing until they see it. A peer playing the stakeholder tends to be too cooperative. _Amended 2026-09-27 by [decision college-0008](college-0008-push-back-is-expected-never-prompted.md): the professor as stakeholder is also unforthcoming, expects push-back from the product owner and the team, and never prompts for it._
- The shared-cohort-system versus individual-track question, pending since the 2026-09-24 session, is settled by this decision in favor of the shared cohort system. Role cycling requires it.

## Consequences

- Every student sees both harnesses from the inside over the degree: they refine and build under the developer harness in some slices and author stories under the product owner harness in others. Q-6 is closed.
- The professor's role changes. They are not the acceptor of the software; the business is, played by the cohort's product owner. The professor is the source of the requirements' instability, which is the thing the accuracy cycle is there to absorb.
- Slice design must schedule the role rotation. A slice that adds a scenario is a natural rotation point.
- Open: whether external partners ever play the stakeholder for later slices, and how the professor's stakeholder role is assessed against the student's, since a mercurial stakeholder makes "most of what was asked" harder to judge.

## Session

Session db3880, 2026-09-27, branch `college-curriculum`.
