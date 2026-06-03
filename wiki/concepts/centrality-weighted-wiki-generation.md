---
title: "Centrality-Weighted Wiki Generation"
tags: [knowledge-graph, wiki, centrality, concept]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Centrality-Weighted Wiki Generation

The second of Thibault Schrepel's six contributions in
[[schrepel-digital-brain-for-research]]. When generating the wiki from the
[[knowledge-graph]], each article draws its summary **primarily from the [[god-nodes]]**
(most-connected sources) in its thematic cluster, rather than weighting all sources
equally. Sources with few connections contribute less.

The rule lives in the `CLAUDE.md` schema as the **"Node Centrality Weighting"** block
(see [[research-schema-design]]) and is executed during wiki generation. For legal
corpora it combines with the authority hierarchy: give more weight both to the
most-connected documents and to higher-authority sources (e.g. court judgments). The
schema and the always-on graph hook "work together — the hook ensures the graph is
loaded, and the schema determines how it is used."

Effect: wiki articles foreground what the corpus's own link structure treats as central,
producing summaries anchored in consensus material rather than incidental sources.

## Related Pages
- [[schrepel-digital-brain-for-research]]
- [[god-nodes]]
- [[research-schema-design]]
- [[knowledge-graph]]
