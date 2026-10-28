# Expectation: Workflows / requirements / scenarios

**Status**: IN (the root of the set)
**Time box**: year (minimum one year, confirmed 2026-09-24)
**Named discipline**: —
**Dived**: 2026-09-27

## What the corporate acceptor holds the graduate to

Stated 2026-09-27: **working software that matches the scenario the business described.** It may have defects. If it does most of what was asked, it passes.

Three things fall out of that wording:

- The unit of acceptance is the **scenario**, not the requirement list. The business described a situation; the software is judged against that description.
- The bar is **most**, not all. Corporate acceptance is a threshold judgment, not a checklist, and it tolerates known defects.
- The acceptor is **the business**, in its own words. Whoever authored the scenario is judged by whether the business recognizes its situation in the running software.

### How the standard was met before GenAI (2026-09-27)

The engineer received a **story**, and stories were usually good but rarely perfect. What pushed them to a high accuracy percentage was **backlog refinement**: the team asking questions of the business until the story was buildable. The remaining gaps got filled while coding, by the engineer, and the acceptor's tolerance for "most" absorbed whatever that filling got wrong.

So the before-times mechanism had three parts: a good story, refinement questioning to make it accurate, and a human coder to close the last gaps silently. The curriculum has to say which of those survive when the coder is an agent.

## What the graduate must be able to state

_In progress._ Candidate, from the refinement observation: the graduate's skill is not writing the story, which the business largely does well already. It is **asking the refinement questions** that take a good story to a buildable one, then stating the answers so an agent can build from them with no human left to fill gaps while coding. The story is the business's artifact; the refined scenario is the graduate's.

### The accuracy cycle and the harness (2026-09-27)

With an agent building, whatever refinement misses becomes the agent's guess. Refinement therefore runs as a **cycle**, not a one-shot: refined scenario in, agent build under guardrails, guardrails and acceptance demonstration catch the guesses, each catch becomes a new refinement question, and the scenario gets more accurate on each pass.

What guides that cycle is a **harness**: a set of agents and skills that guide an LLM user to stay in the left, fast lane (stated 2026-09-27). In this unit the harness is what holds the agent to the expectation set and turns each miss into a question instead of a silent defect. This is where the student first meets the concept.

There is one harness per role, on a shared spine. DevArch is the architecture and developer harness; the same spine has been reused for a knowledge worker, a product owner, a business engineering principal, and a graphic designer. Two consequences for this unit:

- The student works under the **developer harness** and should know it is one of a family, so that on day one in a corporation they recognize the harness they inherit as an instance of something they already understand.
- The business side of the accuracy cycle can run its own harness. A story produced under a **product owner harness** arrives already shaped, and the refinement questions become a conversation between two harnesses rather than between a person and a ticket. (Bears on Q-6; see the brainstorm.)

## What proves it in a slice

The **acceptance demonstration** (TE-1, G-3): run the slice against the scenario with the business as the judge. Under the harness, a failed demonstration is not a rejection; it is the cycle's next refinement question. The slice passes when the business recognizes its scenario and the remaining misses are known and tolerated, which is the corporate standard stated above.

## Collisions

With everything, by construction. Every other expectation arrives inside this unit as a refinement question in the accuracy cycle: "who can see the day's list" is authorization arriving as a scenario question; "what happens when two receptionists book the same slot" is data persistence and change arriving the same way. The collision list for this expectation is therefore the whole roster. What matters for the curriculum is which of those questions the student asks unprompted by year four, which is a measure the slice sequence should track.

## Membership verdict

**Expectation, and the root one.** The acceptor states it as a requirement in the plainest form the set has: does the software match what the business described. It passes the membership test on that alone. It is also different in kind from the rest of the roster: security, authorization, persistence, and every other candidate are conditions on a scenario, so they are derived from this expectation rather than peers of it. Recorded as the root of the set, not a peer.

## Expansion budget

**Year, expanded in every slice.** The one-year minimum was confirmed 2026-09-24, and the slice-then-expand pattern places it in the every-slice group. Expansion is the accuracy cycle getting harder: more scenarios on the shared system, a more mercurial stakeholder, and more of the roster arriving as refinement questions the student is expected to ask before the guardrails catch the miss.

## Decisions produced

- `../decisions/college-0002-cohort-role-cycling-and-professor-as-stakeholder.md` — who runs the business side of the accuracy cycle.
