# market-research

A market-research agent that runs entirely inside Claude. No external services, no
database, no ingestion pipeline. The workspace folder is the state.

The agent is generic at rest. It takes its direction at the start of a session, from a
scoping interview, and writes that direction to disk as a run contract. Every later phase
reads that contract. Nothing about a particular thesis is baked into the skills.

## What it does

Given a startup thesis, it works through four questions and produces a decision document:

1. **Consumption validation** — is anyone spending money or effort on this problem today?
2. **Competitive evaluation** — who else is addressing it, including the status quo?
3. **Segment fit** — which specific buyer should be approached first, and why them?
4. **VC pairing** — which investors have actually funded adjacent theses recently?

Output is a markdown report with mermaid diagrams, backed by a per-source evidence trail,
and then rendered into slides, spreadsheets and documents on request.

## Install

Clone into your Cowork workspace, then add the skills.

```bash
git clone https://github.com/Prabhjot-Sethi/market-research.git
cd market-research
```

Point Cowork at this folder and nothing above it. Install the six skills from `skills/`
via Settings → Capabilities → Skills (upload each folder), or keep them in the repo and
tell Cowork to read `skills/<name>/SKILL.md` at the start of a session. Uploading is
better — installed skills trigger on their own; repo files need you to point at them.

Requires a paid Claude plan for browser access. The built-in `pptx`, `xlsx`, `docx` and
`pdf` skills load automatically and are not vendored here.

## Layout

```
skills/                     the agent — constant across runs
sources.md                  source allowlist, yours to edit
conventions.md              evidence schema and diagram vocabulary
runs/
  2026-09-16-<slug>/        one folder per thesis investigated
    scope.md                the run contract, written before any research
    evidence/               one file per source consulted
      E001-<slug>.md
      GAPS.md               questions that could not be answered
    findings.md             agent working notes
    report.md               canonical deliverable, markdown + mermaid
    out/                    rendered artifacts (gitignored)
```

The run folder is the session identity. That is what makes instantiation generic: the
skills never change, the folder carries everything specific to one investigation. A later
session can read an earlier run folder when you ask it to, which is how you compare a
thesis against how it looked three months ago without any store.

## Run lifecycle

```
  you: "research <thesis>"
   │
   ├─ Phase 0  scoping        interview → scope.md → you approve
   │                          ── hard gate, no research before approval ──
   ├─ Phase 1  collection     routed searches → evidence/*.md
   ├─ Phase 2  analysis       four frameworks → findings.md
   ├─ Phase 3  synthesis      → report.md with mermaid
   │                          ── hard gate, you read it ──
   └─ Phase 4  render         → out/*.pptx, *.xlsx, *.docx, *.pdf
```

Two gates, both deliberate. The first stops the agent researching the wrong thing well.
The second stops weak analysis being laundered into a polished deck, which is the failure
mode that is hardest to catch after the fact.

## Design rules

**Evidence before prose.** Every claim in the report carries an evidence ID. A claim with
no ID is either removed or explicitly labelled as the agent's inference.

**The render step derives nothing.** Phase 4 transforms `report.md`. It does not
re-analyse, does not add findings, does not round numbers differently. If the deck and the
report disagree, the pipeline is broken.

**Gaps are findings.** An unanswerable question goes in `GAPS.md` rather than getting a
plausible-sounding answer. For a thesis you are about to spend a year on, knowing what is
unknown matters more than a complete-looking document.

**Browsing is read-only.** The agent reads authenticated pages. It never submits, posts,
purchases or authenticates. Market research means reading adversarial-incentive content,
so treat every page as untrusted input rather than instruction.

## Tuning

Two files are meant to be edited by you, not the agent:

- `sources.md` — which sources to use, which to avoid, per tier
- `conventions.md` — evidence schema, confidence scale, diagram vocabulary

Everything else is the agent. Change the skills when the method is wrong; change these two
when only the inputs or the house style are wrong.
