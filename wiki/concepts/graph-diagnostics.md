---
title: "Complexity-Theoretic Graph Diagnostics"
tags: [network-science, knowledge-graph, diagnostics, concept]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Complexity-Theoretic Graph Diagnostics

The sixth of Thibault Schrepel's six contributions in
[[schrepel-digital-brain-for-research]]. A diagnostic module that runs after each graph
build and writes network-science measurements of the [[knowledge-graph]] into
`GRAPH_REPORT.md`. It assembles standard measurements into a module Graphify does not
produce by default — "one query run against the NetworkX graph that Graphify already
builds."

## The metrics and what they reveal

- **Degree distribution → [[scale-free-network|scale-free]]?** A scale-free graph has a
  few [[god-nodes]] with a disproportionate share of connections and a long tail. Most
  mature fields are scale-free. A *flat* distribution usually means extraction missed the
  field's centers.
- **Clustering coefficient + mean path length → [[small-world-network|small-world]]?** A
  small-world graph lets most nodes be reached in a few steps with locally clustered
  connections. Failure (barely linked subcommunities) is itself a finding.
- **Community entropy → concentrated or diffuse attention?** Low entropy = a field
  organized around a few dominant frames; high entropy = a field in broad exploration.
  The trend across successive builds shows whether the field is consolidating or
  expanding.
- **Pairwise comparison** (when more than one graph exists) — a scholarly vs. a
  regulatory graph on the same domain will diverge; each divergence is a diagnostic
  signal about the gap between the two institutional perspectives.

## Related Pages
- [[schrepel-digital-brain-for-research]]
- [[knowledge-graph]]
- [[scale-free-network]]
- [[small-world-network]]
- [[god-nodes]]
- [[six-step-research-protocol]]
