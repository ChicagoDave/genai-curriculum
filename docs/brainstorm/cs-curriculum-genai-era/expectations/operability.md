# Expectation: Operability

**Status**: IN (two-sided: an observability standard inherited from the guardrail, and process design decisions elicited from the scenario's stakeholder)
**Time box**: quarter (proposed 2026-09-24)
**Named discipline**: SRE practice (alert on what the business feels, runbook per alert, service level stated as a target). Tentative; confirm or replace.
**Dived**: 2026-09-27

Roster candidate 10. The dive opened on the question left by the prior session: does the scenario ever state operability, or is this the first candidate the organization owns entirely? The answer reframed the roster's vocabulary (decision college-0007): everything is a business decision, and the split that matters is between **business standards** the company holds every system to and **business process design decisions** the stakeholder makes about this system. Operability has both, and the graduate's obligation differs by kind.

## What the corporate acceptor holds the graduate to

Two kinds of business decision, stated 2026-09-27:

1. **The observability standard** (a business standard, inherited). What every system the company runs must emit and expose, regardless of what it does: structured logs in the company's shape, the metrics and traces the platform collects, a health endpoint, an alerting channel, and a runbook in the company's form for every alert. The professor owns it in the stack guardrail as the next bullet of decision college-0005, with an approved telemetry stack the way stores and transports are approved. The graduate inherits it and does not author it. A build that passes every scenario test and emits nothing is a failing result, the same shape as the company data standard's verdict on a build that publishes nothing to the lake.
2. **The process design decisions** (elicited). Which failures the business must be told about, because a booking that silently fails is a patient who does not get seen. Who is told, how, and how fast. What the office does while the system is down (the doing is resilience's; the knowing is this dive's). Whether a refused booking is something the receptionist needs to see again. What the system's hours are, and whether the day list being late costs anything. **This is the dive.** Each answer is a requirement, stated in the scenario's language, and it arrives the way requirements do: the stakeholder did not think to say it until the agent built something that fails quietly.

**The rejected-input hand-off from data validation is resolved by the split.** The standard records every rejection as an event; that part is inherited. Whether anyone looks at those rejections again is a process design decision, and the graduate must ask. "Nobody needs to" is a complete answer. An unasked question is the miss.

**The acceptor** is the business in both kinds, which is what decision college-0007 says. What changes between them is who decided and when: the company, once, for every system; or the stakeholder, here, for this one.

## What the graduate must be able to state

- **The operability questions, asked of the stakeholder before the agent builds, and their answers as requirements.** Which failures matter, who is told, how fast, what is reviewed later. A scenario with no failure stated is a scenario the graduate has not finished asking about.
- **Each notification as a behavior statement.** DOES: tells the receptionist a booking failed, with the patient and the reason. WHEN: a booking the scenario accepted could not be completed. BECAUSE: an unbooked patient is the cost the business named. The test asserts on the notification emitted, not on a log line.
- **Which decisions are the standard's and which are the scenario's.** A log shape is the standard's; who reads the alert is the scenario's. Restating a standard as a requirement invents an obligation the stakeholder never made; treating a process decision as "just logging" hides it from the scenario, the same two misplacements the validation dive named for rules.
- **The runbook, in the scenario's language.** For each alert the process decisions produce, what the person told is expected to do. The graduate writes no inner code and does write this: it is a requirement-level artifact about people, and it is the operability equivalent of the wireframe. Its form is the standard's; its content is the scenario's.
- **The service level as the business stated it.** "The day list is up before the office opens" is a requirement with a time in it. It is stated here, and whether it is met is performance's question and whether it survives a failure is resilience's.

## What proves it in a slice

- **A failure nobody asked about.** The professor, as stakeholder, lets the scenario say nothing about failure. The agent builds something that fails quietly on a path the tests do not cover. The slice passes when the student surfaces the process decision (who is told, and what they do) as a requirement, with a behavior statement and a test that fails when the failure is silent. The failure case the professor can provoke: the receptionist learns a booking failed from the patient.
- **The standard inherited without being asked.** A slice whose build satisfies every scenario and exposes no health endpoint, or emits logs in the agent's own shape. The slice passes when the harness fails it against the observability standard and the student recognizes the standard applies without a requirement saying so.
- **The rejected-input question asked.** A slice with a validation rule from the data validation dive. The slice passes when the student asks the stakeholder whether refused bookings are reviewed, whatever the answer. The professor may say no; the question is what is graded.
- **A runbook followed by someone else.** The professor triggers an alert; a cohort member in a different role follows the runbook cold. The slice passes when they can. This is the reading step's cousin: a runbook only its author can follow is the operability form of a constraint buried in inner code.

## Collisions

- **Scenarios / requirements / workflows**: the process decisions are requirements and arrive through the accuracy cycle. Operability's distinctive contribution is the list of questions the graduate must know to ask.
- **Data validation**: rejected input beyond refusal is settled here as above. The standard records; the scenario decides whether anyone reviews. Validation's collision note stands as written.
- **Resilience (candidate 11)**: the boundary is knowing versus surviving. Operability states that the business is told the provider is down and what the office does by hand; resilience states what the system does about it. Both dives should cite this line.
- **Performance and scale (candidate 12)**: a stated service level is a requirement here and a verdict there. Whether "before the office opens" is met is that dive's.
- **Change management (candidate 15)**: deploy and rollback are process decisions about change, not about running. Left to that dive whole; if it declines them, they come back here as the standard's.
- **Privacy and compliance (candidate 13)**: what a log may carry is a business standard, and a log with a patient's details in it violates it. That dive owns the standard; this one owns the fact that logs exist.
- **Security and authorization**: who may read the telemetry, and that the health endpoint reveals nothing an attacker wants, are the security records' business. OWASP's logging and monitoring failures category is the point where the two standards meet.
- **Integration contracts**: a trace that crosses a boundary is the integration made visible. The context map says which systems the trace passes through; the standard says the trace exists.
- **Data persistence and change**: telemetry is not the application's data and does not go in the application's stores. The approved telemetry stack is the guardrail's, not a tenth kind.
- **Testing**: a notification is a DOES line and has a test that asserts on the emitted notification. The standard's obligations are harness checks, not tests, the way OWASP categories that cannot be tested are.
- **Cost (candidate 16)**: every emitted line and retained trace costs money, and how much to observe is a business decision on both sides. The fourth dive in a row to hand cost a data point.
- **Option evaluation (candidate 19)**: how the business is told, when two channels are viable, gets a matrix.
- **Stack guardrail (decision college-0005)**: the observability standard and the approved telemetry stack join the guardrail. Recorded as an addition below.
- **Decision college-0007**: this dive produced it. Every earlier "organization" placement is read as a business standard.

## Membership verdict

**Expectation, two-sided.** The observability standard is a business standard the graduate inherits and must recognize applies. The process design decisions are requirements the graduate elicits and states. SRE practice is the **discipline**, tentatively: alerts on what the business feels rather than on what the machine does, a runbook per alert, a service level stated as a target the business chose. The **skill** is knowing the questions a scenario never volunteers the answers to, and asking them before the first quiet failure.

## Expansion budget

**Quarter, as sized, expanded in some slices.** Slice 1 inherits the standard in full (a health endpoint, logs in the company's shape, one alert channel) and has no process decision, because one thing with one invariant has no failure the stakeholder cares about yet. The first process decision arrives with the first failure the business feels, likely the first integration or the first scenario with a time in it. The runbook arrives with the first alert. The quarter is where those expansions concentrate.

## Who answers in the classroom

**Professor-guided, unprompted** (settled 2026-09-27). The professor, as stakeholder (decision college-0002), holds the answers to the operability questions and gives them when asked. He does not prompt for the questions or angle for them: the scenario says nothing about failure until someone asks, and a cohort that never asks ships a system that fails quietly and is graded on it (decision college-0008). The answers are scripted into slice design the way the first collision is, as gaps the professor sets and waits on. The cohort's product owner role asks, records the answers in the business-side files, and pushes back when an answer contradicts a recorded decision; the team pushes back when an answer cannot be met at the stated cost. The cohort decides how the build satisfies an answer; it does not decide what the business wants to know.

## Open in this dive

- **The named discipline.** SRE practice is proposed. If the corporate acceptor names something else, replace it.

## Decisions produced

- [college-0007 — Two kinds of business decision](../decisions/college-0007-two-kinds-of-business-decision.md): standards the company holds every system to, and process design decisions the scenario's stakeholder makes. Recasts "organization" in earlier dives.
- [college-0008 — The professor expects push-back and never prompts for it](../decisions/college-0008-push-back-is-expected-never-prompted.md): an unasked question is the student's miss; skepticism is taught by expectation, not by cueing. Amends decision college-0002 by pointer.
- Decision college-0005 extended: the observability standard and an approved telemetry stack join the stack guardrail.
