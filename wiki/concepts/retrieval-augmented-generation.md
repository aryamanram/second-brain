---
title: "Retrieval-Augmented Generation (RAG)"
tags: [llm, retrieval, rag, concept]
date_created: 2026-05-30
date_updated: 2026-06-03
sources: [raw/articles/Post by @karpathy on X.md]
---

# Retrieval-Augmented Generation (RAG)

The technique of retrieving relevant documents (typically via embeddings / vector
search) and inserting them into an LLM's context to ground its answers, rather than
relying on the model's weights alone.

## Relevance to this wiki

In [[karpathy-llm-knowledge-bases]], [[andrej-karpathy]] expected to need "fancy RAG" to
query his [[llm-knowledge-base]], but found that at small scale (~100 articles / ~400K
words) it was unnecessary: the LLM auto-maintained **index files** and **brief
per-document summaries**, and read the important related pages easily. This positions
lightweight index-and-summarize as a simpler alternative to RAG for small corpora.

This repo nonetheless ships a search tool ([[qmd]]) offering both BM25 keyword search and
semantic ("query") search with LLM reranking — a pragmatic middle ground for when the
index-reading approach needs help at larger scale.

## Open question

At what corpus size does index-and-summarize stop scaling and full RAG become
necessary? See [[open-questions-llm-knowledge-bases]].

## Related Pages
- [[karpathy-llm-knowledge-bases]]
- [[llm-knowledge-base]]
- [[qmd]]
- [[open-questions-llm-knowledge-bases]]
