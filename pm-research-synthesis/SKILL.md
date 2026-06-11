---
name: pm-research-synthesis
description: Synthesize raw customer signal — interview notes, transcripts, survey results, support tickets, sales call notes, NPS verbatims, app reviews — into ranked insights, opportunity areas, and roadmap recommendations. Use this whenever the user has a pile of qualitative data to make sense of, says "synthesize", "what are the themes", "analyze this feedback", uploads interview notes or ticket exports, or needs to turn research into product decisions.
---

# Research Synthesis

Turn raw customer signal into insights that survive scrutiny. The failure mode to avoid: theme-counting that flattens everything into "users want better UX." The goal: insights specific enough that two PMs reading them would build the same thing.

## Before starting

1. **Get the raw data** — ask for files/transcripts/exports if not provided. Synthesis from the user's memory of the research is summary, not synthesis; say so and work with what exists.
2. **The decision at stake** — what will this synthesis inform? Roadmap input, problem prioritization, persona refinement, churn diagnosis?
3. **Data provenance** — how were participants selected, when was data collected, what segments are represented? This determines how far conclusions can stretch.

## Synthesis workflow

Work bottom-up. Do not start from hypothesized themes and sort evidence into them — that's how priors survive contact with data.

1. **Extract atomic observations** — one observation per data point: a verbatim quote or specific described behavior, tagged with source, segment, and context. Behaviors and past events outrank opinions; opinions outrank feature requests.
2. **Translate feature requests into problems** — every "I want X" gets rewritten as the underlying need ("I want Slack integration" → "I miss critical updates because I live in Slack, not your app"). Keep the original verbatim alongside.
3. **Cluster by underlying need**, not by topic or product area. "Slow exports" and "no API" can be the same need (get data into their own tooling) — topic-clustering would separate them.
4. **Name insights as findings, not categories.** "Onboarding" is a category. "Users who don't connect a data source in session one churn within two weeks because the empty state shows nothing to act on" is an insight.
5. **Count honestly** — frequency per insight, by segment, noting denominator ("6 of 9 enterprise interviewees" not "many users"). Note recruiting bias where it caps confidence.

## Ranking

Score each insight on:
- **Frequency** — how many independent sources, weighted by segment importance
- **Severity** — workarounds built, money spent, churn/deal-loss attributed, emotional intensity of language
- **Strategic fit** — does solving this serve the product's strategy, or a vocal segment off-strategy?
- **Confidence** — sample size, data quality, consistency across sources

Severity beats frequency for prioritization: five people building spreadsheet workarounds outrank twenty mild gripes.

## Output structure

```
# Research Synthesis: [Topic] — [Date]
## Data basis
[Sources, sample, collection period, known biases — up front, not buried]
## Key insights (ranked)
For each:
**Insight statement** [specific, falsifiable, in the form: WHO experiences WHAT, WHEN, causing WHAT consequence]
- Evidence: [frequency w/ denominator, 1-2 best verbatims, behavioral evidence]
- Severity signals: [workarounds, spend, churn links]
- Confidence: high/medium/low + why
## Contradictions & segment splits
[Where the data disagrees with itself — segment differences are often the real finding]
## Surprises
[What contradicted prior beliefs — flag explicitly; this is the highest-value section]
## What this means for the roadmap
[Insight → opportunity → candidate solution direction, clearly separating evidence from recommendation]
## What we still don't know
[Questions the data can't answer + cheapest next study to answer them]
```

## From insights to the opportunity space

Ranked insights map nearly 1:1 to opportunities on an opportunity solution tree — when the user wants to go from synthesis into solution exploration, opportunity mapping, or mentions OST/continuous discovery/Teresa Torres, hand off to the **pm-opportunity-mapping** skill, passing the ranked insights (with their frequency/severity/confidence scores) as the opportunity inputs. Don't build a one-off tree here; the tree is a maintained artifact and that skill owns its lifecycle.

## Quality bar

- Every insight backed by countable evidence with denominators; verbatims preserved
- Feature requests appear only in translated problem form (original noted)
- At least one contradiction or surprise surfaced — synthesis that's 100% confirmatory is suspect, and saying "this largely confirms X, with these caveats" is itself a finding
- Recommendations separated from evidence so readers can disagree with one without the other
- Never invent quotes or extrapolate beyond the data; small samples reported as small
