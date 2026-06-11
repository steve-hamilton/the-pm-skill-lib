---
name: pm-prioritization
description: Prioritize features, initiatives, and backlogs with the right framework — RICE, WSJF, Kano, ICE, opportunity scoring, cost-of-delay — plus stack-ranking facilitation, tradeoff decisions, and defending priority calls to stakeholders. Use this whenever the user must choose among competing items, asks "what should we build first", has a backlog to rank, needs to make room for a new ask, mentions RICE or any scoring framework, or has to justify why something ISN'T being built.
---

# Prioritization

Prioritization frameworks don't make decisions — they expose the assumptions behind decisions so the team can argue about the right things. Treat every score as a structured argument, not arithmetic truth. The most common failure: false precision (a RICE score of 847 vs 832 means nothing; an order-of-magnitude gap means a lot).

## Before starting

1. **The items and their state** — get the actual list with whatever estimates exist. Flag items that are too big/vague to score ("replatform" can't be scored against "fix export bug" — different altitude; separate strategic bets from backlog items first)
2. **The strategy screen** — what's the current strategy/goal these serve? Items off-strategy get filtered before scoring, not scored politely. No strategy available? Use pm-product-strategy first, or proceed with the goal the user names and label the dependency.
3. **The constraint** — capacity, deadline, dependency, or a political reality? Prioritization against unlimited capacity is fiction.

## Framework selection

Pick for the situation; explain the pick in one line:

- **RICE** (Reach × Impact × Confidence ÷ Effort) — default for feature backlogs with usage data. Discipline: Reach as users/period from real data; Impact on the 0.25–3 scale; Confidence as % that caps enthusiasm (anything without evidence ≤ 50%); Effort in person-weeks from whoever will build it, not the PM.
- **WSJF** (Cost of Delay ÷ Duration) — when timing dominates: deadlines, decaying opportunities, compliance. Forces the question RICE misses: what does waiting cost per month?
- **Kano** — when deciding investment *type*: which features are table-stakes (absence kills deals), performance (more is linearly better), delighters (differentiation). Needs user input data or honest proxy; mark which.
- **Opportunity scoring** (importance vs satisfaction) — post-research, finds underserved needs from pm-research-synthesis output.
- **ICE / simple value-effort 2×2** — early stage, low data, or when the team is drowning in process. Don't over-tool small decisions.

For mixed portfolios, bucket first (e.g., 60% core/strategy, 20% growth bets, 20% debt+quality — adjust to context), then rank within buckets. Cross-bucket scoring always shortchanges debt and bets.

## Scoring discipline

- Build the table with explicit per-cell rationale, not just numbers — the rationale column is the deliverable
- Run sensitivity: which ranking flips if Confidence or Effort moves 2x? Items whose rank is assumption-fragile get flagged for cheap validation (pm-experiment-design) instead of immediate build
- Tier the output (Now / Next / Later / Won't), don't pretend rank #7 vs #8 is meaningful
- Always include the **Won't list with reasons** — it's the most useful artifact for stakeholder management

## Output structure

```
# Prioritization: [Scope] — [Date]
## Method & strategy screen
[Framework chosen + why; items filtered out as off-strategy, named]
## Ranked tiers
[Now / Next / Later — table with scores AND rationale per cell]
## Sensitivity notes
[Which calls are fragile to which assumptions; recommended cheap validations]
## Won't do (and why)
[Each with the honest reason: off-strategy / poor ratio / blocked / superseded by X]
## Tradeoffs made
[What the top tier displaces; who will be unhappy and what to tell them]
```

## Handling the hard cases

- **The exec pet project**: score it with the same table, in front of everyone. If it ranks low, the table does the arguing; offer the cheap-test compromise ("2-week spike before committing a quarter").
- **Sales says we lose every deal without X**: ask for the deal list. Convert anecdote to Reach data. Often real — but sized, it's a tier call, not a fire drill.
- **Everything is P0**: capacity-box it. "Here's the line at our velocity; everything below it moves to next cycle — which two items above the line should drop below it?" Forcing the swap question beats arguing priorities in the abstract.
- **Tech debt never wins**: that's the cross-bucket scoring bug; give debt its own protected allocation and rank within it by risk-of-inaction.

## Quality bar

- Strategy screen before scoring, always
- Every score cell has a stated basis; data-free confidence capped
- Sensitivity analysis present; fragile rankings get validation recommendations, not false certainty
- The Won't list exists and gives real reasons
- Final output acknowledges the judgment calls a framework can't make — and makes them, with reasoning
