---
name: pm-opportunity-mapping
description: Build and maintain opportunity solution trees for continuous discovery (Teresa Torres method) — define the outcome, map and structure the opportunity space from research, branch solutions, attach assumption tests, prune and reprioritize the tree as evidence arrives, and set up a continuous discovery cadence. Use this whenever the user mentions opportunity solution tree, OST, opportunity mapping, continuous discovery, "which opportunity should we pursue", wants to connect research insights to solution bets, or needs a standing artifact that links outcomes to opportunities to solutions to tests.
---

# Opportunity Mapping & Continuous Discovery

The opportunity solution tree is a *standing decision artifact*, not a workshop output. Its job: make the team's discovery thinking visible so opportunity selection becomes comparison ("which branch moves the outcome most?") instead of advocacy ("I like this idea"). This skill owns the tree end to end; pm-research-synthesis feeds it insights and pm-product-ideation deepens any single branch's solution work.

## Tree anatomy

```
OUTCOME (one metric the team can influence)
├── Opportunity (a customer need/pain/desire, in their words)
│   ├── Sub-opportunity (a distinct, smaller slice of the parent)
│   │   ├── Solution A
│   │   │   └── Assumption test
│   │   └── Solution B
│   └── Sub-opportunity
└── Opportunity
```

Layer rules that keep the tree honest:
- **Outcome**: one product outcome (behavior change the team can drive — "increase week-4 activation rate"), not a business outcome ("grow revenue") and not an output ("ship onboarding v2"). If the user brings a business outcome, derive the product outcome that drives it and note the chain. Source it from the KPI tree if one exists (pm-metrics-kpis).
- **Opportunities**: needs, pains, and desires *in the customer's frame*, traceable to research evidence. "Users can't tell if their import worked" is an opportunity; "add a progress bar" is a solution hiding a level too high — push it down and ask what need it serves. Every opportunity should be falsifiable by evidence and sized at least roughly (how many customers, how painful — pull from pm-research-synthesis frequency/severity scores).
- **Sub-opportunities**: split a parent only when the slices would be solved differently. Distinct, non-overlapping, smaller than the parent. Three levels of opportunity is usually the useful maximum.
- **Solutions**: minimum two per pursued opportunity — a single solution under an opportunity means the team decided before exploring; flag it.
- **Assumption tests**: the riskiest assumption per pursued solution and its cheapest test (design via pm-experiment-design).

## Before starting

1. **The outcome** — does the team have one, and is it a product outcome? This is the root; a tree with a fuzzy root is decoration. If multiple teams/outcomes are in play, one tree per team-outcome pair.
2. **Evidence inventory** — what research exists? Build opportunities only from evidence (interviews, support themes, synthesis output). If evidence is thin, say so and route through pm-customer-discovery first — an OST built from team opinions is an opinion tree wearing a methodology.
3. **Current state** — new tree, or restructure/update of an existing one?

## Building the tree

1. Confirm the outcome and its target/timeframe.
2. Extract opportunities from the evidence (or directly from a pm-research-synthesis output — its ranked insights map nearly 1:1 to opportunities).
3. Structure: group by the customer experience journey or by underlying need; enforce the layer rules; rewrite any solution-shaped entries as the needs beneath them.
4. Size each top-level opportunity: reach (how many), severity (how painful), outcome leverage (how plausibly does solving it move the root metric), confidence in the evidence.
5. Recommend the **target opportunity** — the one branch to pursue now — with reasoning. One branch at a time is the method's discipline; pursuing three branches means assessing none well.
6. Branch ≥2 solutions for the target, map their riskiest assumptions, attach tests.

Render the tree as both an indented text outline (the canonical, editable form) and a Mermaid diagram for sharing. Mark each node's status: `[pursuing]`, `[parked]`, `[killed — reason]`, `[needs evidence]`.

## Maintaining the tree (the part most teams skip)

The tree is only useful if evidence updates it. When the user returns with new research, test results, or "should we change course":

- **New evidence arrives** → which opportunities does it strengthen, weaken, or add? Update sizing; note the date and source on the node.
- **A test fails** → kill the solution, not the opportunity (the need is still real; the approach died). Only kill an opportunity when evidence says the need is rarer/milder than believed — record why, and keep killed nodes visible as institutional memory.
- **Quarterly or on outcome change** → re-derive: is the target opportunity still the highest-leverage branch? Prune stale `[needs evidence]` nodes older than a quarter — they're guesses fossilizing into furniture.
- **Drift check**: compare the tree against what the team actually shipped recently. Work that maps to no branch means either the tree is stale or the roadmap is untethered from discovery — name which.

## Continuous discovery cadence (when asked to set up the habit)

Weekly: small touchpoints with customers (aim for one conversation/week minimum; pm-customer-discovery for guides), each debriefed into the tree — new evidence tagged to nodes. Biweekly: review assumption-test results, advance or kill solutions. The tree is the agenda for discovery reviews; if a discussion doesn't touch a node, it's roadmap theater.

## Anti-patterns to catch and name

- **Solution tree in disguise**: opportunities that are features reworded ("opportunity: users need a dashboard"). Rewrite as the underlying need.
- **Outcome soup**: multiple outcomes on one tree — split it.
- **Opinion tree**: no evidence column. Mark every node `[needs evidence]` and prescribe the discovery to fill it.
- **Breadth addiction**: pursuing 4+ branches simultaneously. Force-rank to one target opportunity.
- **Write-only tree**: built once, never updated. Schedule the maintenance cadence at creation time.

## Quality bar

- Root is a single product outcome with a metric
- Every opportunity is customer-framed, evidence-tagged, and sized; no solutions hiding in the opportunity layer
- ≥2 solutions per pursued opportunity; each with riskiest assumption + cheapest test
- One target opportunity recommended, with comparative reasoning
- Tree ships with node statuses, evidence dates, and a maintenance cadence — never as a static diagram alone
