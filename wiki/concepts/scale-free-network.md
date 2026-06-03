---
title: "Scale-Free Network"
tags: [network-science, knowledge-graph, diagnostics, concept]
date_created: 2026-05-31
date_updated: 2026-05-31
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Scale-Free Network

A network whose **degree distribution follows a power law**: a small number of nodes
(hubs) accumulate a disproportionate share of the connections, with a long tail of nodes
having few connections each. One of the network-science benchmarks in the
[[graph-diagnostics]] module of [[schrepel-digital-brain-for-research]].

## Why it matters here

- The hubs of a scale-free [[knowledge-graph]] are exactly its **[[god-nodes]]** — the
  most-connected, foundational documents/concepts.
- "Most mature scholarly fields are scale-free." A corpus that produces a scale-free
  degree distribution has found its centers.
- A **flat** degree distribution (not scale-free) is itself a finding: it "usually means
  the extraction has missed" the field's centers — i.e. a diagnostic of a *bad graph*
  rather than a *flat field*.

Measured from the graph's degree distribution; reported in `GRAPH_REPORT.md` after each
build. Complements the [[small-world-network]] test (clustering + path length) and
community entropy.

## Related Pages
- [[graph-diagnostics]]
- [[small-world-network]]
- [[god-nodes]]
- [[knowledge-graph]]
- [[schrepel-digital-brain-for-research]]
