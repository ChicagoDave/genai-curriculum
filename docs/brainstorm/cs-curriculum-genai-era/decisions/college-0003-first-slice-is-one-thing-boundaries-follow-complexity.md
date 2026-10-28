# college-0003 — The first slice is one thing with one invariant; boundaries follow found complexity

**Status**: ACCEPTED
**Date**: 2026-09-27

## Context

The brainstorm's organizing pattern (slice-then-expand, 2026-09-27) describes the first slice as "one scenario, one capability, one bounded context with one invariant, one behavior statement, one test as verdict, one agent build held to it, one acceptance demonstration." The modularization dive on the same day established that DDD is a set of principles, not a solution: the student learns to identify complexity, and when something is not complex, to skip the modularity test and build one thing. A first slice that opens with a bounded context has the student drawing a boundary before any complexity has been found, which is the reflex the unit exists to unlearn.

The same dive established that the graduate's boundary decisions must sit inside the constraints an organization's harness carries, and that a classroom has to manufacture those constraints if the student is to practice reading them.

## Decision

- **The first slice is one thing with one invariant.** The invariant, the behavior statement, the test as verdict, the agent build, and the acceptance demonstration all stay. The bounded context is removed from slice 1. The first boundary appears in slice 2 or 3, when a second scenario collides with the first and the student names the complexity signal that warrants it.
- **Modularity skipped correctly is a passing result.** The slice sequence must include slices where "not complex, build one thing" is the right answer, graded as such, so that boundaries are not drawn to look diligent.
- **The shared cohort system accumulates its own markdown across slices.** Decision records, plans, a profile, and a stack guardrail written in earlier slices, some by other students in other roles, are the constraints later slices inherit. This is how a student practices reading context that is real rather than simulated.
- **The professor sets the tech stack per cohort as a hard guardrail.** A cohort lives in one shop (Postgres, SQL Server, whichever the professor chose) and has no say in it, so platform is a genuine constraint on where boundaries can go.
  - _Superseded 2026-09-27 (persistence dive)_: the guardrail's composition is now defined by decision college-0005: an approved store per kind the shop has, silent on the rest, plus the design system, a stand-in data lake with a company data standard, and optionally the identity source. The bullet and its amendment below are kept for the record.
  - _Amended 2026-09-27 (UX/UI dive)_: the stack guardrail includes the **design system** (tokens, components, controls, UI toolkit). The cohort inherits it as it inherits the database and does not author one. Deviations are requested from the professor as the guardrail's owner, not made. The identity source is not part of the guardrail by default; the professor may fix it when the security semester runs short (security dive).
- **Role cycling includes executor and originator slices.** In some slices the student is handed a plan and executes it; in others they run the brainstorm or proposal and originate the decisions the next slice inherits. This is how ownership level is taught rather than described.

## Consequences

- The brainstorm's "first slice" description and its slice diagram change: slice 1 has no bounded context, and the DDD strand's expansion starts at the first boundary rather than at slice 1. Updated the same day.
- Slice design gains two obligations: at least one slice whose passing answer is "one thing," and a scripted collision in slice 2 or 3 that introduces the first real complexity.
- The cohort's shared system needs its own harness state from slice 1, since slice 2 already inherits it. _Amended 2026-09-27, same session:_ the business side of that state is a set of markdown files for **stakeholder initiatives, product, feature, and delivery timelines**, owned by the product owner and stakeholder roles; the developer side is the decision records, plans, profile, and stack guardrail already named above. Scope decisions (testing dive) are made against these files. Their form is still to be designed.
- The modularization dive's membership verdict follows from this: modularization is an expectation the organization holds conditionally, when complexity is present; DDD is the discipline for meeting it; complexity identification is the skill underneath.

## Session

Session db3880, 2026-09-27, branch `college-curriculum`.
