---
name: pm-prd-writing
description: Write product specs and PRDs that engineering teams can build from — full PRDs, lean one-pagers, problem statements, scope definitions with goals/non-goals, success metrics, edge-case coverage, and phased delivery plans. Use this whenever the user needs a spec, PRD, product requirements, feature definition, says "spec this out", "write requirements for", needs to turn an idea or research into a buildable document, or wants an existing spec reviewed for gaps.
---

# PRD & Spec Writing

A PRD's job is to transmit *judgment*, not just requirements — so the team makes the same call the PM would when they hit the hundred decisions the doc doesn't cover. That means the why gets as much rigor as the what, and non-goals get as much rigor as goals.

## Before starting

1. **Problem evidence** — what's known about the problem and from where? A PRD built on an unvalidated problem should say so in its risks section, loudly.
2. **Solution maturity** — is the solution decided, or is this PRD the place where options get weighed? (Both are legitimate; mixing them silently is not.)
3. **Team context** — who builds this, what they already know, existing system constraints, design involvement. Calibrates how much detail is respect vs. micromanagement.
4. **Size the doc to the bet** — one-pager for a sprint-sized reversible change; full PRD for a quarter-sized investment. Offer the right size; don't default to maximal.

## Full PRD structure

```
# [Feature name] — PRD
**Owner / Status / Last updated / Reviewers**
## 1. Problem
[Who hurts, how much, evidence with links. The strongest verbatim or data point goes here. If evidence is thin: say so + what would firm it up]
## 2. Goals & success metrics
[2-4 goals max. Each goal → a metric → a target → when measured. Include the guardrail metrics (what must not regress) and the instrumentation needed to measure any of this — specced HERE, not after launch]
## 3. Non-goals
[What this deliberately doesn't do, especially the things people will ask about. Each with one line of why. This section prevents 80% of scope creep]
## 4. Users & scenarios
[Primary user + the 2-3 concrete scenarios this must nail, written as short narratives with real data shapes — not "user can configure settings"]
## 5. Solution overview
[The approach and the user-facing flow. Diagrams/wireframe descriptions where words strain. If options were considered, the losing options and why they lost — one paragraph each]
## 6. Requirements
[Grouped by scenario. Each requirement: testable, numbered for reference, tagged P0 (launch-blocking) / P1 (fast-follow) / P2 (someday). Behavior at boundaries specified: empty states, error states, permission boundaries, concurrent edits, scale limits, migration of existing data]
## 7. Edge cases & failure behavior
[The unhappy paths: what the user sees when things break, degrade, or arrive malformed. Engineers find missing edge cases at 2am; PRDs should find them first]
## 8. Phasing
[What ships in v1 vs follows. The v1 line drawn at "smallest thing that delivers the core scenario end-to-end" — not the smallest demoable thing]
## 9. Dependencies, risks & open questions
[Each open question: owner + needed-by date. An open question without an owner is a launch delay in disguise]
## 10. Launch & rollout
[Flag strategy, rollout stages, kill criteria, comms — or pointer to pm-launch-gtm for the full plan]
```

## One-pager (lean spec)

Problem (with evidence) → Proposed change → Success metric + guardrail → Non-goals → Requirements (P0 only, testable) → Edge cases → Open questions. One page is a hard limit; the constraint is the editing.

## Writing requirements well

- Testable means a QA engineer could write the pass/fail without asking: "loads in under 2s at p95 for accounts with 10K records", not "fast"
- Write behavior, not implementation — unless the implementation IS the requirement (compliance, API contracts); then say so explicitly
- For every requirement touching existing behavior, state the migration: what happens to current users/data/links on day one
- Numbers on everything quantifiable: limits, timeouts, truncation, pagination, retention

## Spec review mode

When reviewing an existing spec, check in order of damage: Is the problem evidenced or asserted? Do metrics have targets and instrumentation? Do non-goals exist? Are requirements testable (sample 5; if 3 fail, the section needs a rewrite)? Where are empty/error/permission/scale states? Is there a real v1 line? Open questions owned? Deliver as: blocking gaps / should-fix / polish, with rewritten examples for the worst offenders.

## Quality bar

- Someone outside the team could read the PRD and know what's being built, why, for whom, and what "working" means
- Every metric has instrumentation specced; every open question has an owner
- Non-goals section present and specific in every output, including one-pagers
- Edge cases addressed before engineers ask
- The doc transmits the reasoning, so the team can extrapolate the PM's intent to decisions the doc doesn't cover
