# college-0001 — Deep dives per expectation; decisions recorded locally, not as ADRs

**Status**: ACCEPTED
**Date**: 2026-09-27

## Context

The brainstorm's open question Q-3 asks what belongs in the expectation set. Reading the brainstorm on 2026-09-27 showed the question was less "what else" than "which candidates are real, and by what test." Seventeen candidates exist across the Core Concepts and Structural Patterns sections, and no shared test decides whether a candidate is an expectation the corporate acceptor states, a discipline for meeting one, or a skill exercised across several.

Answering that per item produces decisions. The repository's `docs/adrs/` records decisions that constrain future sessions working on DevArch itself. The curriculum is a separate body of work that happens to live in the same repository, and its decisions should not sit among DevArch's.

## Decision

- Each candidate expectation gets a deep dive in `docs/brainstorm/cs-curriculum-genai-era/expectations/<slug>.md`, following the single template in the folder README, so the membership question is asked the same way of every item.
- Decisions the dives produce are recorded in `docs/brainstorm/cs-curriculum-genai-era/decisions/NNNN-<title>.md`, numbered from 0001, with the same four sections an ADR carries (Context, Decision, Consequences, Session) so the form is familiar, but they are not ADRs: they do not go in `docs/adrs/`, they do not carry ADR numbers, and rule 11 of the DevArch ruleset does not apply to them. _Amended 2026-10-10 by [ADR-0047](../../../adrs/0047-decision-records-carry-a-kind.md) Decision 4: the filenames and ids carry the `college-` prefix (`college-NNNN-<title>.md`, cited as `college-NNNN`), never a bare four-digit id, because the ADR locator reads any bare-id file in a directory named for decisions as an ADR and the finalize scans filed the bare ids as fourteen collisions (#50 to #63)._
- The whole body of work stays inside `docs/brainstorm/cs-curriculum-genai-era/`. The brainstorm at `docs/brainstorm/cs-curriculum-genai-era/overview.md` remains the summary surface and links here for detail.

## Consequences

- The expectation set closes by verdict, one dive at a time, instead of by list growth. _Amended 2026-09-27 by [decision college-0012](college-0012-logic-is-a-foundation-taught-through-play.md): the verdict categories are expectation, discipline, skill, and, for logic alone, foundation._ A candidate that fails the membership test is marked OUT or FOLDED INTO another, not deleted, so the reasoning survives.
- Future curriculum sessions look in this folder first. Nothing about the curriculum is expected in `docs/adrs/`, and finding it there would be a defect.
- DevArch's plan tooling ignores this folder. The enforcing gate (`plan-pointer-gate.sh`) fires only on a write to `.current-plan`, which this work never touches; the advisory staleness sweep globs `docs/work/*/plan.md`, and no plan lives here.

## Session

Session db3880, 2026-09-27, branch `college-curriculum`.
