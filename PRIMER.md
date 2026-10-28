# Primer: A CS Curriculum for the GenAI Era

**For**: faculty and staff considering this work, starting with DePaul University
**Author**: David Cornelson
**Status**: a working design, in open brainstorm since 2026-09-24. Nothing here is final. Everything here is argued.

This page is the five-minute version of the repository. It says what the problem is, what the proposed degree produces, how the design is organized, what has been decided, and what is still open. Read it first, then follow the links.

## The problem in three sentences

Most computer science programs teach programming: producing correct code for a stated problem. Corporate software engineering runs on a different layer, design and architecture: deciding what the pieces are, where the boundaries go, how the system changes over time, and what the trade-offs cost. Employers have always absorbed the cost of teaching that second layer on the job, so no price signal ever reached the college, and the gap persisted as a stable equilibrium.

GenAI breaks the equilibrium. The layer the degree teaches best, writing code from a spec, is the layer a model now produces as a first draft. The layer the degree never taught, judging whether what the model produced belongs in the system at all, is the layer the model cannot do. The gap was always the real problem. GenAI just makes it impossible to keep ignoring.

## The one-line vision

**A CS degree whose product is design judgment grounded in logic: graduates who can state what acceptable working software is, to the corporate standard, and hold an AI agent to it.**

The graduate's artifact is no longer code and no longer a reading of code. It is the behavior statement, the test that encodes it as a verdict, and the boundary the agent is held to. Logic is what makes those right, so logic stays a premium. Programming moves to the model, under guardrails. Students still learn to read code, but at the level of classes and interfaces, as a habit of checking the agent's structure against the design, never as the verdict itself.

## The central idea: the expectation set

Software is a set of capabilities and requirements. Code is one way they get realized, and in the GenAI era it is the model's way. What the graduate owns is the set itself and the standard it must meet: **the corporate expectations of acceptable working software**. That standard is the curriculum.

Nineteen candidate expectations were each given the same deep dive and a verdict. Sixteen are expectations proper, two are skills exercised across all of them, and one is a foundation:

| Kind | Members |
|---|---|
| Expectations | Workflows, requirements and scenarios · Modularization (DDD) · Testing (TDD) · Security · Authorization · UX/UI standards · Data validation · Data persistence and change · Integration contracts · Operability · Resilience · Performance and scale · Privacy and compliance · Accessibility · Change management · Cost |
| Skills | Reading code (as eyes on the results) · Option evaluation (weighted matrices) |
| Foundation | Logic |

Each expectation answers the same four questions: what a corporate acceptor actually holds the graduate to, what the graduate must be able to state, what proves it in a slice, and what it collides with. The dives are in `docs/brainstorm/cs-curriculum-genai-era/expectations/`.

## How the degree is shaped

**Time boxes of unequal size, not one course each.** Workflows, requirements and scenarios, DDD, and TDD are full-year units, because they are where requirements come from and the guardrails that hold the agent to them. Security with authorization, and data persistence and change, are semesters. Several others are quarters applied to an existing system. Logic is the year-one foundation. Cost, change management, accessibility, reading code, and option evaluation are exercised in every slice rather than taught in a unit of their own.

**The slice is the unit of work.** A slice is a thin, end-to-end proof of one scenario through every expectation. The first slice is one thing with one invariant. Boundaries are drawn when complexity is found, not in advance. Later slices inherit the earlier ones' decisions and standards.

**Cohorts, not individuals.** Students work in cohorts that cycle roles each slice, including product owner. The professor plays the business stakeholder and is deliberately unforthcoming: an unasked question is the student's miss. Skepticism and push-back are taught by expectation, never prompted.

**The professor owns the stack guardrail.** Approved data stores, transports, an API standard, a design system, observability and resilience standards, a performance budget, an agent budget per slice. The professor also sets the company posture at cohort start (startup or large enterprise), which scales every standard, and picks the scenario's domain so a real regulation applies, whose floor no posture can thin.

**Every decision is a weighted matrix.** Requirements as weighted rows, candidate solutions as columns, a score per cell. The business weights, the developer scores, the professor may override. The record carries the reasoning so the next slice inherits it, not just the conclusion.

**Logic is taught through play.** Year one: board, text, and video games, logic puzzles, geometry proofs, innovation exercises, in a rigorous half that judges and a generative half that proposes.

## What has been decided

Thirteen local decision records, `college-0001` through `college-0013`, each with Context, Decision, Consequences, and the session that produced it. They cover the points above: cohort role cycling, the first-slice rule, the cohort code review, the stack guardrail, the weighted matrix, two kinds of business decision, push-back by expectation, two cost rows, company posture, the regulatory floor, logic as foundation, and the semester units. They live in `docs/brainstorm/cs-curriculum-genai-era/decisions/`.

## What is still open

Four named risks, in `docs/brainstorm/cs-curriculum-genai-era/risks.md`:

- **R-1** Professor skill is the bottleneck. The design asks a lot of the person playing stakeholder and owning the guardrail.
- **R-2** Grading may not be comparable across sections.
- **R-3** Models will drift across a four-year degree.
- **R-4** The assumption that employers do not screen for inner-code fluency is unverified.

Beyond the risks, the brainstorm itself is partway through. Problem, vision, core concepts, and structural patterns are done. User activities, competitive landscape, role assessments, a year-one and a year-four walkthrough, and MVP scope are not. The form of each cohort artifact (plans, decision records, runbooks) is not yet designed.

## Why I am bringing this to DePaul

This is a design, not a program. It needs faculty who teach CS today to stress it: which parts an accredited program could actually adopt, which assumptions about students are wrong, where the professor's load is unrealistic, and what a first pilot slice would look like in a real course. I am offering to volunteer time toward that conversation, and this repository is the shared surface for it.

The most useful first contributions are disagreement with a specific decision record, a candidate expectation I missed, or a scenario that would break the design.

## How to read the repository

1. `README.md` at the root, for the layout.
2. `docs/brainstorm/cs-curriculum-genai-era/overview.md`, for the full argument: problem, vision, vocabulary, sizing table, and diagrams.
3. The roster in `docs/brainstorm/cs-curriculum-genai-era/README.md`, to see how each of the nineteen candidates was judged.
4. The decision records, for why the degree is shaped the way it is.
5. `risks.md`, for what could sink it.

The repository is documentation only. There is no code. The working method, DevArch, is the same kind of guardrail-based harness the curriculum proposes teaching students to use, and its session records in `docs/context/` show the design being made.
