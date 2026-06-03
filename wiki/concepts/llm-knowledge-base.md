---
title: "LLM Knowledge Base"
tags: [llm, knowledge-management, workflow, concept]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/articles/Post by @karpathy on X.md]
---

# LLM Knowledge Base

A personal knowledge base that an **LLM builds and maintains** from a corpus of raw
source documents, producing a navigable wiki of markdown pages. Articulated by
[[andrej-karpathy]] in [[karpathy-llm-knowledge-bases]]; it is the pattern this wiki
implements. A closely related, more formalized variant — adding an explicit
[[knowledge-graph]] layer — is the **[[digital-brain]]** described in
[[schrepel-digital-brain-for-research]] (compared in
[[karpathy-vs-schrepel-digital-brain]]).

## Shape of the system

- **`raw/`** — immutable source documents (articles, papers, repos, datasets, images).
- **Compiled wiki** — a tree of `.md` files the LLM generates: per-source summaries,
  backlinks, and concept articles that categorize and cross-link the material.
- **Index + summaries** — auto-maintained index files and brief per-document summaries
  serve as lightweight retrieval, often removing the need for fancy
  [[retrieval-augmented-generation]] at small scale.
- **Frontend** — [[obsidian]] (or similar) for human viewing; the LLM does the writing.
- **Schema** — kept current in an agent-instructions file (`AGENTS.md` for Karpathy;
  `CLAUDE.md` here).

## Key properties

- **LLM-owned.** The human collects sources and asks questions; the LLM does all
  summarizing, cross-referencing, filing, and maintenance.
- **Compounding.** Query outputs are filed back into the wiki, so explorations
  accumulate value over time.
- **Simple and flat.** A nested directory of `.md`/`.png`/`.csv`/`.py` beats elaborate
  tooling; LLMs handle plain file trees easily.
- **Scales surprisingly far without RAG.** ~100 articles / ~400K words remained
  answerable via index + summary reading.

## Lifecycle

Built via [[incremental-compilation]], kept healthy via [[wiki-linting]], queried via
agentic Q&A, with a possible long-term path to synthetic data + finetuning so the model
"knows" the corpus in its weights. For how the concrete tools at each stage fit together,
see [[llm-knowledge-base-toolchain]].

## Related Pages
- [[karpathy-llm-knowledge-bases]]
- [[andrej-karpathy]]
- [[digital-brain]]
- [[schrepel-digital-brain-for-research]]
- [[llm-knowledge-base-toolchain]]
- [[knowledge-graph]]
- [[karpathy-vs-schrepel-digital-brain]]
- [[incremental-compilation]]
- [[wiki-linting]]
- [[retrieval-augmented-generation]]
- [[raw-directory-as-product]]
- [[obsidian]]
