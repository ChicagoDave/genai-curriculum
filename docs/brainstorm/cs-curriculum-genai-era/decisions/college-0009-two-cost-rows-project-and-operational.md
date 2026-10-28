# college-0009 — Decision records carry two cost rows, project and operational

**Status**: ACCEPTED
**Date**: 2026-09-27

## Context

Decision college-0006 gave every decision record a weighted matrix and observed that "the cost row is where overrides are expected to land most often." Six dives then handed cost a data point each, and the cost dive (2026-09-27) found they were two different things: the resources it takes to build and change a system (people, calendar, and the agent's spend), and what it takes to run it (cloud or on-prem, stores, telemetry, redundancy). A single cost row hides the trade between them, and the trade is the judgment: project cost now against operational cost later, or the reverse.

## Decision

- **Every matrix carries two cost rows**, project and operational, weighted separately.
- **Each traces to its own source.** The project row traces to the business-side delivery timeline and the guardrail's agent budget per slice. The operational row traces to a stated run-cost tolerance or the approved product's price at the stated volume. An untraceable weight is struck, as 0006 already says.
- **The trade is stated.** When a record chooses one lever over the other, it says so and names the number at which the choice would flip.
- **Deferral is a candidate with both rows.** "Not yet" costs the scope it pushes past the timeline and the operational cost of running without it, and it is scored like any other column.
- **The professor's override names its lever.** An override on a cost weight (0006) lands on project or operational, and the record says which.

## Consequences

- Decision college-0006 is amended by pointer: "the cost row" reads as "the two cost rows."
- The agent's spend becomes a line item the cohort meets from the first matrix; the guardrail (decision college-0005) gains an agent budget per slice as its source.
- The product owner and developer roles each estimate one lever and challenge the other (decision college-0008): the product owner states project cost from the timeline, the developer states operational cost from the platform, and each pushes back on the other's number.
- The change management dive (candidate 15) inherits a question: whether the cost of changing what already shipped is stated there or as the project row here.

## Session

Session e8a087, 2026-09-27, branch `college-curriculum`.
