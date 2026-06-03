---
title: "Wiki Linting / LLM Health Checks"
tags: [llm, knowledge-management, data-integrity, concept]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/articles/Post by @karpathy on X.md]
---

# Wiki Linting / LLM Health Checks

LLM-run "health checks" over an [[llm-knowledge-base]] that improve its data integrity
incrementally. From [[andrej-karpathy]]'s description in
[[karpathy-llm-knowledge-bases]].

## What the checks do

- Find **inconsistent data** / contradictions across pages.
- **Impute missing data**, often using web search.
- Surface **interesting connections** that become candidates for new articles.
- Suggest **further questions** to investigate.

Karpathy notes LLMs are "quite good at suggesting further questions to ask and look
into," making linting a generative as well as corrective step.

## In this wiki

The `CLAUDE.md` lint workflow operationalizes this: check for broken wikilinks,
find orphan pages (no inbound links), look for contradictions, identify important
concepts mentioned but lacking their own page, and suggest new questions or sources.

## Related Pages
- [[karpathy-llm-knowledge-bases]]
- [[llm-knowledge-base]]
- [[incremental-compilation]]
- [[andrej-karpathy]]
