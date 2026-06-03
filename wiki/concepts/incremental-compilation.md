---
title: "Incremental Compilation (of a wiki)"
tags: [llm, knowledge-management, workflow, concept]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/articles/Post by @karpathy on X.md]
---

# Incremental Compilation (of a wiki)

The process by which an LLM "compiles" raw source documents into a maintained
[[llm-knowledge-base]] — adding summaries, backlinks, concept articles, and updated
indexes one source at a time. Described by [[andrej-karpathy]] in
[[karpathy-llm-knowledge-bases]].

## How it works in practice

- **Human-in-the-loop, one source at a time.** It is *not* a fully autonomous pipeline.
  Karpathy adds every source manually and stays in the loop, especially in early stages.
- **The pattern bootstraps.** After a while the LLM "gets" the directory schema and
  conventions, and the marginal document becomes much easier — the prompt collapses to
  "file this new doc to our wiki: (path)."
- **Schema as anchor.** A kept-current schema file (`AGENTS.md` / `CLAUDE.md`) gives the
  LLM the conventions it needs to file consistently.

## Open tension: batch size

A commenter (Gavriel Cohen) noted that processing sources one-by-one can leave the LLM
without enough context to decide how to divide content into directories, and asked
whether there's an optimal batch size or multi-stage approach. Karpathy's answer
sidesteps batch size by relying on human-in-the-loop curation early, then easier
marginal ingests later. The optimal-batch-size question remains open — see
[[open-questions-llm-knowledge-bases]].

## Related Pages
- [[karpathy-llm-knowledge-bases]]
- [[llm-knowledge-base]]
- [[wiki-linting]]
- [[andrej-karpathy]]
- [[open-questions-llm-knowledge-bases]]
