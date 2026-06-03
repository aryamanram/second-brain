---
title: "Open Questions: LLM Knowledge Bases"
tags: [questions, llm, knowledge-management]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/articles/Post by @karpathy on X.md]
---

# Open Questions: LLM Knowledge Bases

Research gaps surfaced by [[karpathy-llm-knowledge-bases]].

1. **Optimal batch size for ingest.** Processing sources one-by-one can leave the LLM
   without enough context to decide directory structure, but large batches lose the
   human-in-the-loop curation. Is there an optimal batch size or multi-stage approach?
   (Raised by commenter Gavriel Cohen; unresolved.) See [[incremental-compilation]].
2. **When does index-and-summarize stop scaling?** Karpathy found no need for
   [[retrieval-augmented-generation]] at ~100 articles / ~400K words. At what corpus
   size does lightweight index reading break down and full RAG become necessary?
3. **Synthetic data + finetuning.** Karpathy flags as a "further exploration" generating
   synthetic data from the wiki and finetuning so the LLM "knows" the corpus in its
   weights rather than its context window. What does this pipeline look like, and when
   is it worth it versus context-window retrieval?
4. **What does the "incredible new product" look like?** Both Karpathy and commenters
   see a product opportunity (see [[raw-directory-as-product]]) beyond a hacky
   collection of scripts — especially for non-developers. What are its core primitives?

## Related Pages
- [[karpathy-llm-knowledge-bases]]
- [[llm-knowledge-base]]
- [[incremental-compilation]]
- [[retrieval-augmented-generation]]
- [[raw-directory-as-product]]
- [[open-questions-digital-brain-research]]
