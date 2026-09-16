---
name: market-evidence-capture
description: Record each source consulted during market research as a structured evidence file with provenance, confidence and contradiction tracking. Use throughout any market, competitor, customer or investor research run — every time a source is read and something is learned from it. Capture evidence as you go rather than reconstructing citations at the end.
---

# Evidence capture

Research agents fail at the evidence layer, not the analysis layer. Analysis over a typed,
attributed evidence set is close to mechanical. Analysis over a context window full of
half-remembered pages produces fluent text with no traceable relationship to anything.

Capture as you read. Reconstructing sources afterwards produces citations that point at the
right domain and the wrong claim, which is worse than no citation because it survives review.

Read `conventions.md` at the workspace root for the ID scheme, confidence scale and
anchor rules.

## One file per source

`evidence/E###-<short-slug>.md`, using the template in `assets/evidence-template.md`.
Sequential IDs in the order consulted, never reused, never renumbered.

One file per source, not per claim. A pricing page yielding four facts is one file with
four claims. A claim appearing on two sites is two files, which is the point — that is how
independence gets counted.

## What to record

**The claim, paraphrased.** Your own words, stating what this source establishes. This is
what analysis reads.

**A short anchor.** A few words that let a reader find the passage again. Not an extract.
Long pasted passages are both a copyright problem and a signal you have not understood the
source well enough to state it yourself.

**Provenance.** URL, tier, retrieval date, and whether it required a session.

**Origin, when the source is repeating someone else.** An article citing a company's
funding announcement is evidence of the announcement, not independent confirmation. Record
the origin so the independence count stays honest.

**Confidence**, per `conventions.md`.

**Contradictions.** If this source conflicts with an existing evidence file, note the ID on
both sides. Contradictions are findings, frequently the most valuable ones. Do not resolve
by picking the more recent or the more authoritative-looking source and dropping the other.

## Recording absence

Absence of evidence is evidence, and it needs a file too. If the pricing page has no
enterprise tier, if no job postings mention the role, if a category has no funded entrants
in eighteen months — record it, with what was searched and where. These negative findings
often carry the thesis.

Unanswerable questions go to `evidence/GAPS.md` instead, with what was tried and what would
answer it.

## Discipline

**Do not record what you inferred.** Evidence files hold what the source said. Your
reasoning belongs in `findings.md`, labelled as inference per `conventions.md`. The
boundary between the two is the thing that makes the report auditable, and it erodes
quietly unless it is enforced per file.

**Do not upgrade a claim while capturing it.** A source saying a vendor "has seen strong
adoption in logistics" does not establish a logistics customer count. Record the vague
claim as vague. Precision invented at capture time is invisible by synthesis time.

**Record the date the source describes, not just the date you read it.** A 2023 figure read
today is a 2023 figure.
