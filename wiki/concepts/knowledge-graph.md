---
title: "Knowledge Graph"
tags: [knowledge-graph, network-science, retrieval, concept]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Knowledge Graph

A structured network of concepts, documents, and relationships extracted from a corpus.
In [[schrepel-digital-brain-for-research]] it is the layer that sits between the raw
documents and the generated wiki, built by [[graphify]] and stored as a **NetworkX**
graph clustered with [[leiden-community-detection]].

## Why it matters here

- **Grounding.** The AI navigates the graph to locate relevant nodes before answering,
  which constrains it to content already extracted from the documents — every claim is
  traceable to a source.
- **Structure as signal.** The graph exposes [[god-nodes]] (highest-degree, most
  foundational), disconnected components (frontiers/dead ends), absent paths (gaps), and
  communities (thematic clusters). These structural features power the
  [[six-step-research-protocol]] and the [[absence-first-research]] orientation.
- **Compression.** On a 674-file corpus (~12.7M raw tokens), extraction produced only
  ~56K tokens (225× compression) → 1,037 nodes, 1,231 edges, 80 communities.

## Outputs

`graph.html` (interactive), `graph.json` (queryable, GraphRAG-ready), and
`GRAPH_REPORT.md` (audit report with god nodes, surprising connections, suggested
research questions, and the [[graph-diagnostics]] metrics).

## Relation to RAG

The graph is a structured alternative/complement to vector-based
[[retrieval-augmented-generation]]: Schrepel calls the JSON output "GraphRAG-ready," and
graph navigation finds documents that are structurally connected to a concept even when
they never use the exact term.

## Related Pages
- [[schrepel-digital-brain-for-research]]
- [[graphify]]
- [[leiden-community-detection]]
- [[god-nodes]]
- [[graph-diagnostics]]
- [[six-step-research-protocol]]
- [[retrieval-augmented-generation]]
