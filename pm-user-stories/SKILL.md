---
name: pm-user-stories
description: Generate user stories and acceptance criteria from specs, PRDs, features, or ideas — epic breakdown, INVEST-quality stories, Gherkin (Given/When/Then) acceptance criteria, story mapping, slicing oversized stories, and backlog-ready output for Jira/Linear/ADO. Use this whenever the user needs user stories, acceptance criteria, epics, backlog items, story breakdown, says "break this down for the team", "write stories for", mentions Gherkin or story points, or has a PRD that needs converting into sprint-ready work.
---

# User Stories & Acceptance Criteria

Stories are a unit of *conversation and delivery*, not a requirements format with extra ceremony. Good ones are vertically sliced (each delivers observable user value end-to-end), independently shippable, and carry acceptance criteria precise enough that "done" isn't a negotiation.

## Before starting

1. **The source material** — PRD, feature description, or idea. If it's a PRD, mine it fully (scenarios → epics; requirements → stories; edge cases → acceptance criteria). If it's a sentence, expand scope with the user before decomposing.
2. **Team conventions** — tracker (Jira/Linear/ADO), story format preferences, estimation practice, definition of done. Match their dialect; offer CSV/markdown formatted for direct import when useful.
3. **The actual users** — get real role names. "As a user" is a smell; "as an account admin", "as a first-time visitor", "as the on-call engineer" change what gets built.

## Decomposition: feature → epics → stories

Slice **vertically by user value**, never horizontally by layer. "Build the API" + "build the UI" are tasks inside a story, not stories — neither alone changes anything for a user.

Slicing strategies for oversized stories, in order of preference:
1. **By workflow step** — each step of the journey that's independently observable
2. **By business rule** — happy path first, then each rule variation as its own story
3. **By data variation** — one input type first, then extend
4. **By quality level** — manual/slow version first, optimized version later (real shippable increments, not "do it badly then redo it")
5. **By persona** — core role first, then adjacent roles
Never slice by: layer, CRUD-operation-per-story when the user job needs all of them at once, or "part 1/part 2".

Apply INVEST as the test: Independent, Negotiable, Valuable, Estimable, Small (fits in a few days), Testable. If a story fails Valuable, it's a task — nest it under a story rather than promoting it.

## Story format

```
[STORY-ID] As a [specific role], I want [capability], so that [outcome the role actually cares about]

**Context**: [1-3 sentences: why this story exists, link to PRD section]
**Acceptance criteria**: [see below]
**Edge cases covered**: [which PRD edge cases land in this story]
**Out of scope**: [what an eager engineer might include but shouldn't — points to the story where it lives]
**Dependencies**: [story IDs or external]
**Suggested size**: [if the team estimates — with the reasoning, flagged as PM-guess pending team input]
```

The "so that" clause must carry real information — if it just restates the want ("so that I can have the feature"), dig until the actual outcome surfaces, or the story's value is unverified.

## Acceptance criteria

Default to Gherkin for behavior, checklist for qualities:

```gherkin
Scenario: [meaningful name]
  Given [precondition incl. data state]
  When [the action]
  Then [observable outcome — what the user sees/gets, not what the system does internally]
```

Coverage discipline per story: the happy path, each business-rule variation, the relevant unhappy paths (invalid input, permission denied, empty state, failure mode), and boundary values where numbers exist (limits, truncation, pagination edges). 3–8 scenarios per story is the healthy range — more means the story should split; one means edge cases are missing.

Non-behavioral criteria (performance, accessibility, telemetry) go in a checklist: measurable, with numbers. **Every story that introduces user-facing behavior includes a telemetry criterion** — events fired with what properties — because untracked features can't be measured against the PRD's success metrics.

## Epic-level output

When breaking down a full feature, lead with a story map: backbone (user activities, left to right) × slices (releases, top to bottom). The first horizontal slice = the walking skeleton (thinnest end-to-end path). Then list epics with goal + metric link, then stories in slice order with IDs and dependencies, ready for tracker import. State explicitly which stories make up release 1.

## Quality bar

- Every story vertically sliced and INVEST-checked; no layer-stories, no "part 2" stories
- Specific roles everywhere; zero "as a user"
- Unhappy paths and boundaries in the AC, not just happy paths; PRD edge cases all land somewhere traceable
- Telemetry criteria on every behavior-changing story
- Out-of-scope notes prevent adjacent work from leaking in
- Output formatted for the team's actual tracker, importable without rework
