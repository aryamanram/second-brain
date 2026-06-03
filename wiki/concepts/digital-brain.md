---
title: "Digital Brain"
tags: [llm, knowledge-management, knowledge-graph, concept]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Digital Brain

A term **coined by [[andrej-karpathy]]** for a personal knowledge infrastructure built
from documents you trust. As defined in [[schrepel-digital-brain-for-research]], a
digital brain:

- maps connections between sources,
- surfaces patterns and inconsistencies,
- generates answers on demand with references to the underlying material,
- builds more connections the more it is used, and
- produces, on demand, wiki pages on any theme in the corpus — each new page feeding
  back into the knowledge base.

The output is described as "a private, queryable Wikipedia."

## Relationship to other concepts

A digital brain is the same family of system as an [[llm-knowledge-base]]: an immutable
`raw/` corpus plus an LLM-maintained wiki. Schrepel's contribution is to add an explicit
[[knowledge-graph]] layer (via [[graphify]]) between the raw documents and the wiki, and
a research protocol on top (see [[six-step-research-protocol]]). Karpathy's original
formulation (informal, no named graph tool) is in [[karpathy-llm-knowledge-bases]];
the two are compared in [[karpathy-vs-schrepel-digital-brain]].

## Related Pages
- [[schrepel-digital-brain-for-research]]
- [[llm-knowledge-base]]
- [[knowledge-graph]]
- [[andrej-karpathy]]
- [[karpathy-vs-schrepel-digital-brain]]
