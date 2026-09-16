# Conventions

House rules for evidence and diagrams. Read by `market-evidence-capture` and
`market-synthesis`. Edit this rather than the skills when you want a different style.

## Evidence IDs

Sequential within a run: `E001`, `E002`, ... assigned in the order sources are consulted.
Never reused, never renumbered. A file per source at `evidence/E###-<short-slug>.md`.

Claims in `findings.md` and `report.md` reference IDs inline: `[E014]`, or `[E014, E021]`
where several sources support the same claim.

## Confidence scale

Applies to a claim, not to a source.

| Label | Meaning |
|---|---|
| **High** | Two or more independent sources, at least one T0/T1, no contradiction found |
| **Medium** | One T1 source, or several consistent T2/T3 sources |
| **Low** | Single T2/T3 source, or sources agree but all trace to one origin |
| **Contested** | Credible sources disagree; record both sides, do not average them |

Independent means different origin, not different URL. Three articles citing the same
press release are one source.

## Anchors, not extracts

Each evidence file records a short anchor — a phrase of a few words that lets you find the
claim again on the page — plus the agent's own paraphrase of what it means. Do not paste
long passages. The paraphrase is what analysis works from; the anchor is for verification.

## Inference marking

The agent is allowed to reason beyond the evidence, and frequently should. It must label
it. In `findings.md` and `report.md`, an unsourced claim is written as:

> *Inference:* <claim>. Basis: [E007, E012]. Would be falsified by: <what evidence>.

A claim with neither an evidence ID nor an inference label does not belong in the report.

## Diagram vocabulary

Fix the diagram type per job so runs stay comparable. Deviate only when none of these fit.

| Job | Mermaid type |
|---|---|
| Where money flows today, and who intercepts it | `flowchart LR` |
| Competitive position on two chosen axes | `quadrantChart` |
| Investor–company–thesis relationships | `graph LR` |
| How a purchase actually gets made, and by whom | `sequenceDiagram` |
| Market events over time | `timeline` |
| Segment structure and dependencies | `flowchart TD` |

Rules: label every edge in a flow diagram, state both axes explicitly in a quadrant chart
including what high and low mean, and never draw a diagram that restates a table. Six to
ten nodes is the useful range; past that it is decoration.

Avoid `pie`. Proportions belong in a table where the numbers can be read.

## Numbers

Every figure carries its unit, its currency, its period and its evidence ID. `$4.2M ARR
(FY25) [E033]`, not `$4.2M`. Converted figures state the rate and date used. A figure
whose derivation cannot be shown is marked *Inference* or dropped.

## Report tone

Write for someone deciding where to spend the next year. Lead with the answer, then the
reasoning. No hedging that carries no information — "further research may be warranted"
either names the research or comes out.
