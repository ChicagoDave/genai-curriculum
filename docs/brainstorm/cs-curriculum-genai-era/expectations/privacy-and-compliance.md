# Expectation: Privacy and compliance

**Status**: IN (standard-dominant: a compliance standard in the guardrail citing a regulation the professor chose the domain to be under; a thin process side about what the business does above the floor)
**Time box**: present from slice 1 as a standard, expanded in a few slices (retention, the lake, a staged breach); quarter-sized expansion (was unplaced; settled 2026-09-27)
**Named discipline**: the regulation itself, as the security dive names OWASP; privacy by design as its application. Tentative on the second half.
**Dived**: 2026-09-27

Roster candidate 13. Arrives with one hand-off, from operability: what a log may carry is this dive's standard. Settled 2026-09-27: **the professor picks the scenario's domain so that a regulation applies** (decision college-0011). A clinic's appointment desk, the running example since TE-1, is under health-privacy law from the first booking, in startup mode or not. The regulation is the thing on this roster that neither the scenario's stakeholder nor the company decided, and the graduate must recognize an obligation that comes from outside both.

## What the corporate acceptor holds the graduate to

**The regulation is the acceptor, through the company's records.** The same shape as security: the company's compliance standard cites the regulation the way the security records cite OWASP, and the harness holds the agent to what the standard says. Two differences from every other standard in the guardrail. First, the company did not choose it and cannot waive it: **the company posture (decision college-0010) scales company standards and does not scale the regulatory floor.** A startup's compliance standard is as thick as the law, whatever else is thin. Second, the graduate cannot request a deviation from the guardrail's owner, because the owner did not write the rule.

Then the two kinds of business decision (decision college-0007):

1. **The compliance standard** (a business standard, inherited, floored by the regulation). Data classification: which fields are personal, which are sensitive, so that every other rule knows what it applies to. Retention and deletion: how long each class may be kept and how it is destroyed. Minimum necessary access: who may see which class, as a floor under authorization. Purpose and notice: what the patient is told and what the data may be used for. Breach notification: who must be told, by when, when data leaks. Logs and telemetry carry no regulated data (operability's hand-off). What leaves the boundary is de-identified or covered by a processor's contract: the lake under the company data standard, an external provider behind the anti-corruption layer. Audit: who saw what, kept as a record.
2. **The process design decisions** (elicited, unprompted, above the floor). How long the business wants to keep a patient's history, within what the regulation allows. Who in the office may see what, stated as authorization by the business and bounded below by minimum necessary. What the notice says, in the business's words. Whether the business chooses to do more than the floor, and what that costs. Thin, but real, and none of it volunteered (decision college-0008).

## What the graduate must be able to state

- **The classification of the scenario's data.** Field by field, which class each is in and therefore which rules reach it. A field nobody classified is the misplacement this dive names: it is regulated whether or not anyone said so.
- **The obligations that apply here and the guardrail that resolves each**, in the form the security dive set for OWASP categories: a harness rule, a test that makes it a verdict, or a structure the reading step checks. "Compliance" in this degree is knowing which obligation applies and what guardrail meets it.
- **Retention as a behavior statement with a state to assert on.** DOES: deletes the appointment history after the stated period, across every store it reached. A test that finds the record gone, in the operational store and the read model and the stream, is the verdict. This is where event streams meet a regulation: a kind that cannot forget is a kind choice the regulation constrains (persistence collision).
- **Access as authorization with a floor.** The business says who may see what; the graduate checks it against minimum necessary and states where the floor lifts the business's answer.
- **The breach path as an operability process decision.** Who is told, by when, and what the runbook says; the regulation supplies the deadline, the business the rest.
- **What may leave the boundary, and in what state.** De-identified into the lake under the data standard; to an external processor only under a contract the integration's decision record cites.
- **The floor and the choice above it.** The record says which obligations are the regulation's and which the business chose, so a later slice knows which can be renegotiated and which cannot.

## What proves it in a slice

- **A patient's name in a log.** A build that passes every scenario test and writes a booking with the patient's name into its logs. The slice passes when the harness fails it against the compliance standard and the cohort states the classification that made it a violation.
- **Retention stated and asserted.** The cohort states a retention period, the business's choice within the floor, and a test asserts the record is gone from every store after it. A record that lingers in a stream or a cache is the failure the professor can provoke.
- **An analytics publish that leaks identity.** A slice that publishes to the lake with a regulated field in the clear. The slice passes when the data standard's de-identification check fails it.
- **The access question asked, unprompted.** The stakeholder says nothing about who in the office may see history. The slice passes when the cohort asks, records the answer as authorization, and checks it against minimum necessary (decision college-0008).
- **A staged breach.** The professor scripts a leak. The slice passes when the cohort follows the breach path it had stated: the regulation's deadline, the business's notification, the runbook. A cohort with no stated path finds out what the deadline is on the day.
- **A field nobody classified.** A later scenario adds a field with regulated content that reads as harmless. The slice passes when classification happens before the agent builds, not after the reading step finds it in a log.

## Collisions

- **Security and authorization**: the regulation and OWASP are the roster's two external acceptors, both reaching the slice through the company's records. Minimum necessary is an authorization floor; audit is a security record. The security dive's four paths gain a fifth voice.
- **Operability**: logs and telemetry carry no regulated data (the hand-off, resolved here as the standard's); breach notification is an alert with a legal deadline and a runbook.
- **Data persistence and change**: retention and deletion reach every kind the data touched, and some kinds resist deletion; the lake receives de-identified data under the company data standard; a migration that moves regulated data is a compliance event.
- **Integration contracts**: an external processor of regulated data needs a contract the decision record cites, and the anti-corruption layer is where de-identification for an outbound crossing lives.
- **Data validation**: classification travels with the field; a format rule for a regulated field is still the design system's, but its class is this dive's.
- **UX/UI standards**: the notice and consent are content from the business in the design system's form, the same split as validation messages.
- **Testing**: deletion is asserted as absent state on the real stores, not as a returned status.
- **Cost (decision college-0009)**: compliance is an operational cost the startup cannot thin and a project cost on every slice that touches a regulated field; the one row a posture never lightens.
- **Change management (decision college-0010)**: a change that adds or moves a regulated field carries a compliance review at every posture. The floor exception to 0010 is recorded in decision college-0011.
- **Company posture (decision college-0010)**: scales company standards; does not scale the regulatory floor.
- **Decisions college-0007 and 0008**: the standard is inherited and cannot be requested away; the thin process side is asked, unprompted.
- **Stack guardrail (decision college-0005)**: the compliance standard joins the guardrail, citing the regulation. Recorded as an addition below.

## Membership verdict

**Expectation, standard-dominant, with an acceptor outside the company.** The compliance standard is a business standard whose floor the company did not set; the thin process side is what the business chooses above it. The regulation is the **discipline** in the sense OWASP is for security, with privacy by design as the way of meeting it without writing the code. The **skill** is classifying data before the agent touches it, and recognizing an obligation that neither the stakeholder nor the company can waive.

## Expansion budget

**Present from slice 1, expanded in a few slices.** Slice 1 has a patient's name in a booking, so classification and the log rule apply on day one. Retention arrives with the first scenario that keeps history. The lake rule arrives with the first analytics publish. The staged breach is one scripted slice. Quarter-sized, concentrated where those land.

## Open in this dive

- **Privacy by design as the named application.** Proposed alongside the regulation itself. Replace if the acceptor names it otherwise.
- **Which regulation.** Follows the professor's domain choice per cohort; the clinic example implies health-privacy law. Not fixed here.

## Decisions produced

- [college-0011 — The professor picks the scenario's domain so a regulation applies; the regulatory floor is not scaled by posture](../decisions/college-0011-domain-chosen-for-regulation-floor-not-scaled.md): the regulation is the roster's second external acceptor, cited by the compliance standard as OWASP is by the security records; decision college-0010's scaling stops at it.
- Decision college-0005 extended: the compliance standard joins the guardrail.
