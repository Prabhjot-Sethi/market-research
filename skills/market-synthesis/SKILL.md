---
name: market-synthesis
description: Turn analysed market-research findings into the canonical report — a markdown document with mermaid diagrams, every claim traced to evidence. Use after analysis in any startup-thesis, market, competitor or investor research run, when producing the deliverable. This report is the single source of truth; all other formats are rendered from it.
---

# Synthesis

Produce `report.md` in the run folder. Everything downstream renders from this file, so it
carries the full argument — nothing important may exist only in a deck.

Read `scope.md` for the question and the null hypothesis, `findings.md` for the analysis,
`conventions.md` for diagram vocabulary and number formatting.

## Structure

Follow `assets/report-template.md`. Order matters: the verdict comes first, because the
reader is deciding something and should not have to assemble the answer from a tour of the
evidence.

## Answer the question that was asked

`scope.md` names a decision and a null hypothesis. The verdict section addresses both
directly. "The evidence does not settle this" is a legitimate verdict when true, and far
more useful than a confident answer the evidence does not support — but it must be
accompanied by what would settle it and what that would cost to find out.

## Claim discipline

Every claim carries evidence IDs, or is labelled as inference with its basis and what would
falsify it. Applied per sentence, not per paragraph: a paragraph with one citation at the
end implies coverage it does not have.

Where the evidence is thin, say so in place rather than in a caveats section at the end.
Caveats at the end are not read; the reader has already formed a view.

## Diagrams

Use the vocabulary in `conventions.md`. Each diagram earns its place by showing a
relationship prose handles badly — flow, dependency, position, sequence. A diagram that
restates a list is decoration and slows the reader down.

Keep to six to ten nodes. Label every edge. Introduce each diagram with one sentence saying
what to look at in it, because a reader who does not know what the diagram is arguing will
skip it.

Verify mermaid syntax before finishing. A broken diagram block will fail the render step
and is invisible in plain markdown.

## What to include that reports usually omit

**What would change the verdict.** Specific, checkable conditions. This is the most useful
section for someone who will revisit the thesis in six months.

**What could not be established.** Pull from `GAPS.md`. A founder needs to know which parts
of the picture are dark, and roughly what each would cost to illuminate.

**The strongest case against.** Assembled properly, not as a token paragraph. If the run
found no serious case against, that itself needs explaining, because one almost always
exists and failing to find it usually means it was not sought.

## Stop after writing

Do not render artifacts. Tell the user the report is ready, give the path, and state the
verdict in a sentence or two plus anything that genuinely surprised you.

The gate exists so weak analysis is caught before it is laundered into a polished deck.
A deck is read as more authoritative than the same claims in markdown, which is exactly why
it must not be produced until the markdown has been read by a human.
