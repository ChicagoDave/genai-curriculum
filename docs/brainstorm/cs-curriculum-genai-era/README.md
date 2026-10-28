# College CS Curriculum in the GenAI Era — Working Folder

**Owner**: David Cornelson
**Started**: 2026-09-27
**Brainstorm**: `overview.md` beside this file is the summary surface; this folder holds the detail. Extracted from the DevArch repository (`docs/work/college/` and `docs/brainstorm/cs-curriculum-genai-era/`) on 2026-10-28; history before that date lives in that repository.

This folder holds everything the curriculum work produces beyond the brainstorm summary: one deep dive per candidate expectation, and the decision records those dives produce. It is self-contained on purpose. Nothing here is an ADR and nothing here governs the DevArch repository (decision college-0001).

## Layout

| Path | Holds |
|---|---|
| `README.md` | This index: the expectation roster with dive status, and the decision log |
| `expectations/<slug>.md` | One deep dive per candidate expectation, in the template below |
| `decisions/NNNN-<title>.md` | Local decision records, numbered from 0001, four sections: Context, Decision, Consequences, Session |
| `risks.md` | Open risks to the curriculum as designed, each with the records it bears on and the question a decision record must settle |

## Deep dive template

Every expectation gets the same dive, so the dives can be compared and the membership question (is this an expectation, a discipline, or a skill?) is answered the same way each time.

```markdown
# Expectation: <name>

**Status**: CANDIDATE | IN | OUT | FOLDED INTO <other>
**Time box**: year | semester | quarter | foundation | unplaced
**Named discipline**: <e.g. DDD, TDD> or —
**Dived**: <date>

## What the corporate acceptor holds the graduate to
The standard as a corporation actually states it. Concrete, in the acceptor's words.

## What the graduate must be able to state
The requirement-level artifact the graduate authors. Not code, not a reading of code.

## What proves it in a slice
The guardrail or demonstration that judges the agent's output against this expectation.

## Collisions
Which other expectations this one changes or constrains when both are present in a slice.

## Membership verdict
Expectation (the acceptor states it as a requirement), discipline (a named way of meeting an expectation), skill (judgment exercised across expectations), or foundation (what the other three run on; logic alone, decision college-0012). Reasoning in two or three sentences.

## Expansion budget
How far this is expanded after the first slice, and why that size.

## Decisions produced
Links to `decisions/NNNN-*.md`.
```

## Expectation roster

Nineteen candidates as of 2026-09-27: seven named in the brainstorm's Core Concepts, ten more surfaced by its Structural Patterns sizing table, one added when Q-1 was amended the same day, and one surfaced by the persistence dive. Status moves as each dive lands. **Roster closed 2026-09-27: 19 of 19 dived.** Verdicts: sixteen expectations, two skills (18 reading code as a cohort step, 19 option evaluation), one foundation (17 logic). Since decision college-0007, "the business" and "the organization" in the dives read as two kinds of business decision: process design decisions the scenario's stakeholder makes, and standards the company holds every system to.

| # | Candidate | Source | Dive |
|---|---|---|---|
| 1 | Workflows / requirements / scenarios | Core Concepts | [IN, root of the set](expectations/workflows-requirements-scenarios.md) |
| 2 | Modularization (DDD) | Core Concepts | [IN, conditional on complexity](expectations/modularization.md) |
| 3 | Testing (TDD) | Core Concepts | [IN, self-imposed](expectations/testing.md) |
| 4 | Security | Core Concepts | [IN, with 5: stated by the organization's records, citing OWASP](expectations/security-and-authorization.md) |
| 5 | Authorization | Core Concepts | [IN, with 4: stated by the business in the scenario](expectations/security-and-authorization.md) |
| 6 | UX/UI standards | Core Concepts | [IN, two-sided: wireframes from the business, design system from the organization](expectations/ux-ui-standards.md) |
| 7 | Data validation | Core Concepts | [IN, two-sided: business rules from the scenario as explicit constraints (DDD ch. 9), format rules from the design system](expectations/data-validation.md) |
| 8 | Data persistence and change | Structural Patterns | [IN, two axes: purpose says who owns the data, kind (nine kinds) says what fits and what it costs](expectations/data-persistence-and-change.md) |
| 9 | Integration contracts | Structural Patterns | [IN, derived from the business flow across a boundary in the ubiquitous language; monolith-internal boundaries count; transport inherited](expectations/integration-contracts.md) |
| 10 | Operability | Structural Patterns | [IN, two-sided: an observability standard from the guardrail, process design decisions (who is told, what is reviewed) from the scenario, asked unprompted; produced decisions college-0007 and 0008](expectations/operability.md) |
| 11 | Resilience | Structural Patterns | [IN, two-sided: a resilience standard (timeouts, retry ceilings, degraded mode, idempotency, fail-closed) from the guardrail; what this system may lose, queue or refuse, and the manual fallback from the stakeholder, asked unprompted](expectations/resilience.md) |
| 12 | Performance and scale | Structural Patterns (unplaced) | [IN, professor-driven: a thin budget from the guardrail, the numbers and the growth event scripted by the professor as stakeholder; the graduate is held to not building for a scale nobody stated](expectations/performance-and-scale.md) |
| 13 | Privacy and compliance | Structural Patterns (unplaced) | [IN, standard-dominant: a compliance standard citing the regulation the professor chose the domain to be under; a floor no posture thins; a thin process side (retention within the floor, who may see what) asked unprompted; produced decision college-0011](expectations/privacy-and-compliance.md) |
| 14 | Accessibility | Structural Patterns (unplaced) | [IN, privacy's twin: an accessibility standard cited from outside the company and met by the design system; the process side is the users the scenario forgot, asked unprompted; kept separate from UX/UI for the acceptor it recognizes](expectations/accessibility.md) |
| 15 | Change management | Structural Patterns (unplaced) | [IN, the slice is the change: a change standard from the guardrail at the weight the company posture sets (startup: speed; larger company: standards and deadlines), who is told and when they can absorb it from the stakeholder; produced decision college-0010](expectations/change-management.md) |
| 16 | Cost | Structural Patterns (unplaced) | [IN, two levers: project (people, calendar, agent spend) and operational (run cost); each a row in every matrix, traced to its own source; exercised in every decision record, no time box of its own; produced decision college-0009](expectations/cost.md) |
| 17 | Logic | Foundation (Q-4) | [IN, foundation (fourth verdict category): year one, taught through play, board, text, and video games, logic puzzles, geometry proofs, innovation exercises, in a rigorous half and a generative half; produced decision college-0012](expectations/logic.md) |
| 18 | Reading code: classes and interfaces, as eyes on the results | Q-1 amendment | [IN, held by the cohort as one](expectations/reading-code.md) |
| 19 | Option evaluation: weighted requirements and scenarios against candidate solutions, Harvey ball matrix | Persistence dive | [IN, a skill in every decision record: business weights, developer scores, professor may override](expectations/option-evaluation.md) |

## The cohort system's markdown

The shared system carries its own harness state from slice 1, and later slices inherit it (decision college-0003). Two sides, two owners:

| Side | Files | Owned by | Read by the student to |
|---|---|---|---|
| Business | Stakeholder initiatives, product, feature, delivery timelines | Product owner and stakeholder roles | Know what scope is, and take a push-back to the people who decide it |
| Developer | Decision records (with an Alternatives matrix, decision college-0006), plans, profile, stack guardrail (approved store per kind, approved transports and API standard, design system, stand-in lake and company data standard, observability standard and telemetry stack, resilience standard, performance budget, agent budget per slice, change standard, all at the company posture's weight, the compliance standard at the regulation's, and the accessibility standard met by the design system; decisions college-0005, 0010, 0011), runbooks (operability dive), dependency tolerances (resilience dive), alignment verdicts (decision college-0004) | Developer role, professor (stack), the cohort as one (alignment verdicts) | Know what is closed, what is open, and what level of ownership they hold |

Form of each file: not yet designed.

## Risks

Four open as of 2026-10-28, in [`risks.md`](risks.md): R-1 professor skill is the bottleneck, R-2 grading is not comparable across sections, R-3 model drift across a four-year degree, R-4 unverified assumption that inner-code fluency is not screened for.

## Decision log

| # | Title | Date |
|---|---|---|
| 0001 | Deep dives per expectation; decisions recorded locally, not as ADRs (amended by 0012: a fourth verdict category, foundation) | 2026-09-27 |
| 0002 | Cohorts cycle roles, including product owner; the professor plays the stakeholder (amended by 0008: unforthcoming, expects push-back) | 2026-09-27 |
| 0003 | The first slice is one thing with one invariant; boundaries follow found complexity (amended: stack guardrail includes the design system) | 2026-09-27 |
| 0004 | Eyes on the results is a cohort review, with personas dropped | 2026-09-27 |
| 0005 | The stack guardrail is an approved store per kind, plus the design system and a stand-in data lake (supersedes 0003's guardrail bullet; extended by every later dive; framed by 0010) | 2026-09-27 |
| 0006 | Decision records carry a weighted matrix: the business weights, the developer scores, the professor may override a weight (amended by 0009: two cost rows) | 2026-09-27 |
| 0007 | Two kinds of business decision: standards the company holds every system to, and process design decisions the scenario's stakeholder makes (recasts "organization" in earlier dives) | 2026-09-27 |
| 0008 | The professor expects push-back and never prompts for it: an unasked question is the student's miss; skepticism is taught by expectation (amends 0002) | 2026-09-27 |
| 0009 | Decision records carry two cost rows, project and operational, each traced to its own source (amends 0006) | 2026-09-27 |
| 0010 | The professor sets the company posture, size and velocity, at cohort start; it scales every standard in the guardrail (frames 0005; floored by 0011) | 2026-09-27 |
| 0011 | The professor picks the scenario's domain so a regulation applies; the regulation is the second external acceptor and its floor is not scaled by posture | 2026-09-27 |
| 0012 | Logic is a foundation, the fourth verdict category, taught in year one through play: games, puzzles, proofs, innovation exercises (amends 0001) | 2026-09-27 |
| 0013 | The two semester units, security and authorization and data persistence and change, stay semesters after the roster-completion revisit | 2026-09-27 |
