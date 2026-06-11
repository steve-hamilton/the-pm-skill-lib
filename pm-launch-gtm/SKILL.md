---
name: pm-launch-gtm
description: Plan product launches and go-to-market — launch tier selection, rollout and feature-flag strategy, launch readiness checklists, GTM motion alignment, internal enablement, launch comms coordination, and post-launch review. Use this whenever the user is shipping something — asks how to launch a feature or product, mentions GTM, rollout plan, beta program, launch checklist, enablement, release plan, or "we ship in N weeks, what do we need".
---

# Launch & Go-to-Market

A launch is a coordinated bet that attention + readiness = adoption. Most launch failures are tiering failures: company-launch treatment for a feature nobody outside the team should care about, or silent-shipping the thing that needed sales enablement. Get the tier right and the rest is checklists done early.

## Before starting

1. **What's shipping and the evidence behind it** — feature/product/redesign, who it's for, validated how
2. **The motion** — sales-led, PLG, marketplace, hybrid; existing customers vs. new acquisition focus
3. **Date pressure** — fixed (event, contract, compliance) or quality-gated? This decides whether scope or date flexes when something slips.
4. **Adoption definition** — what does success look like 30/90 days post-launch, in numbers? A launch without an adoption target is a deploy.

## Tier the launch first

- **Tier 1 (company moment)**: new product/category bet. Full GTM: press, exec comms, sales play, pricing, events. Rare — 1-3/year.
- **Tier 2 (market moment)**: major capability that changes a buying decision or renewal. Blog, campaign, enablement, customer comms, maybe analyst pre-brief.
- **Tier 3 (customer moment)**: notable improvement for existing users. Changelog, in-app announce, docs, CS heads-up.
- **Tier 4 (silent)**: fixes, infra, experiments behind flags. Changelog at most.

Most disagreement about "the launch plan" is unstated disagreement about tier — make the tier decision explicit and get it agreed before planning. Effort and the checklist scale from it.

## Rollout strategy

Decouple *deploy* from *launch* — dark-launch behind a flag, then stage exposure: internal → design partners/beta (with a feedback loop that has an owner) → percentage ramp (with metric gates at each stage: what must hold to widen) → GA. For each stage: entry criteria, watch metrics, hold duration, and **rollback criteria pre-committed** ("we pull back if error rate > X or activation < Y"). For changes to existing behavior, add: migration plan, deprecation comms timeline, and the loud-minority plan (who will hate this change and what we tell them).

## Launch plan structure

```
# Launch Plan: [Name] — Tier [N] — Target [date]
## The moment
[One paragraph: what ships, for whom, why now, the one-line message]
## Success targets
[Adoption/usage/revenue targets at 30/90 days + leading indicators in week 1]
## Rollout schedule
[Stages with dates, gates, rollback criteria]
## Workstream checklist
[See below — each item: owner + date, working backward from launch]
## Messaging core
[Positioning one-liner, 3 proof points, the demo moment. Full positioning via pm-product-strategy]
## Risk register
[Top risks with mitigation + the call-tree for launch-day issues]
## Post-launch
[Day-7 metrics check, day-30 review (pm-metrics-kpis), retro date — scheduled NOW]
```

## Workstream checklists (scale by tier)

**Product readiness**: instrumentation live and verified pre-launch (test events received — the #1 day-one regret is unmeasurable launches), flags tested both directions, perf at expected load, accessibility pass, error/empty states, docs.
**Enablement** (T1-2): sales deck + demo script, FAQ with the hard questions (pricing edge cases, competitor comparisons, migration), CS macros, train-the-team session ≥1 week before, win/loss feedback channel.
**Comms**: external (blog, email, in-app, social, PR by tier) and internal (the company knows before customers do — support hearing about a launch from a ticket is a planning failure).
**Commercial** (if applicable): pricing/packaging final, billing tested, legal/compliance, partner notifications.

## Post-launch review

At day 30: targets vs. actuals with the why behind misses, funnel from awareness → trial → adoption → habit (find the leak stage), qualitative pull (what are users/reps saying unprompted), and the decision: double-down / iterate / harvest / sunset. A launch isn't done until this review happens — it's the input to the next bet.

## Quality bar

- Tier decided explicitly and stated before any planning detail
- Deploy decoupled from launch; rollback criteria pre-committed per stage
- Instrumentation verified before exposure widens — never after
- Every checklist item has an owner and a date; internal comms precede external
- Success targets numeric, with a scheduled review that has a decision attached
