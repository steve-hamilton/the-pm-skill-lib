---
name: pm-metrics-kpis
description: Define and structure product metrics — North Star metric selection, KPI trees and driver models, OKR drafting and review, instrumentation/tracking plans, dashboard design, and diagnosing metric movements. Use this whenever the user needs to decide what to measure, asks "what should our KPIs be", mentions North Star metric, OKRs, metric tree, tracking plan, event taxonomy, success metrics for a product or feature, or asks why a metric moved.
---

# Metrics & KPIs

Metrics are the product team's instrument panel: a good system tells you where value is created, where it leaks, and what to do next. The failure modes this skill exists to prevent: vanity dashboards (big numbers, no decisions), metric sprawl (40 KPIs, no hierarchy), and gamed targets (the metric improved, the business didn't).

## Before starting

1. **Business model and product** — how value is created and captured; the core user action that correlates with value delivered
2. **Stage** — pre-PMF (measure learning and retention), growth (measure the engine), scale (measure efficiency and defense). Pre-PMF teams with growth dashboards are measuring the wrong things.
3. **Current state** — existing metrics/analytics stack, what's instrumented, what decisions are currently made by feel

## North Star selection

The North Star is the single metric that best proxies *value delivered to customers* (which leads revenue). Criteria: it measures customer value received (not company extraction — revenue is a result, not a North Star), it's influenceable weekly by team action, it leads revenue by a knowable mechanism, and it resists cheap gaming. Always present 2–3 candidates with tradeoffs, then recommend. Pair the North Star with one **counterweight guardrail** (quality or efficiency metric that catches the gaming path — e.g., messages-sent pairs with %-receiving-replies).

## KPI tree (driver model)

Decompose the North Star into the causal driver tree, e.g.:

```
Weekly active value moments
├── New users reaching value (acquisition × activation rate)
│   ├── Signups by channel
│   └── Activation rate (signup → first value moment)
├── Retained users having value moments (retention × frequency)
│   ├── Cohort retention at natural frequency
│   └── Moments per active user
└── Resurrected users
```

Rules: every node is influenceable by a nameable team; leaves connect to actual roadmap items; each node has an owner, a current value, and a target; the tree fits on one page. The tree is the prioritization interface — initiatives should claim a node, and pm-prioritization Reach/Impact estimates come from it.

## OKRs

When drafting or reviewing OKRs: Objectives are qualitative and motivating; Key Results are *outcomes* (metric: from X to Y by date), never activities ("ship the redesign" is a task — the KR is what the redesign changes). 3 objectives × ~3 KRs max. Each KR maps to a KPI-tree node. Review-mode checks: outcome vs. activity per KR, ambition calibration (sandbagging vs. fantasy — ask for the baseline and trajectory), and whether anyone would behave differently if the OKR were deleted (if not, cut it).

## Instrumentation / tracking plan

For any feature or product needing measurement, produce the tracking plan as a table:

| Event | Trigger (exact) | Properties | Question it answers |
|---|---|---|---|

Discipline: name events `object_action` (`report_exported`), present-tense triggers at the moment of user intent completion, properties capture the segmentation you'll wish you had (plan, role, source, count). Every event must answer a named question — events without questions are storage costs. Include the identity spine (user/account IDs, joins to revenue data) and a verification step: fire each event in staging and confirm receipt before launch counts on it.

## Dashboard design

A dashboard answers a standing question for a specific audience: exec (is the strategy working — North Star + tree level 1, monthly), team (is our area healthy — their subtree + funnel, weekly), launch (is this rollout working — adoption funnel + guardrails, daily, retired after stabilization). Per metric shown: comparison context (target, trend, cohort) — a number without comparison is decoration. Annotate known causes (launches, seasonality, incidents) so the dashboard accumulates institutional memory.

## Diagnosing metric movements

When asked "why did X move": segment before theorizing (the move is almost always concentrated — by platform, channel, geo, cohort, plan); check the boring causes first in order: instrumentation change/breakage (the #1 cause of dramatic moves), mix shift (denominator changed composition), seasonality/calendar, recent launches/flags, then real behavior change. Quantify the move's concentration ("80% of the drop is iOS organic signups post-14.2") before any narrative. Recommend the confirming check for the leading hypothesis.

## Quality bar

- North Star measures delivered value and ships with a counterweight guardrail
- Every tree node has an owner and connects to action; tree fits on a page
- KRs are outcomes with baselines, not shipped artifacts
- Every event in a tracking plan answers a named question; verification before launch
- Metric diagnoses segment first, check instrumentation first, narrative last
