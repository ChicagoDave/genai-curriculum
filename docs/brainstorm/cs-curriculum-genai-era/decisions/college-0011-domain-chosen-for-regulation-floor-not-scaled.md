# college-0011 — The professor picks the scenario's domain so a regulation applies; the regulatory floor is not scaled by posture

**Status**: ACCEPTED
**Date**: 2026-09-27

## Context

Every standard in the guardrail so far was the company's to set and, since decision college-0010, the company posture's to scale. The privacy and compliance dive (2026-09-27) found the one obligation that is neither: a regulation reaches the slice through the company's records, but the company did not choose it and cannot thin it. Whether one applies at all depends on the scenario's domain, which nothing yet said the professor chose on purpose. The security dive already established the pattern for an external acceptor: OWASP, cited by the company's records, met by guardrails rather than by reading code.

## Decision

- **The professor picks the scenario's domain so that a regulation applies**, and does so deliberately, as a slice-design decision made before the first scenario alongside the company posture (0010). The running clinic example is under health-privacy law from the first booking.
- **The regulation is the roster's second external acceptor.** _Amended 2026-09-27 by the accessibility dive: the accessibility standard the records cite, met by the design system, is the third; the pattern below applies to it unchanged, with the floor where a law adopts it._ The compliance standard in the guardrail (decision college-0005) cites it the way the security records cite OWASP, and the graduate meets it the same way: know which obligation applies here and which guardrail resolves it.
- **The regulatory floor is not scaled by posture.** Decision college-0010 scales company standards. A startup's compliance standard is as thick as the law, whatever else is thin, and no deviation from it can be requested of the guardrail's owner, because the owner did not write it.
- **The record distinguishes floor from choice.** Every compliance obligation a decision record states is marked as the regulation's or the business's, so a later slice knows which can be renegotiated.

## Consequences

- Decision college-0010 is amended by pointer: its scaling has a floor.
- Slice design now carries two decisions before any scenario: the company posture and the regulated domain. A professor may vary either across cohorts.
- The compliance standard joins the stack guardrail (decision college-0005), with data classification as the first thing in it, since every other rule needs to know what it applies to.
- The cost dive (0009) gains the one row a posture never lightens.
- Open: which regulation, per cohort, following the domain; and whether a second regulated domain is ever worth a later scenario.

## Session

Session e8a087, 2026-09-27, branch `college-curriculum`.
