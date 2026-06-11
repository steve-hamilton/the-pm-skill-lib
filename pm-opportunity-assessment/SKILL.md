---
name: pm-opportunity-assessment
description: Build the business case for a product opportunity — opportunity sizing, revenue/cost modeling, strategic fit, risk assessment, and a clear go/no-go/test-first recommendation. Use this whenever the user needs to decide whether to invest in an initiative, justify a project to leadership, asks "should we build this", "is this worth it", mentions business case, opportunity assessment, ROI of a feature, or needs a one-pager to get funding for an idea.
---

# Opportunity Assessment

Produce the document that gets an honest funding decision made. An opportunity assessment is not a pitch — it earns credibility by making the case *against* visible alongside the case *for*. Modeled on Marty Cagan's opportunity assessment discipline plus real financial framing.

## Before starting

1. **The opportunity** — problem, target customer, rough solution direction, and what evidence already exists (discovery done? or is this pre-evidence?)
2. **The decision and audience** — who decides, what they care about (growth? margin? retention? strategic positioning?), and what size of investment is being requested
3. **Business model basics** — how the product makes money, current scale, rough unit economics. Needed to model impact in the company's own currency.

## Assessment structure

```
# Opportunity Assessment: [Name] — [Date]
## Recommendation
[GO / NO-GO / VALIDATE-FIRST, the size of bet, and the 2-3 sentence reasoning. First, not last — execs read the first half page.]
## Problem & who has it
[Problem statement, target segment, evidence quality: validated / signals / hypothesis]
## Value sizing
[See sizing rules below — show the model]
## Strategic fit
[Which company/product objective this serves; what it would mean to do this well; what it crowds out]
## Costs & risks
[Build estimate (range), ongoing costs (support, infra, maintenance — the part everyone forgets), opportunity cost (the named thing we won't do instead)]
## Key assumptions & kill criteria
[The 3-5 assumptions the case rests on, each with: current evidence, how to test cheaply, and the result that should kill the initiative]
## Alternatives considered
[Including 'do nothing' and 'partner/buy instead of build' — a case with no alternatives is a pitch]
## Decision requested
[Exactly what approval/resources are being asked for, and for what duration before re-review]
```

## Value sizing rules

Build the impact model as an explicit chain the reader can audit, e.g.:

> reachable users (40K active) × % affected by problem (30%, from support-ticket analysis) × adoption if shipped (25–50%, comparable feature benchmarks) × value per adoption ($X retention lift / conversion delta) = $Y–$Z annual range

- Always a range, never a point estimate. State which variable the range is most sensitive to.
- Tie each multiplier to its evidence source, or label it "assumed — needs validation."
- Translate to the audience's currency: revenue, retention, cost saved, or strategic option value (if claiming strategic value, name the future move it enables — "strategic" without a named follow-on move is a smell).
- Run the pessimistic case: if every assumption lands at the low end, is this still worth doing? Say so either way.

## Scoring the recommendation

The recommendation derives from evidence quality × impact size × reversibility:

- Strong evidence + meaningful impact → **GO**, sized to confidence
- Weak evidence + big potential → **VALIDATE-FIRST** with a specific test plan and budget (most common right answer; recommend a discovery sprint via pm-customer-discovery or experiments via pm-experiment-design)
- Any impact + evidence pointing away, or fails strategy screen → **NO-GO**, written respectfully but plainly

Reversible decisions deserve less analysis, not more — if the bet is small and reversible, say "this analysis is already more expensive than trying it" when true.

## Quality bar

- Recommendation on page one, with reasoning
- Impact model shows its arithmetic; every multiplier sourced or flagged as assumed
- Opportunity cost names the actual displaced alternative, not "other priorities"
- Kill criteria are pre-committed and specific
- The strongest argument against the recommendation appears in the doc, steel-manned
- Honest NO-GO and VALIDATE-FIRST calls are expected outputs, not failure modes
