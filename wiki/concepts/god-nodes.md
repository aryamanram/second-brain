---
title: "God Nodes"
tags: [knowledge-graph, network-science, centrality, concept]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# God Nodes

In [[schrepel-digital-brain-for-research]], **god nodes** are the highest-degree nodes
in a [[knowledge-graph]] — the documents or concepts to which the largest number of
other nodes connect. They reflect the field's consensus more than isolated documents,
and their centrality is **emergent**, not editorially imposed: it arises from the pattern
of citations and conceptual links across the whole corpus.

## How they are used

- **Wiki weighting.** Under [[centrality-weighted-wiki-generation]], each wiki article's
  summary is built primarily from the god nodes in its cluster; weakly connected sources
  contribute less. Encoded in `CLAUDE.md` as the "Node Centrality Weighting" rule.
- **Research signal.** Identifying god nodes is Step 1 of the
  [[six-step-research-protocol]] — it reveals what a field treats as foundational
  (e.g. a corpus organized around Gundlach & Foer (2006) vs. one organized around Intel
  AT.37990 reflects different underlying conceptions).
- **Institutional memory audit.** For an institution's own decisional corpus, the god
  nodes reveal which of its decisions its case law has treated as foundational.

A degree distribution with clear god nodes indicates a **scale-free** graph; a flat
distribution usually means extraction missed the field's centers (see
[[graph-diagnostics]]).

## Related Pages
- [[schrepel-digital-brain-for-research]]
- [[knowledge-graph]]
- [[centrality-weighted-wiki-generation]]
- [[six-step-research-protocol]]
- [[graph-diagnostics]]
