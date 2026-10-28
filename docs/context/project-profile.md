# Project Profile

**Generated**: 2026-10-28
**Repository**: genai-curriculum

## Domains

- Documentation / Curriculum Design — Markdown-only repository; brainstorm folder `docs/brainstorm/cs-curriculum-genai-era/` with a README index, 18 expectation deep dives, and 13 local decision records
- Decision Records — `decisions/college-NNNN-*.md` (Context, Decision, Consequences, Session); local series with the `college-` prefix, not ADRs (college-0001)

No code domains detected (no manifests, source directories, infrastructure, or data layer).

## Tech Stack

- **Language**: Markdown (prose only)
- **Runtime**: N/A
- **Framework**: DevArch workflow (`.devarch/descriptor.json`, version 9.8.1, capability: base)
- **Data layer**: N/A
- **Messaging**: N/A
- **Test framework**: None
- **Test command**: NONE — docs-only repository: Markdown curriculum content with no code, manifest, or test suite
- **Build tool**: None
- **Package manager**: None
- **CI/CD**: None
- **Monorepo**: No

## Conventions

- **Test location**: N/A
- **Test naming**: N/A
- **Source structure**: `docs/brainstorm/<topic>/` with `expectations/<slug>.md` (one per candidate expectation, fixed deep-dive template) and `decisions/college-NNNN-<title>.md`
- **TypeScript strict mode**: N/A
- **Import style**: N/A
- **Documentation standard**: `always` (descriptor `documentationStandard`)

## Mutation Signatures

No code domains were detected, so there are no mutation patterns to verify.

### Documentation / Curriculum Design
- **Mutation calls**: N/A (file edits to Markdown only)
- **Reporting without mutation**: N/A
- **Test assertions — verify**: N/A; consistency checks instead: the README roster matches `expectations/` files, and decision records are numbered sequentially
- **Test assertions — insufficient**: N/A

## Notes

- Extracted on 2026-10-28 from the DevArch repository; earlier history lives there.
- Decision records here are local (prefix `college-`) and do not govern DevArch (college-0001).
- All files the README references (`overview.md`, `risks.md`, decisions, expectations) are present in the tree.
- `docs/context/` held no profile before this one.
