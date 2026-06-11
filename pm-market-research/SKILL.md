---
name: pm-market-research
description: Research and size a market for product decisions — landscape mapping, TAM/SAM/SOM sizing, segmentation, trend analysis, and market entry assessment. Use this whenever the user wants to understand a market, size an opportunity, evaluate a new space, asks "how big is the market for X", mentions TAM, market maps, industry analysis, market trends, or needs market context for a strategy doc, board deck, or investment case — even if they don't say "market research" explicitly.
---

# Market Research & Sizing

Produce market research a CPO would trust in a board meeting: sized with explicit assumptions, sourced with dates, and honest about uncertainty.

## Before starting

Gather what's needed, asking only for what can't be inferred:

1. **Decision context** — what decision does this research inform? (enter a market, fund an initiative, position against a trend, brief execs). The decision determines depth and framing.
2. **Market definition** — what exactly counts as "the market"? Push for precision: "AI note-taking for sales teams" not "productivity software". A fuzzy market definition makes every number downstream meaningless.
3. **Geography and time horizon** — global or regional? Sizing for today or a 3–5 year projection?

If the user gives a vague brief, propose a sharp market definition and confirm it before researching.

## Research workflow

Use web search aggressively. Market data goes stale fast — never rely on training knowledge for market sizes, growth rates, or vendor landscapes. Search for: analyst reports (Gartner, Forrester, IDC, CB Insights), public company filings and earnings calls (the best free market data available), funding announcements, and practitioner communities for ground truth on pain points.

For every figure captured, record: the number, the source, the publication date, and what the source counted. Two "market size" numbers often differ 10x because they counted different things — reconcile or note the discrepancy.

## Market sizing method

Always size two ways and triangulate:

**Top-down**: start from an analyst-reported market size, narrow by segment/geography. Fast but inherits the analyst's definition.

**Bottom-up** (more credible — always include): `# of target customers × adoption ceiling × realistic price point`. Build the chain explicitly, e.g.: ~400K mid-market B2B companies in target geos × ~30% with dedicated sales ops × $15K ACV = $1.8B SAM.

State every assumption in the chain as a line item the reader can disagree with. A sizing whose assumptions are visible is more credible than a bigger number with hidden ones.

- **TAM**: everyone who could conceivably buy if you served every segment/geo
- **SAM**: the portion your business model and go-to-market can actually reach
- **SOM**: what you can realistically capture in 3–5 years given competition and your resources — justify with an analogous company's trajectory, not a "1% of TAM" hand-wave (call out that pattern if tempted)

When the two methods disagree by more than ~2x, say so and explain which to trust and why.

## Report structure

Default to a markdown document (offer .docx for exec distribution). Use this template:

```
# Market Research: [Market], [Date]
## Executive summary
[The decision this informs, the headline numbers, and the 2-3 findings that matter most. Max half a page.]
## Market definition & boundaries
[What's in, what's out, and why]
## Market size
[TAM/SAM/SOM with both sizing methods, assumption tables, triangulation note]
## Growth & trends
[CAGR with source; 3-5 structural trends, each with evidence and a "so what" for the reader]
## Segmentation
[Segments by need (not just firmographics), relative size, which are underserved]
## Competitive landscape snapshot
[Market map: leaders, challengers, insurgents. Point to a full CI deep-dive (pm-competitive-intelligence skill) rather than duplicating it]
## Buyer dynamics
[Who buys, who decides, budget source, replacement cycle, build-vs-buy posture]
## Risks & open questions
[What would change the conclusion; what to validate next]
## Sources
[Every source with date accessed]
```

## Quality bar

- Every quantitative claim has a dated source or an explicit assumption chain
- Bottom-up sizing present, with the multiplication shown
- At least one finding that challenges the user's likely prior — research that only confirms what was already believed should say so explicitly
- Trends connect to implications: never "AI is growing" without "which means X for your decision"
- Flag any segment where you found strong pain-point evidence but weak vendor coverage — that's the most valuable output of market research
