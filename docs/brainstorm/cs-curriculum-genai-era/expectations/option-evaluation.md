# Expectation: Option evaluation

**Status**: IN (a skill exercised in every slice that carries a decision record)
**Time box**: every decision record, unbudgeted (not a unit of its own; like reading code)
**Named discipline**: weighted decision matrix with Harvey balls
**Dived**: 2026-09-27

Roster candidate 19, surfaced by the persistence dive. The curriculum's definition of design judgment ("choosing among realizations of the expectation set and defending the trade-off") and every slice proof that says "defend the cost" assume the student can compare options in a way the professor can grade. Nothing named how. This dive names it.

## What the corporate acceptor holds the graduate to

A corporation does not accept "we chose X" in a decision record. It accepts the alternatives considered and the reason X won, in a form someone who was not in the room can check. The common corporate form is the **weighted decision matrix**: requirements and scenarios as rows, each with a weight; candidate solutions as columns; a Harvey ball per cell (empty to full, scoring how well that solution meets that row); a weighted total per column. The form is used for vendor selection, architecture options, buy-or-build, and any ADR with a real alternative.

The acceptor is the organization, through the decision record. The graduate is held to producing the matrix whenever a decision record has more than one candidate, and to producing it honestly.

**Who fills what** (confirmed 2026-09-27; decision college-0006):

- **The business weights the rows.** The product owner role sets the weight on each requirement or scenario, because weight is priority and priority is the business's to state. A weight the product owner cannot trace to the scenario or to the business-side markdown is not a weight.
- **The developer scores the cells.** The developer role fills the Harvey balls, because how well a candidate meets a row is a technical judgment. A score the developer cannot explain against the candidate's actual behavior or cost is not a score.
- **The professor may override a weight.** As the stakeholder, the professor can change a weight directly and without a scenario behind it, the way a real executive says "cost matters more than anything this quarter." The override is recorded as the stakeholder's, and the matrix is re-totalled. This is how the student learns that priorities come from above as well as from the scenario.

## What the graduate must be able to state

- **The candidates**, at least two, each real enough to score. One candidate and a strawman is not an evaluation.
- **The rows**, as the requirements and scenarios the decision actually turns on, not every requirement the system has. Choosing the rows is itself a judgment.
- **The weights, with their provenance**: which scenario or business-side file each weight traces to, or which stakeholder override set it.
- **The scores, with their reasons**: why this candidate is a half ball on this row. Cost rows are scored in what the candidate costs to run, operate, and change (persistence dive).
- **The result, and whether it was accepted.** The matrix informs the decision; it does not make it. A record may choose the second-highest total and say why. What it may not do is choose without a matrix, or re-score to preserve a conclusion.
- **Under an override**: the re-totalled result, and what changed. When the professor's override flips the outcome, the student re-scores nothing and re-weights only the overridden row.

## What proves it in a slice

- **A kind choice with a matrix.** A persistence slice where the store kind is chosen from two or more candidates, with weights traced to the scenario and scores the reading step can check against the candidates. The slice passes on the matrix, not on the choice.
- **A considered-and-rejected candidate.** The low-scoring column is how "this does not need a graph" is evidenced rather than asserted.
- **An override that flips the outcome.** The professor raises the cost weight mid-slice. The slice passes when the student re-totals, records the override as the stakeholder's, and the scores are untouched. It fails when the scores drift to keep the old winner.
- **A weight with no provenance.** The professor can provoke this: a matrix in which one weight traces to nothing. The passing answer is to find the scenario it came from or to strike it.
- **An inherited matrix.** A later slice, in a different role, reads the earlier record's matrix and finds the reasoning for a constraint it now lives under. This is the proof that the record carried the reasoning and not just the conclusion.

## Collisions

- **Scenarios / requirements / workflows**: weights are the scenario's priorities made numeric. A row nobody can weight is a scenario nobody has refined.
- **Role cycling (decision college-0002)**: the matrix is filled by two roles and overridden by a third. Decision college-0006 records the split; decision college-0002 stands, with this as an instance of it.
- **Data persistence and change**: the kind axis is the matrix's first customer, and cost is its most-overridden row.
- **Security and authorization**: the identity-source decision record carries a matrix (corporate, social, custom).
- **Modularization**: boundary placement rarely has two candidates worth a matrix; when it does (split now or later), it gets one.
- **Cost (candidate 16)**: cost is a row here, weighted by the business and overridden by the professor. That dive decides whether cost needs more than a row.
- **Logic (foundation)**: the weighted sum is arithmetic; what logic supplies is the refusal to let the arithmetic launder a judgment.
- **Cohort-system markdown**: the decision record form, still undesigned, gains an Alternatives section holding the matrix.

## Membership verdict

**Skill.** No acceptor states "evaluate options" as a requirement; every decision with a real alternative exercises it. The weighted matrix is the **discipline**. The skill underneath is honesty in two places: weights that trace to something and scores that survive a reader who checks them.

## Expansion budget

**Unbudgeted; every decision record with more than one candidate.** It enters at the first such record, likely the first kind choice or the identity source, and is not a unit of its own. The professor's override is introduced once, deliberately, in a slice where it flips the result.

## Decisions produced

- `decisions/college-0006-decision-records-carry-a-weighted-matrix.md`: decision records with more than one candidate carry a weighted Harvey ball matrix; the business weights, the developer scores, the professor may override a weight.
