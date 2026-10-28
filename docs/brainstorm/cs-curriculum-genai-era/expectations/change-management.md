# Expectation: Change management

**Status**: IN (two-sided under decision college-0007, with the standard side scaled by the company posture the professor sets; the slice is the change)
**Time box**: in every slice, at the weight the company posture sets (was unplaced; settled 2026-09-27)
**Named discipline**: continuous delivery at the startup end, formal change control at the enterprise end; the posture picks the point between them. Tentative; confirm or replace.
**Dived**: 2026-09-27

Roster candidate 15. Arrives with three hand-offs: deploy and rollback from operability, breaking-change rollout from integration contracts, and the cost of changing what already shipped from decision college-0009. The dive found that in this curriculum the change is the slice itself, so the expectation is less a topic than the discipline of how each slice lands on the running cohort system. And it found the dimension that sets how heavy that discipline is: **company size and velocity**, stated by the professor (decision college-0010).

## What the corporate acceptor holds the graduate to

**The company posture comes first.** The professor states, as part of the cohort's shop, what kind of company this is. In **startup mode**, speed is the priority: few standards, no approval gates, a change lands the day it is accepted and is rolled back by redeploying the last one. In a **larger company**, standards and deadlines become the priority: a release process, approval gates, change windows, a versioning policy, a change record per release, and a date the business was promised. The graduate is held to knowing which company they are in and what that implies for every change they make. The same slice lands differently in the two, and a graduate who only knows one way is a graduate for one kind of employer.

Then the two kinds of business decision:

1. **The change standard** (a business standard, inherited, scaled by posture). At the startup end: a deploy that is a redeploy away from undone, a contract change that expands before it contracts, and nothing else. At the enterprise end: the release process, who approves, when changes may land, how versions are numbered under the API standard (decision college-0005), what a change record contains, and how a rollback is authorized. The professor owns it in the stack guardrail at the weight the posture sets. Deploy and rollback, handed here by operability, are the standard's mechanics at both ends.
2. **The process design decisions** (elicited, unprompted). Who has to know before this change lands. Whether the receptionist can absorb a new screen mid-week or must wait for Monday. Whether a breaking contract change waits for the consumer to move or forces them by a date. What the business promised and to whom, so a slipped slice is a conversation and not a surprise. Each is a requirement about the change rather than about the software, stated in the scenario's language, and under decision college-0008 the stakeholder does not raise any of it until asked.

**Posture and velocity as a trade.** Speed buys the startup the ability to learn from a shipped slice; standards buy the larger company the ability to ship without breaking what already works for many people. Neither is right; the graduate is held to naming which the company chose and why, and to noticing when a startup's habit is being carried into an enterprise or the reverse.

## What the graduate must be able to state

- **The company posture and what it implies for this change.** In a sentence: which company we are, and therefore what the change standard requires of this slice before it lands.
- **The change record at the posture's weight.** What changes, who is affected, how it is undone, when it lands, and its project cost (decision college-0009). At the startup end this is a paragraph in the slice; at the enterprise end it is a document with approvals. The content is the same; the weight differs.
- **The rollout of a breaking contract change** (from integration contracts). Expand-and-contract under the API standard's versioning rules, with the consumer's move as the gate, or a forced date the stakeholder chose and owns.
- **Who is told, and when they can absorb it.** The process decisions as requirements, with the receptionist's week as a constraint the scenario states.
- **Rollback as a state a test can assert on.** The last slice's behavior restored on the real path, with the store in the state the rollback rule promises. A rollback that has never been run is a hope.
- **The posture's habit carried wrong.** When a slice ships enterprise-style paperwork in a startup or a same-day change in an enterprise, the graduate names the mismatch and the cost of it on the project lever.

## What proves it in a slice

- **The posture stated, the slice landed to it.** The professor sets the company posture at cohort start. Every slice from then on lands by that standard, and the harness fails a slice that skips a gate the posture requires or carries paperwork it does not.
- **A change nobody told the receptionist about.** The stakeholder says nothing about who must know. The slice lands and the receptionist meets a new screen on the busiest morning. The slice passes when the cohort had asked who is told and when, and stated it; otherwise the miss is graded and asked next slice (decision college-0008).
- **A breaking contract change rolled out.** The provider's published language changes. The slice passes when the record shows expand-and-contract under the API standard, the contract test gates the contraction on the consumer's move, and the consumer was told.
- **Rollback exercised on the real path.** The professor asks for the last slice back. The slice passes when the rollback rule the standard states is run against the real deployment and store and a test asserts the prior behavior and state.
- **A posture shift, if the professor scripts it.** The startup the cohort has been shipping to becomes a larger company mid-degree, and the change standard thickens: the next slice needs a record, an approval, and a window. This pairs naturally with the performance dive's growth event; whether it is a fifth scripted obligation is left open below.

## Collisions

- **Integration contracts**: breaking-change rollout lands here; contract versioning stays there as intrinsic. The API standard's versioning rules are the shared ground.
- **Operability**: deploy and rollback land here as the standard's mechanics; the telemetry that says whether a change hurt is operability's, and the alert that triggers a rollback is its runbook.
- **Cost (decision college-0009)**: the project cost of changing what already shipped is stated in the change record. Speed against standards is the two levers again: the startup spends operational risk to save project time, the enterprise the reverse.
- **Performance and scale**: the growth event and a posture shift are the same kind of scripted change and may be one scripted slice.
- **Data persistence and change**: that dive owns the migration's mechanics under the company standard; this one owns when it lands, who approves, and who is told.
- **Security and authorization**: at the enterprise end, approval gates and separation of duties are security controls on the change process itself, and are stated in the security records.
- **UX/UI standards**: a new screen is a change the receptionist absorbs; the design system's consistency is what makes it absorbable, and the process decision says when.
- **Testing**: the contract test and the behavior tests are the gates a change passes; at the enterprise end the standard names them as such.
- **Scenarios / requirements / workflows**: the slice is the change, so every slice exercises this expectation at the posture's weight without a scenario saying so.
- **Stack guardrail (decision college-0005)**: the company posture frames the whole guardrail, not only the change standard: a startup's guardrail is thin everywhere, an enterprise's is thick everywhere. Recorded in decision college-0010.
- **Decisions college-0007 and 0008**: the standard side is inherited at the posture's weight; the process side is asked, unprompted.

## Membership verdict

**Expectation, two-sided, scaled by posture.** The change standard is a business standard whose weight the company posture sets. Who is told, when a change can be absorbed, and whether a consumer is waited for or forced are process decisions the graduate elicits. The **discipline** runs between continuous delivery and formal change control, and the posture picks the point. The **skill** is knowing which company you are in, landing the change the way that company does, and naming the cost when a habit from the other kind is carried in.

## Expansion budget

**Every slice, at the posture's weight.** Slice 1 lands under the posture's standard like every other; in startup mode that is nearly nothing, and the cohort learns that "nearly nothing" is also a standard. The process side arrives with the first change that touches someone outside the cohort's roles, the receptionist. The breaking-change rollout arrives with the first contract. A posture shift, if scripted, is the one large expansion.

## Open in this dive

- **Whether the posture shifts mid-degree.** A startup becoming a larger company is the most realistic thing a cohort could live through, and it pairs with the growth event. Proposed as a fifth scripted obligation; not decided.
- **The named discipline.** The continuous-delivery-to-change-control range is proposed. Replace if the acceptor names it otherwise.

## Decisions produced

- [college-0010 — The professor sets the company posture, size and velocity, and it scales the guardrail](../decisions/college-0010-company-posture-scales-the-guardrail.md): startup mode makes speed the priority and the standards thin; a larger company makes standards and deadlines the priority and the standards thick. Stated at cohort start; frames decision college-0005.
