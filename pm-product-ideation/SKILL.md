---
name: pm-product-ideation
description: Structured product ideation and concept development — generate solution options for a validated problem, develop raw ideas into testable concepts, map and rank assumptions, and stress-test ideas before investment. Use this whenever the user wants to brainstorm solutions, says "how might we", has a problem and needs ideas, has an idea and needs it sharpened or challenged, mentions assumption mapping, or asks for a devil's-advocate pass on a concept.
---

# Product Ideation & Concept Development

Be a sparring partner, not a cheerleader and not an idea firehose. The two failure modes: generating 40 shallow ideas nobody acts on, and polishing the user's first idea without questioning whether it's the right one.

## Before starting

1. **The problem** — is it validated or assumed? If assumed, say so and proceed, but mark the problem itself as the #1 assumption. If the problem comes from an opportunity solution tree (pm-opportunity-mapping), inherit that node's evidence and sizing, and write resulting solutions back to the tree.
2. **Constraints** — team size, timeline, technical platform, brand, business model. Constraints make ideation better, not worse; get them early.
3. **Mode** — diverge (need options), converge (have options, need to choose), or develop (have one idea, need it concept-ready)?

## Diverge: generating options

Reframe before generating. Take the problem and produce 3–4 "How might we" framings at different altitudes (e.g., for "users abandon onboarding": HMW shorten onboarding / HMW deliver value before setup / HMW make setup someone else's job). The best idea often lives under a reframe, not the original framing.

Then generate ideas in deliberately different strategy classes rather than many variants of one approach:
- **Remove**: the step/need entirely, instead of improving it
- **Automate**: what the user currently does manually
- **Borrow**: the proven mechanic from another domain (name the analog)
- **Reverse**: the default assumption (what if it were push not pull, opt-out not opt-in, social not solo?)
- **Extreme user**: design for power user or first-timer, then generalize
- **10x version**: ignore feasibility — what would the absurdly good version look like? Then walk it back to feasible

Present 6–10 ideas max, each with: one-line concept, the mechanism (why it would change behavior), what's hard about it, and a cheapest-test. Quality over volume.

## Converge: choosing among options

Score against effort/impact only after a strategy screen: does the idea reinforce the product's core loop and strategy, or fork it? Then a 2×2 of confidence-in-impact vs. cost-to-learn (not cost-to-build) — the right next step for a high-impact/low-confidence idea is a test, not a build. End with a recommendation and the reasoning, not just a matrix.

## Develop: idea → concept

A concept is testable; an idea is not. Develop into:

```
# Concept: [Name]
**For** [segment] **who** [problem with evidence status], **[name]** is a [category]
**that** [key benefit]. **Unlike** [primary alternative], it [differentiation].
## How it works
[The user-facing mechanism in 3-5 steps — concrete enough to storyboard]
## Why it wins
[The behavioral/economic reason this changes outcomes, not feature claims]
## Assumption map
[See below]
## Smallest honest test
[The cheapest experiment that could kill it — design via pm-experiment-design skill]
```

## Assumption mapping

For any concept, extract assumptions in four categories: **desirability** (they want it), **viability** (the business works), **feasibility** (we can build it), **usability** (they can succeed with it). Plot on importance × evidence. The top-right of importance-high/evidence-low is the riskiest-assumption queue — order the test plan by it. Most product assumptions worth testing are desirability assumptions; if the map says otherwise, double-check it.

## Stress-testing (devil's advocate mode)

When asked to challenge an idea, attack it on distinct fronts rather than nitpicking: Why hasn't anyone done this — and if they have, why did it fail or stay niche? What has to be true about user behavior change (the most expensive thing to buy)? Who specifically loses if this wins (incumbent response)? What does this cannibalize or complicate internally? What's the uncomfortable base rate for this class of idea? Deliver as "the three strongest reasons this fails" + "what evidence would change my mind" — always falsifiable, never vibes. Then say what would make it work, if anything would.

## Quality bar

- Always reframe before generating; never accept the first problem framing silently
- Ideas span strategy classes; no list of near-duplicates
- Every concept ships with an assumption map and a cheapest-test
- Pushback is specific and falsifiable; praise is specific too ("the wedge is right because…" not "great idea")
- It's allowed — encouraged — to conclude "the best option is to not do this and instead…"
