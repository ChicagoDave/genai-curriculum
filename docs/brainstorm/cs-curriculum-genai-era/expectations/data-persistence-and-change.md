# Expectation: Data persistence and change

**Status**: IN (two axes: purpose says who owns the data, kind says what shape fits and what it costs)
**Time box**: semester (proposed 2026-09-24; confirmed at the roster-completion revisit, decision college-0013)
**Named discipline**: DDD aggregates and context-owned data; CQRS for read models; polyglot persistence for the kind axis
**Dived**: 2026-09-27

Roster candidate 8. The 2026-09-24 sizing gave it a semester because it collides with several other expectations and needs a system large enough to feel the trade-off. The dive found the topic is wider than the sizing assumed: what is architecturally right for a bounded context or a small app depends on company standards, on complexity (other systems, the data lake), and on purpose (operational, analytics, read model or dashboard), and the graduate has to know every kind of store, not the one the shop happens to run.

## What the corporate acceptor holds the graduate to

Two axes, stated 2026-09-27, with company standards running under both.

### Axis 1: purpose, which says who owns the data

| Purpose | What it is | Owner | The graduate's judgment |
|---|---|---|---|
| **Operational** | The bounded context's own data: what must be remembered, its lifecycle, the aggregate shape that lets the invariant be enforced at write time | The context; the platform is the professor's | The one purpose the scenario genuinely drives. Aggregate boundaries and lifecycle are stated here |
| **Read model / dashboard** | Derived, shaped for a question the business asks that the operational shape cannot answer cheaply | Whoever asks the question | Recognizing that it is derived and never the source of truth, and that it is a separate thing rather than a wider table |
| **Analytics / data lake** | What the context publishes into the organization's store, in the shape the company data standard dictates | The organization | Security's fourth path again: an inherited obligation the graduate did not author and must recognize in the decision records. A small app does not make it optional |
| **Integration with other systems** | Data another context or system needs | The boundary between them | DDD's answer is no shared database: published language, events, an anti-corruption layer. Named here as the collision; candidate 9 owns it |

### Axis 2: kind, which says what shape fits and what it costs

Nine kinds, closed 2026-09-27: **relational, document, graph, key/value, cache, text search, blob and object, time series, event streams.** "Text" means full-text search; unstructured content the system stores and never queries is blob.

Choosing the kind is the persistence-level form of the judgment the brainstorm already kept for data structures: the choice and its cost survive, the implementation goes to the agent. The graduate must hold all nine as a body of concepts (what each is good at, what it gives up, what consistency it offers, what it costs to run) before any scenario asks for one, and must exercise the choice one kind at a time as scenarios pull them in.

**Cost is a design factor on this axis, not an afterthought** (stated 2026-09-27). Every kind choice is defended with what it costs to run, to operate, and to change later. A store that fits the shape and is unaffordable is the wrong store. This is the first dive where cost (candidate 16) is exercised rather than named.

### Company standards, under both axes

A shop has an approved store per kind and is usually missing some kinds. The stack guardrail states which product the cohort uses for each kind the shop has and is silent on the rest (decision college-0005). When a scenario wants a kind the shop does not have, the graduate does it in a kind the shop does have and defends the cost, or writes the request to the professor as the guardrail's owner. Same mechanism as a design-system deviation.

### Change

The candidate is named persistence **and change**, and change is a fifth thing rather than an aspect of the four purposes: schema migration, expand-and-contract, versioning the shape while the system runs. Company standards decide most of it (zero downtime or a maintenance window, who approves a migration, how long the old shape is kept). It stays in this dive as named; the collision with change management (candidate 15) is recorded below and that dive may take the organizational half.

## What the graduate must be able to state

- **The purpose of every piece of persisted data**, and therefore its owner. Operational, read model, analytics, or integration. Misplacing one is the recognizable corporate failure: an operational table that grew into a reporting store, a dashboard reading the write model, a context reading another context's tables because the lake was too much trouble.
- **The aggregate and its lifecycle**, for operational data: what is remembered together so the invariant can be enforced in one write, and when it is created, changed, and gone.
- **The kind, with its cost**, for each store the system uses: why this shape, what it gives up, what it costs to run and to change. Stated in a decision record the next slice inherits.
- **The kind the shop does not have**, when a scenario wants one: the trade-off of doing it in an approved kind, or the request to add one, with the cost of each.
- **The considered-and-rejected kind.** "This does not need a graph" is a passing answer, graded as such, the same way "not complex, build one thing" is (decision college-0003).
- **The analytics obligation** the decision records and the company data standard place on the context: what it publishes and in what shape, recognized rather than authored.
- **The change**, when the shape moves: what migrates, in what order, what the old shape's consumers see meanwhile, and which company standard governs it.

## What proves it in a slice

- **A purpose placed correctly.** A scenario asks for the day's list. The slice passes when the student states it as a read model derived from the operational store rather than a wider query on the write side, and the test asserts on the read model after the write.
- **A kind pulled in by a scenario.** The professor scripts scenarios that pull in one kind at a time: patient search pulls in text, the day list a cache, a referral network graph, appointment reminders time series, the lake feed an event stream, scanned referrals blob. The slice passes when the kind is chosen, its cost defended in a decision record, and the agent held to it.
- **A kind considered and rejected.** A scenario that looks like it wants a document store and does not. The passing answer is the approved relational store and a stated reason.
- **A kind the shop lacks.** The scenario wants graph; the guardrail is silent on graph. The slice passes on a defended workaround or a written request, not on an unapproved store appearing in the build.
- **An inherited analytics obligation.** The company data standard in the cohort's records says every context publishes its events to the stand-in lake. The professor can provoke the failure: a build that passes every scenario test and publishes nothing.
- **A change under a standard.** A later scenario changes the aggregate's shape. The slice passes when the migration is stated under the company's change standard and the old consumers keep working through it.

## Collisions

- **Modularization**: the aggregate is the boundary's write-time form, and context-owned data is why a boundary is warranted. Decision college-0003's slice 1 has one thing with one invariant and one operational store.
- **Testing**: DOES lines name the persisted state, and rule 13's "the test queries the store after the call" is the verdict. Read models are tested by writing to the operational side and asserting on the derived side.
- **Integration contracts (candidate 9)**: the integration purpose is handed to that dive whole. Event streams as a kind are shared between the two.
- **Security and authorization**: identity storage is the custom identity source's obligation; data at rest and access control on stores are OWASP categories stated by the organization.
- **Operability (candidate 10)**: every kind added is something to run. Cost as a design factor is where the two meet.
- **Cost (candidate 16)**: exercised here for the first time. That dive decides whether cost is an expectation of its own or a factor every dive already carries.
- **Change management (candidate 15)**: migration stays here as named; the organizational half (who approves, what window) may move there.
- **Privacy and compliance (candidate 13)**: retention and deletion are persistence decisions the organization states. Named here, owned there.
- **Stack guardrail (decision college-0005)**: the guardrail names a product per kind the shop has, a design system, a stand-in lake with a company data standard, and optionally an identity source.

## Membership verdict

**Expectation, stated by the organization for three of the four purposes and by the scenario for the operational one, with the kind axis a body of knowledge the graduate holds and exercises.** DDD aggregates, CQRS, and polyglot persistence are the **disciplines**. The **skill** is placing a need on both axes at once (whose data is it, what shape fits, what it costs) and recognizing which of those answers the organization already decided.

## Expansion budget

**Semester, as sized, expanded in some slices.** _Revisit 2026-09-27: confirmed a semester (decision college-0013); the flag below is retired._ Slice 1 has one operational store in the shop's relational product and nothing else. Each further kind arrives when a scripted scenario pulls it in, at most one kind per slice, some as considered-and-rejected. The read model arrives with the first question the write shape cannot answer; the analytics obligation with the first decision record that names the lake; change with the first shape that moves. Nine kinds plus four purposes plus change is wider than security's semester, which was already flagged as tight. Both are queued for the roster-completion revisit.

## Decisions produced

- `decisions/college-0005-stack-guardrail-composition.md`: the stack guardrail is an approved store per kind the shop has, silent on the rest, plus the design system, a stand-in data lake with a company data standard, and optionally an identity source. Supersedes the guardrail bullet of decision college-0003, which now points here.
