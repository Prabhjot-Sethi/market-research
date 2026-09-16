# Source registry

Edited by you, read by the agent. `market-source-routing` consults this before every
search. Adding a source here is how you teach the agent where to look without touching a
skill.

Tiers describe how much weight a claim from that source carries, not how useful it is.
Discourse is often the most useful and the least reliable at the same time.

## T0 — your own material

Prior run folders under `runs/`, and anything you place in the workspace. Highest trust,
zero coverage. Check first; it is free and it stops the agent re-researching what you
already know.

- Prior runs: `runs/*/report.md`
- Drop customer call notes, transcripts or internal docs in the run folder to have them
  treated as T0 evidence

## T1 — primary and official

The company's own words, or a regulator's. Trust the fact, not the framing.

- Vendor sites: pricing pages, changelogs, docs, status pages, security pages
- Job boards: the vendor's own careers page, and LinkedIn job listings
- Filings and registries: MCA/ROC (India), SEC EDGAR (US), Companies House (UK)
- Government and regulator publications, tender and procurement portals
- Trade data portals where the thesis has an import/export dimension

## T2 — structured third-party

Someone else's database. Good for coverage, frequently stale on specifics.

- Funding and company data: Crunchbase, Tracxn, PitchBook, Dealroom
- Buyer reviews: G2, Capterra, TrustRadius, Gartner Peer Insights
- Usage proxies: GitHub stars and commit cadence, npm/PyPI download trends, app store
  ranks and review counts, Docker pulls
- Headcount trend: LinkedIn company page over time

## T3 — discourse

What practitioners say when they are not being marketed to. Weight by specificity: a
comment describing a concrete workaround is worth more than ten comments agreeing that a
problem exists.

- Hacker News, relevant subreddits, Discord and Slack communities
- Vendor support forums and GitHub issue trackers (volume and recurrence matter)
- LinkedIn posts from practitioners, not founders marketing
- Podcasts and conference talks by operators in the segment

## T4 — analyst and media

Useful for framing and for numbers you will need to attribute. Rarely load-bearing.

- Analyst firms, industry press, sector newsletters

## Denylist

Do not use these, and do not cite them even if they surface in search:

- Content-farm "top 10 tools" listicles and affiliate comparison sites
- AI-generated market-size pages with no stated methodology
- Any market-size figure whose source chain cannot be traced to a primary document

## Authenticated sources

Sources requiring a logged-in session, reached through the browser. Pre-approve these in
a short session before the first unattended run so per-site permission prompts do not
stall it.

<!-- Add yours. Format: name — URL — what it is good for -->

- (none configured yet)

## Freshness

Default window is 18 months. Anything older is usable for structural context but must not
carry a claim about the current state of the market. Override per run in `scope.md`.
