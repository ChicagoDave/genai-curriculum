# college-0008 — The professor expects push-back and never prompts for it

**Status**: ACCEPTED
**Date**: 2026-09-27

## Context

Decision college-0002 has the professor play the stakeholder, supplying the instability real stakeholders have. Decision college-0007 split business decisions into standards the company sets and process design decisions the stakeholder makes, and the operability dive (2026-09-27) found that its process decisions arrive only if the graduate knows to ask: which failures matter, who is told, whether refused input is reviewed. The first draft of that dive had the professor "guiding the cohort toward asking." That would make the professor the source of the question, and a question the professor angled for proves nothing about the student.

The stance the curriculum actually takes: it teaches students to be skeptical and discerning, to ask questions, and to challenge assumptions, including the professor's.

## Decision

- **The professor expects push-back from the product owner and the team, and does not prompt for it or angle for it.** The stakeholder answers what is asked and volunteers nothing the scenario did not need. Silence is not a hint.
- **An unasked question is the student's miss, not the professor's omission.** A scenario that says nothing about failure, cost, timing, or what happens to refused input is complete as the stakeholder stated it. Whether the cohort finds the gap is what the slice grades.
- **Push-back is a graded behavior in every role.** The product owner challenges a stakeholder request that contradicts a recorded decision or a business file; the developer challenges a requirement the build cannot satisfy at the stated cost; the cohort as one challenges a result that passed its guardrails (Q-1 amendment: never trust the output completely).
- **Skepticism is taught by expectation, not by prompting.** The professor demonstrates it, scripts scenarios that reward it, and grades its absence. The professor does not cue it in the moment.

## Consequences

- Decision college-0002 is amended by pointer: the professor's stakeholder role is mercurial and also unforthcoming. The mercurial part supplies instability; the unforthcoming part supplies the gaps the cohort must find.
- Every dive's "slice proof" of the form "a rule stated in passing," "a failure nobody asked about," or "a question asked" is read under this record: the professor sets the gap and waits.
- Slice design gains an obligation alongside the scripted first collision (decision college-0003): at least one gap per slice that only a question would surface.
- Assessment gains a dimension decision college-0002 left open: the student's questions and challenges are recorded and graded alongside the software, which partly answers how a mercurial stakeholder's work is judged.
- The operability dive's "Who answers in the classroom" section is rewritten to match.

## Session

Session e8a087, 2026-09-27, branch `college-curriculum`.
