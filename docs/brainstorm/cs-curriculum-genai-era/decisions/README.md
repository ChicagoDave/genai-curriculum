# Curriculum decision records

Decisions produced by the college-curriculum deep dives (`../expectations/`). They carry the four sections an ADR carries — Context, Decision, Consequences, Session — so the form is familiar, but **they are not ADRs**: they constrain the curriculum, not DevArch, and rule 11 of the DevArch ruleset does not apply to them (decision college-0001).

**Ids and filenames carry the `college-` prefix** (`college-0001-<title>.md`, cited as `college-0001`), never a bare four-digit id. That is what keeps this series out of DevArch's ADR sequence: the ADR locator (`docs/workflow/scripts/adr-locate.sh`) discovers any directory named for decisions that holds a `NNNN-*.md` file, so a bare id here would be read as a second ADR directory and reported as a collision at every `/devarch:finalize`. The prefix rule is ADR-0047 Decision 4; the fourteen issues it closed (#50 to #63) are the record of what the bare ids cost.

Numbering starts at college-0001 and is sequential. A new record cites the records it amends by their prefixed id.
