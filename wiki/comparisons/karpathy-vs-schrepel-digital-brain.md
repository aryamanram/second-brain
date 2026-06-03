---
title: "Karpathy vs. Schrepel: Digital Brain Approaches"
tags: [comparison, llm, knowledge-management, knowledge-graph]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/articles/Post by @karpathy on X.md, raw/papers/Building a Digital Brain for Research.pdf]
---

# Karpathy vs. Schrepel: Digital Brain Approaches

Both [[karpathy-llm-knowledge-bases]] and [[schrepel-digital-brain-for-research]] describe
building an LLM-maintained wiki from an immutable `raw/` corpus. Schrepel explicitly
builds on Karpathy ("the methodology … was developed by Andrej Karpathy"). The
differences are in formalization, tooling, and purpose.

## Shared foundation

- Immutable `raw/` folder of trusted sources; an LLM-maintained wiki the human rarely
  edits directly.
- Schema kept in an agent-instructions file (`AGENTS.md` for Karpathy; `CLAUDE.md` for
  Schrepel and this repo).
- [[obsidian]] as the viewing frontend.
- Incremental, cache-backed updates; the marginal document is cheap to add.
- Outputs filed back into the wiki so the system compounds.

## Key differences

| Dimension | Karpathy (X post) | Schrepel (paper) |
|---|---|---|
| **Nature** | Informal personal workflow | Formal, reproducible methodology guide |
| **Domain** | General research interest | Research / legal-regulatory (field-neutral pipeline) |
| **Graph layer** | None named; relies on index files + summaries | Explicit [[knowledge-graph]] via [[graphify]] (NetworkX + Leiden) |
| **Ingest tooling** | Obsidian Web Clipper; manual | [[markitdown]] batch conversion; scripted corpus download |
| **Retrieval** | Index-and-summarize; "didn't need fancy RAG" | Graph navigation ("GraphRAG-ready"); structural, not keyword |
| **Purpose** | Q&A / retrieval + exploration | Retrieval *and* hypothesis generation ([[six-step-research-protocol]]) |
| **Unit of analysis** | Documents | Documents *and* propositions ([[claim-level-extraction]]) |
| **Rigor add-ons** | LLM "health checks" / linting | [[hypothesis-register]], [[graph-diagnostics]], authority weighting |
| **Scale cited** | ~100 articles / ~400K words | 674 files / ~9.5M words → 1,037 nodes, 80 communities |

## The throughline

Karpathy's "didn't need fancy RAG, index files sufficed" and Schrepel's explicit
knowledge graph represent two points on a spectrum. At small scale, auto-maintained
indexes work (see [[retrieval-augmented-generation]]); Schrepel's graph layer adds value
mainly when the goal shifts from *retrieving what's there* to *finding what's structurally
absent* ([[absence-first-research]]) and when corpora reach thousands of documents. The
open question of when index-and-summarize stops scaling (see
[[open-questions-llm-knowledge-bases]]) is partly answered by Schrepel's choice to add a
graph at the ~hundreds-to-thousands-of-documents range.

## Related Pages
- [[karpathy-llm-knowledge-bases]]
- [[schrepel-digital-brain-for-research]]
- [[digital-brain]]
- [[llm-knowledge-base]]
- [[llm-knowledge-base-toolchain]]
- [[knowledge-graph]]
- [[open-questions-llm-knowledge-bases]]
