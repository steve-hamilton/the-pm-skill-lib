---
name: pm-experiment-design
description: Design product experiments and validation tests — hypothesis writing, A/B test design with sample size and duration math, MVP and prototype test selection (fake door, concierge, Wizard of Oz, landing page), and interpreting ambiguous results. Use this whenever the user wants to test an idea or assumption, validate demand, run an A/B test, asks "how do we know if this works", mentions MVP, experiment, hypothesis, conversion test, or has test results to interpret.
---

# Experiment Design

Design tests that can actually change a decision. The two failure modes: experiments that can't fail (success criteria written after results), and experiments more expensive than just shipping the thing.

## Before starting

1. **The assumption under test** — get it stated as a falsifiable claim about user behavior, not a feature ("≥20% of trial users who see the import option will use it in week one", not "users want imports")
2. **The decision tied to it** — what happens on pass, what happens on fail? If the answer to both is "we ship anyway," refuse politely: that's not an experiment, recommend skipping it and instrumenting the launch instead
3. **Available traffic/users and tooling** — determines which methods are even possible

## Hypothesis format

> We believe **[change/concept]** for **[segment]** will cause **[behavioral outcome]**, measured by **[metric]**. We'll conclude it worked if **[threshold]** within **[timeframe]**. If it fails, we will **[decision]**.

Every element pre-committed, including the fail action.

## Method selection

Match the method to the assumption type and evidence cost — always recommend the cheapest test that could kill the assumption:

| Assumption | Cheapest honest test |
|---|---|
| People want this (demand) | Fake door / landing page + signup with a real ask (email, deposit, waitlist position) |
| People will pay / pay this much | Pricing page test, pre-order, sales conversations with a real close attempt |
| People can use it (usability) | Prototype test, 5 users per round |
| The value is real once used | Concierge (deliver manually) or Wizard of Oz (fake the backend) |
| It moves the metric at scale | A/B test (only valid at this stage — A/B testing demand for an unbuilt thing is overkill) |
| It's feasible | Spike / technical prototype |

Note the ethics line for fake-door tests: collect intent honestly, tell users it's coming, don't burn trust with paying customers — suggest running on prospects or a holdout.

## A/B test design

When designing a controlled test, always produce:

1. **Primary metric** (one), guardrail metrics (the things that must not degrade — always include at least one), and the minimum detectable effect (MDE) worth acting on — ask "what's the smallest lift that would justify shipping the complexity?"
2. **Sample size & duration math** — compute it (α=0.05, power=0.8 defaults; state them). Use the shell to calculate rather than estimating. Then the critical honesty check: if the user's traffic gives a 9-week test for the MDE, say so and offer the real options: bigger MDE, sequential testing, a coarser method, or shipping with monitoring.
3. **Run rules, pre-committed**: full weekly cycles (minimum one, prefer two), no peeking-and-stopping (or use a sequential design explicitly), segments to analyze named in advance (everything else is exploratory, labeled as such)
4. **Decision matrix written before launch**: win → ship; flat → [named action]; lose → [named action]; guardrail breach → [named action]

## Interpreting results

When the user brings results: check duration/sample against plan first; check for novelty effect (did the lift decay over the run?); flat results with adequate power are a real answer (the assumption failed — say it plainly); underpowered flat results are no answer at all (distinguish loudly). For surprising segment effects discovered after the fact, label them hypothesis-generating, not conclusions. Multiple-comparison inflation is real: 20 metrics at p<0.05 ≈ 1 false positive expected.

## Validation plan (multi-assumption)

For a concept with an assumption map (see pm-product-ideation), sequence tests by risk: kill-shot assumptions first, cheapest method first, each round's pass condition feeding the next. Present as a stage-gate table: assumption → method → threshold → cost → on-fail action.

## Quality bar

- Every test has a pre-committed fail action; no test exists that can't change a decision
- Sample size and duration computed, not vibed; underpowered designs flagged before launch
- Guardrail metrics always present
- The cheapest sufficient method recommended — including "don't test, just ship it reversibly" when the build cost is lower than the test cost
