# college-0013 — The two semester units stay semesters after the roster-completion revisit

**Status**: ACCEPTED
**Date**: 2026-09-27

## Context

The 2026-09-24 sizing put security and authorization, and data persistence and change, in one semester each. Both dives (2026-09-27) flagged the semester as tight and queued a revisit for when the roster closed. It closed the same day at 19 of 19, and by then eight later dives had handed security something each (injection as a validation guardrail, authentication at every crossing, telemetry access, fail-closed, approval gates, the minimum-necessary floor, audit, two more external acceptors) and seven had handed persistence a constraint on the kind choice (queue and cache kinds, read models at the growth event, retention across kinds, the de-identified lake, migration timing, the operational cost lever).

The revisit asked whether either had become a year-long strand. The case for security was that every actor after slice 3 brings an authorization rule, which is expansion in every slice. The case against, which won: an authorization rule per actor is a REJECTS WHEN like any requirement, so that growth belongs to the scenarios strand, and nearly everything else the later dives added is recognition of an inherited standard, thin per slice. Persistence's expansion is under the professor's control, one kind per slice, at most.

## Decision

- **Security and authorization stays a semester.** Its expansion concentrates on the identity decision, the OWASP categories as the system grows a surface each applies to, and the cross-role security statement. Recognizing the standards later dives attached to it is a per-slice check, not a unit's worth of content. Authorization's per-actor growth is counted against the scenarios strand.
- **Data persistence and change stays a semester.** The cohort exercises the kinds the professor's scripted scenarios pull in, at most one per slice, and knows the rest. The guardrail's deliberate silence on kinds the shop lacks (decision college-0005) is what makes that a complete education rather than a partial one.
- **The revisit is closed.** Both dives' "flagged" language is retired; re-sizing either needs a new case, not a re-reading of this one.

## Consequences

- The year map and sizing table stand as written: three year-long strands, two semester units, the quarter units, the unbudgeted rows, the foundation.
- Year three's load, TDD expanded in every slice plus two semester units, is the intended difficulty the working framing names, not an overrun.
- The security dive's semester proofs (an authorization scenario, an identity record, an OWASP category made a guardrail, a cross-role statement) and the persistence dive's (one kind per slice, a considered-and-rejected kind, a kind the shop lacks, the inherited analytics obligation) are confirmed as the units' content.

## Session

Session e8a087, 2026-09-27, branch `college-curriculum`.
