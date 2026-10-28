# Curriculum risks

**Raised**: 2026-10-28
**Status**: OPEN, none yet answered by a decision record

Risks to the curriculum as designed, raised in review against the decision records and dives as of this date. Each names the records it bears on and the question a later decision record must settle. A risk closes when a record answers it; the record cites the risk by number.

## R-1: Professor skill is the bottleneck

**Bears on**: college-0002, 0003, 0005, 0008, 0010, 0011

The professor sets the stack guardrail and design system (0003, 0005), sets the company posture (0010), picks a regulated domain (0011), scripts the collisions and the planted gaps (0003, 0008), and plays a mercurial, unforthcoming stakeholder (0002, 0008). Doing all of that well takes the same practitioner judgment the curriculum exists to produce, and it is rare among working engineers, let alone CS faculty. The harness family has a product owner, knowledge worker, business engineering principal, and graphic designer instance, but no professor instance.

**Question**: Does the curriculum ship with a professor harness (scenario scripting, gap planting, guardrail and posture setup) so that it can be taught by faculty without industry DDD experience? If not, the curriculum scales only as far as instructors like its author.

## R-2: Grading is not comparable across sections

**Bears on**: college-0002, 0004, 0008

The professor is both the source of the requirements' instability and a grader, and 0002 leaves open how the professor's stakeholder role is assessed against the student's. Under 0008 the graded behavior is finding gaps the professor planted, so two professors planting different gaps grade against different tests. Results are not comparable across sections, institutions, or years.

**Question**: Is there a shared scenario bank with known planted gaps, so a slice result can be stated as "found n of N" and compared across sections? What is the protocol when a professor improvises a gap outside the bank?

## R-3: Model drift across a four-year degree

**Bears on**: college-0003, 0004, the accuracy cycle (workflows dive)

A cohort spans four years, and agent capability has changed substantially within single years. The same slice will produce different agent output for different cohorts, and for the same cohort if the model changes mid-degree. A guardrail tuned to one generation's failure modes may stop catching the next generation's, and a planted provocation that relied on a predictable agent error (0004's "passes every test and violates a decision record") may stop appearing on its own.

**Question**: Does grading anchor on the students' artifacts (refined scenarios, questions asked, decision records, alignment verdicts) rather than on the build? Are provocations scripted so they do not depend on a given model's errors? Is the model, and its version, recorded per slice?

## R-4: Unverified assumption that inner-code fluency is not screened for

**Bears on**: college-0004, reading-code dive

0004 holds that inner code (loops, branches, conditionals) is the test's domain, that reading is structural, and that inner-code fluency is neither required nor taught. That rests on the corporate acceptor no longer screening graduates for it. No evidence was found either way for 2026 hiring practice, and it is the claim an employer or accreditor is most likely to challenge.

**Question**: What evidence supports it (employer interviews, hiring-loop surveys, acceptor statements in the acceptor's words, as the dives require elsewhere)? If the evidence goes the other way, is inner-code reading added as a skill, or is the gap accepted and stated to employers?
