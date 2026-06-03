---
title: "Small-World Network"
tags: [network-science, knowledge-graph, diagnostics, concept]
date_created: 2026-05-31
date_updated: 2026-05-31
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Small-World Network

A network in which **most nodes can be reached from any other in a few steps** (short
mean path length) **and connections cluster locally** (high clustering coefficient). One
of the network-science benchmarks in the [[graph-diagnostics]] module of
[[schrepel-digital-brain-for-research]].

## Why it matters here

- The test combines two measured quantities of the [[knowledge-graph]]: the **clustering
  coefficient** and the **mean path length**. Satisfying both = small-world.
- "Most research fields satisfy both conditions." A graph that **fails** the small-world
  test is one "whose subcommunities are barely linked, and the failure is itself a
  finding" — it points to a fragmented literature (or, as with a flat degree distribution
  under [[scale-free-network]], to under-extraction).

Reported in `GRAPH_REPORT.md` after each build, alongside the scale-free check and
community entropy.

## Related Pages
- [[graph-diagnostics]]
- [[scale-free-network]]
- [[knowledge-graph]]
- [[schrepel-digital-brain-for-research]]
