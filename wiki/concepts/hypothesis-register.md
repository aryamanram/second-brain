---
title: "Hypothesis Register"
tags: [research-methodology, knowledge-graph, longitudinal, concept]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Hypothesis Register

The fifth of Thibault Schrepel's six contributions in
[[schrepel-digital-brain-for-research]]. A persistent store (`hypotheses.md`) of every
conjecture the [[six-step-research-protocol]] generates, re-tested as the corpus grows.

## What it stores

Each run of the protocol produces hypotheses — an absent path is a conjecture, a
[[god-nodes|god node]] is a structural claim about the field, a disconnected cluster is a
prediction that a body of work hasn't been integrated, an undefined-but-referenced
concept is a claim about the field's assumed knowledge. Each is stored as a **dated
entry** recording:
- the generating query,
- the graph state at the time, and
- the evidence the query returned.

## Re-testing over time

When the corpus is updated, the register re-runs each stored query against the new graph
and appends the result as a new dated entry. This accumulates into a **research diary**:
- a hypothesis that held in April 2026 and failed in April 2027 is a documented shift in
  the field;
- a hypothesis that survives two years of new material is a proposition the field has not
  contradicted.

Both outcomes are research findings. Implementation is "one instruction in `CLAUDE.md`
and a standing command to re-test on update" (part of [[research-schema-design]]).

## Related Pages
- [[schrepel-digital-brain-for-research]]
- [[six-step-research-protocol]]
- [[research-schema-design]]
- [[god-nodes]]
