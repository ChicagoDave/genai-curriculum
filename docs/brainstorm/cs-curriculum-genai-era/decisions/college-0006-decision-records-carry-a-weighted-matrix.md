# college-0006 — Decision records carry a weighted matrix: the business weights, the developer scores, the professor may override a weight

**Status**: ACCEPTED
**Date**: 2026-09-27

## Context

The curriculum defines design judgment as choosing among realizations and defending the trade-off, and the persistence and security dives both prove their expectations with slices where a choice (store kind, identity source) is "defended." Nothing said what a defense looks like or how a professor grades one. The option evaluation dive (2026-09-27) named the corporate form: a weighted decision matrix with Harvey balls, requirements and scenarios as weighted rows, candidates as columns.

Decision college-0002 cycles the cohort through roles and has the professor play the stakeholder. Decision college-0003 has the cohort system accumulate decision records that later slices inherit, and leaves the record's form undesigned. A matrix filled by one person, or one that inherits without its reasoning, would defeat both.

## Decision

- **Every decision record with more than one real candidate carries a weighted decision matrix** in an Alternatives section: rows are the requirements and scenarios the decision turns on, each weighted; columns are the candidates; cells are Harvey balls; each column has a weighted total.
- **The business weights the rows.** The product owner role sets weights, and each weight traces to a scenario or a business-side file. An untraceable weight is struck.
- **The developer scores the cells.** The developer role fills the balls, and each score has a reason the reading step can check against the candidate.
- **The professor, as stakeholder, may override a weight.** The override needs no scenario, is recorded as the stakeholder's, and re-totals the matrix. Scores are never touched by an override.
- **The matrix informs; the record decides.** A record may choose against the highest total and say why. It may not choose without a matrix or re-score to protect a conclusion.

## Consequences

- The decision record form (decision college-0003, still to be designed) has one section settled: Alternatives, holding the matrix, its weight provenance, and any override.
- Slice design gains one obligation: one slice in which the professor's override flips a result, so the student meets a priority that comes from above the scenario.
- Decision college-0002 stands; this is an instance of its role split, with the professor's stakeholder role given a concrete lever.
- The cost row is where overrides are expected to land most often, which is a data point for the cost dive (candidate 16). _Amended 2026-09-27 by [decision college-0009](college-0009-two-cost-rows-project-and-operational.md): the cost row is two rows, project and operational, each traced to its own source._

## Session

Session 45bafc, 2026-09-27, branch `college-curriculum`.
