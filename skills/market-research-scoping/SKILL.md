---
name: market-research-scoping
description: Scope a market or startup-thesis research run before any research begins — interview the user, then write a run contract to disk. Use this whenever the user asks to research, validate, size, or pressure-test a startup idea, business thesis, product opportunity, market, segment or competitive landscape, even if they phrase it casually ("look into X", "is there a market for Y", "should we build Z"). Always run this first; never start searching before the contract exists and the user has approved it.
---

# Research scoping

A research run is only as good as its brief. The most expensive failure in market research
is not a bad search, it is researching the wrong question thoroughly. This skill spends
five minutes preventing that.

Output is `scope.md`: a written contract that every later phase reads. It is also what
makes the agent generic — nothing about a particular thesis lives in these skills, it all
lives in the contract.

## Hard gate

Do not search, browse, or fetch anything before `scope.md` exists and the user has
approved it. This includes "just a quick look to understand the space". An early search
anchors the whole run on whatever happened to rank first, and the user loses the chance to
redirect before the evidence is collected.

If the user asks you to skip scoping, offer the defaults path below instead of skipping.

## Procedure

### 1. Create the run folder

Slugify the thesis. `runs/YYYY-MM-DD-<slug>/`, with an empty `evidence/` inside. If a
folder for the same slug exists, ask whether this is a refresh of that run (read the old
`scope.md` and offer it as a starting point) or a new investigation.

### 2. Ask batch one — what are we deciding?

Ask these together, not one at a time. Serial questioning is exhausting and produces worse
answers than a single considered reply.

1. **The thesis in one sentence.** Who has what problem, and what changes if it is solved.
2. **The null hypothesis.** What would you have to learn for this to be a bad idea? This
   is the single most valuable answer in the interview. If the user cannot name it, the
   thesis is not yet falsifiable, and saying so is more useful than researching it.
3. **Geography.** Where the customers are, not where the user is. Note separately if
   trade, import/export or regulatory jurisdiction is part of the thesis.
4. **Who pays.** Distinguish the user of the product, the person who feels the pain, and
   the person with budget. These are frequently three different people and conflating them
   is the most common way segment research goes wrong.
5. **Stage of the question.** Is this "does a market exist", "which segment first", "can we
   win against incumbents", or "who would fund this"? The four need different depth.

### 3. Ask batch two — how should we work?

6. **What counts as evidence of consumption.** Offer concrete options so the user is
   choosing rather than composing: existing spend on alternatives, job postings naming the
   pain, tool adoption curves, support-forum volume, procurement records, switching
   behaviour. Let them rank.
7. **Evidence bar.** How many independent sources before a claim is treated as established.
   Default: two, at least one primary.
8. **Sources.** Read `sources.md` and confirm the tiers to use. Ask specifically whether
   any authenticated portals should be in scope, since those need the browser and
   per-site approval.
9. **Depth budget.** Number of competitors, number of investors, freshness window, and
   whether the run is attended (you can ask questions mid-run) or unattended (you must
   log gaps and continue).
10. **Deliverables.** Which of report, deck, spreadsheet, document, PDF. Default to
    `report.md` only, with the rest on request after review.

### 4. Write and confirm

Fill `assets/scope-template.md` and write it to the run folder. Then show the user a short
summary — thesis, null hypothesis, segment focus, source tiers, depth — and ask for
explicit approval or corrections. Do not proceed on silence or on a vague "sounds good"
to a long list; confirm the thesis and null hypothesis specifically, since those two
govern everything downstream.

### Defaults path

If the user wants to move fast, offer to fill everything from defaults except items 1, 2
and 4, which nobody can answer for them. Write the defaults into `scope.md` explicitly
rather than leaving fields blank, so the run is reproducible and the assumptions are
visible when the report is read later.

## Anti-patterns

**Researching during the interview.** The user says "it's a bit like Vendor X" and the
temptation is to look up Vendor X. Write the name in the contract and move on.

**Accepting an unfalsifiable thesis.** "We think AI will change procurement" cannot be
researched. Push for the specific claim underneath it. One round of pushing is help; three
is obstruction, so if it will not sharpen, record it as broad-exploratory in the contract
and set expectations that the output will be a map rather than a verdict.

**Inventing answers to unasked questions.** If the user did not specify geography, ask.
Do not default to the US because most sources are American.

**Silently widening scope.** If during the run the question changes, stop and amend
`scope.md` with a dated note. A run whose contract drifts cannot be interpreted afterwards.
