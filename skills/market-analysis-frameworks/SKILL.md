---
name: market-analysis-frameworks
description: Analyse collected market-research evidence across consumption validation, competitive landscape, segmentation and ICP fit, and VC pairing. Use after evidence collection in any startup-thesis, market-opportunity, competitor or investor research run, when turning sources into findings. Load only the reference file for the analysis being performed.
---

# Analysis frameworks

Four analyses, four reference files. Read only the one you need — loading all four wastes
context and blurs the distinct questions each answers.

| Question | Read |
|---|---|
| Is anyone spending money or effort on this today? | `references/consumption-validation.md` |
| Who else addresses it, and can we win? | `references/competitive-landscape.md` |
| Which buyer first, and why them? | `references/segmentation-icp.md` |
| Who would fund this, and why them? | `references/vc-pairing.md` |

Output goes to `findings.md` in the run folder. Work from `evidence/`, not from memory of
what was read — the files exist so that analysis is over a fixed set rather than a fading
impression of one.

## Rules across all four

**Every claim carries evidence IDs.** A claim with none is either removed or labelled as
inference in the form `conventions.md` specifies, including what would falsify it.

**Answer the null hypothesis.** `scope.md` states what would make this a bad idea. Each
analysis must say what it found bearing on that, including nothing. An analysis that only
accumulates supporting evidence is not analysis.

**Contested stays contested.** Where sources disagree, present both and say what would
settle it. Averaging two incompatible figures produces a number that is certainly wrong.

**Confidence is per claim.** A section can hold a high-confidence claim next to a low one.
Blanket confidence statements at section level hide exactly the claims that need flagging.

**Count independence, not citations.** Five sources tracing to one press release is one
source. The `Origin` field in the evidence files exists for this.

**Report thin evidence as thin.** If a section rests on two weak sources, say so in the
section. The instinct to write around a gap so the analysis reads smoothly is the single
most damaging habit here — the user is making a resource-allocation decision and needs to
know which parts of the picture are load-bearing.
