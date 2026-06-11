---
name: pm-pmf-assessment
description: Measure and diagnose product-market fit — Sean Ellis survey design and analysis, retention curve interpretation, engagement depth analysis, PMF scorecards, and "do we have PMF / why are we stuck" diagnosis with next moves. Use this whenever the user asks about product-market fit, PMF, whether to scale or keep iterating, why growth is stalling, churn diagnosis at the product level, retention curves, or "is this working" for an early product.
---

# Product-Market Fit Assessment

PMF is not a feeling, a press cycle, or a revenue number — it's evidenced by retention and pull. This skill turns the question "do we have it?" into a measurable answer with a diagnosis and a next move. The cardinal rule: **PMF is assessed per segment, not per product.** Most "weak PMF" is strong PMF in one segment diluted by everyone else.

## Before starting

1. **Product, stage, and motion** — what it is, how long in market, sales-led/PLG/marketplace/consumer (benchmarks differ enormously)
2. **Available data** — retention cohorts? survey capability? usage analytics? churn interviews? Build the assessment from what exists; prescribe what's missing.
3. **The decision** — raise/scale spend/keep iterating/pivot? The bar differs by what's at stake.

## The evidence stack (in order of trustworthiness)

1. **Retention cohorts** — the ground truth. Plot % of each cohort still active (on a meaningful action, not logins) over time. **Flattening curve = PMF evidence; curve that decays to zero = no PMF, regardless of growth.** Growth can mask non-retention for years; always check whether topline is new users replacing churned ones.
2. **Usage intensity** — frequency vs. the natural frequency of the job (daily tool used weekly = problem; quarterly tool used quarterly = fine). Define the product's natural frequency before judging.
3. **Pull signals** — organic/word-of-mouth share of acquisition, inbound demand, users hacking the product to do more, complaints when it's down (silence during outages is a bad sign)
4. **Sean Ellis survey** — "How disappointed if you could no longer use this?" ≥40% "very disappointed" is the classic threshold. Run it correctly: only on users who've experienced the core value recently (active 2+ weeks, used core feature), segment results before reading the topline, and mine the follow-ups ("what type of person benefits most?", "what's the main benefit?") — the verbatims from very-disappointed users are the positioning and roadmap, not just the score.
5. **Willingness to pay** — renewals, expansion, price-insensitivity. Lagging but confirming.

Never rest a PMF verdict on one source; triangulate at least retention + one demand-side signal.

## The scorecard

```
# PMF Assessment: [Product] — [Date]
## Verdict
[Strong PMF in [segment] / Emerging / Not yet — one paragraph, evidence-led]
## Evidence summary
[Each evidence source: finding, benchmark comparison, confidence]
## Segment analysis
[The heart of it: retention/survey/engagement broken out by segment. Name the best segment and how it differs]
## Diagnosis
[See failure modes below]
## Recommended next move
[Specific: who to focus on, what to stop, what to measure next, when to reassess]
```

## Diagnosis: common failure patterns

Match symptoms to disease before prescribing:

- **Retention flat but low plateau (5–15%)** → PMF with a niche; identify who the retained users are and refocus everything on them (the Superhuman method: build for very-disappointed users' needs, ignore the rest)
- **Good activation, decaying retention** → value isn't durable: one-time job, or competing habit wins. Check natural frequency; consider repositioning to the recurring version of the job
- **Poor activation, good retention of activated** → PMF exists behind an onboarding wall; this is a funnel problem, not a fit problem — cheapest PMF win available
- **High NPS/survey love, low usage** → people love the idea, not the product; or wrong respondents surveyed
- **Strong logo retention, weak usage (B2B)** → shelfware risk; renewal cliff is coming, fix engagement before it arrives
- **Everything mediocre, no strong segment** → the hard truth: no wedge yet. Recommend narrowing target + discovery (pm-customer-discovery), not feature volume

## Benchmarks to apply (state as ranges, note motion-dependence)

Consumer social/daily: D30 ≥ 20–25% strong · Consumer transactional: M6 ≥ 15–20% on natural frequency · B2B SaaS: gross logo churn ≤ 1–2%/mo SMB, ≤ 0.5–1%/yr enterprise; NDR ≥ 110% strong · PLG: activation→week-4 retention is the canary. Search for current benchmarks when precision matters; label all benchmarks as directional.

## Quality bar

- Verdict is segment-specific, never product-global
- Retention evidence always requested first; survey-only verdicts labeled as weak
- Every diagnosis pairs with a falsifiable next test or move
- Willing to deliver "you don't have it yet" plainly, with the kindest-but-clearest framing of what to do about it
