---
title: "Six-Step Research Protocol"
tags: [knowledge-graph, research-methodology, hypothesis-generation, concept]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Six-Step Research Protocol

The third of Thibault Schrepel's six contributions in
[[schrepel-digital-brain-for-research]], and the heart of the method. It is a sequence of
queries that turns a completed [[knowledge-graph]] from a *retrieval system* into a
*hypothesis-generation instrument*. The protocol does not modify the pipeline; it
specifies how to query the graph once built. Run in sequence, the six steps produce "a
structured research agenda — a map of what the field has established, where its frontiers
lie, and which connections it has failed to make."

## The six steps

1. **Identify the god nodes** — highest-degree concepts; what the field treats as
   foundational. (`/graphify query "what are the most connected nodes in the graph"`)
   See [[god-nodes]].
2. **Identify disconnected components** — clusters with no connection to the main corpus:
   emerging subfields, abandoned arguments, or unencountered work. Each is a research
   question. (`/graphify query "identify disconnected components"`)
3. **Query for absent paths** — pairs of nodes that *should* connect on theoretical
   grounds but don't. An absent path is a finding — a paper waiting to be written. (The
   paper's example: no path between the Collingridge Dilemma and Arthur's technology
   lock-in theory.) (`/graphify query "identify absent paths in the graph"`)
4. **Cross-corpus divergence** (needs two graphs) — compare two corpora on the same
   domain (e.g. scholarship vs. regulatory decisions). Concepts dense in one but isolated
   in the other are candidates for adoption/theorization.
5. **Authority-chain conflict check** (legal corpora) — find nodes where different
   authority levels state contradictory positions; these are sites of doctrinal
   evolution. Surfaced automatically when the authority hierarchy is in the schema.
6. **Health check** — concepts referenced everywhere but never defined (many incoming
   edges, no outgoing edges, no defining article): the field's *assumed knowledge*.
   (`/graphify query "concepts mentioned frequently but never defined"`)

## Orientation and outputs

The protocol embodies an [[absence-first-research]] orientation. Each run produces a set
of hypotheses (an absent path, a god node, a disconnected cluster, an undefined concept),
stored and re-tested via the [[hypothesis-register]]. Applied to an institution's own
decisional corpus, it yields an [[institutional-memory-audit]] (which decisions are
foundational, which doctrines were started and abandoned).

## Related Pages
- [[schrepel-digital-brain-for-research]]
- [[god-nodes]]
- [[absence-first-research]]
- [[hypothesis-register]]
- [[institutional-memory-audit]]
- [[knowledge-graph]]
- [[claim-level-extraction]]
