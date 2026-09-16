---
name: market-deliverable-render
description: Render an approved market-research report into slides, spreadsheets, documents and PDFs. Use only after report.md exists and the user has reviewed it and asked for artifacts. This step transforms the report and never adds analysis, findings or numbers that are not already in it.
---

# Deliverable render

Reads `report.md` and `evidence/`. Writes to `out/`. Derives nothing.

## The rule

No new analysis, no new claims, no new numbers. Not a rounded figure, not a tightened
headline that sharpens a hedged claim, not a slide bullet that states more confidently what
the report stated carefully.

This matters because the deck is what gets circulated and the report is what was reviewed.
Any divergence means the reviewed artifact and the circulated one disagree, and nobody will
know which is right. Compression is allowed; the compression must not change a claim's
strength.

If the report is missing something a deliverable needs, do not fill the gap. Say what is
missing and offer to return to synthesis.

## Formats

| Format | Carries | Note |
|---|---|---|
| Slides | Verdict, one slide per section, case against, gaps | 10–12 slides. The verdict is slide one, not a build-up to it |
| Spreadsheet | Competitor matrix, investor shortlist, evidence index, sizing arithmetic | Build from `evidence/`, not by parsing markdown tables — round-tripping loses typing |
| Document | The full report, formatted | Closest to a straight transform |
| PDF | Usually from the document | Confirm which source the user wants |

Use the built-in `pptx`, `xlsx`, `docx` and `pdf` skills. Read each skill before writing.

## Diagrams

Mermaid is the source of truth in `report.md`. Slides and PDF need images.

Render with `mmdc` (mermaid-cli) to SVG where the target supports it, PNG otherwise. Verify
the tool is present before relying on it; it needs a headless browser and is the most
fragile part of this pipeline.

If rendering fails, do not silently drop the diagram. Rebuild the two or three diagrams that
carry argument as native shapes in the target format, and tell the user which were rebuilt
and which were omitted. A deck missing a diagram the report relies on misrepresents the
report.

## Naming

`out/<slug>-<artifact>-<YYYY-MM-DD>.<ext>`. Dated because these get emailed and versions
proliferate.

## Cross-check before presenting

1. Every number in every artifact appears in `report.md` with the same unit, period and
   precision
2. Every claim's hedging survived compression — a "Medium confidence" finding is not stated
   flatly on a slide
3. Diagrams rendered, or omissions reported
4. The gaps section survived into the deck; it is the first thing dropped for space and the
   thing a reader most needs

Then present the files and state which checks passed.
