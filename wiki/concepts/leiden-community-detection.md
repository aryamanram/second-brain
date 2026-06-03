---
title: "Leiden Community Detection"
tags: [network-science, knowledge-graph, clustering, concept]
date_created: 2026-05-31
date_updated: 2026-05-31
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Leiden Community Detection

A graph-clustering algorithm that partitions a network into **communities** — densely
connected groups of nodes. In [[schrepel-digital-brain-for-research]], it is the step
[[graphify]] uses to cluster the merged **NetworkX** [[knowledge-graph]] before exporting
it. Each resulting community becomes a **thematic cluster**, and each thematic cluster
becomes a wiki article during [[centrality-weighted-wiki-generation]].

## Why it matters here

- **Thematic structure of the wiki.** The community partition is what gives the generated
  wiki its topic pages; on the 674-file research corpus, clustering produced **80
  communities** from 1,037 nodes.
- **Input to diagnostics.** The community partition feeds the **community entropy** metric
  in [[graph-diagnostics]] (low entropy = a field organized around a few dominant frames;
  high entropy = broad exploration), and disconnected communities are the target of
  Step 2 of the [[six-step-research-protocol]].
- **Visualization.** Communities are rendered as colors in the interactive `graph.html`
  and mirrored by the [[obsidian]] graph view of the wiki.

Leiden is a refinement of the older Louvain method, designed to avoid badly connected or
internally disconnected communities; the source names Leiden specifically as the
algorithm Graphify applies.

## Related Pages
- [[knowledge-graph]]
- [[graphify]]
- [[centrality-weighted-wiki-generation]]
- [[graph-diagnostics]]
- [[six-step-research-protocol]]
