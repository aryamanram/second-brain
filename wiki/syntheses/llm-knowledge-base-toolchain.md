---
title: "The LLM Knowledge-Base Toolchain"
tags: [synthesis, llm, knowledge-management, knowledge-graph, tooling]
date_created: 2026-06-01
date_updated: 2026-06-01
sources: [raw/articles/Post by @karpathy on X.md, raw/papers/Building a Digital Brain for Research.pdf, raw/articles/Andrej Karpathy.md]
---

# The LLM Knowledge-Base Toolchain

A cross-cutting view of how the individual tools, concepts, and people in this wiki fit
together into a single working system: an LLM-maintained knowledge base built from an
immutable corpus. It draws the [[llm-knowledge-base]] / [[digital-brain]] idea together
with the concrete software that implements it.

## The pipeline, end to end

Both [[karpathy-llm-knowledge-bases]] (informal) and
[[schrepel-digital-brain-for-research]] (formalized) describe the same shape — raw
documents in, a queryable wiki out — but Schrepel names a specific toolchain for each
stage. Mapped to the tools in this wiki:

| Stage | What happens | Tool(s) |
|---|---|---|
| **Collect** | Trusted sources land in an immutable `raw/` folder | (manual; web clippers; scripted downloads) |
| **Convert** | PDFs/Office docs → clean Markdown | [[markitdown]] (Microsoft) |
| **Graph** | Extract concepts + relationships into a structured network | [[graphify]] (by [[safi-shamsi]]) → NetworkX + [[leiden-community-detection]] |
| **Wiki** | Each thematic cluster becomes a cross-linked article | [[centrality-weighted-wiki-generation]] anchored on [[god-nodes]] |
| **Query** | Natural-language questions grounded in the corpus | [[claude-code]] navigating the [[knowledge-graph]] |
| **View** | Browse raw + wiki + graph | [[obsidian]] (graph view mirrors the community structure) |
| **Maintain** | Re-run incrementally; only changed files reprocessed | SHA-256 cache; [[incremental-compilation]] |

The AI runtime threading these together is [[claude-code]] (Anthropic), with the schema
held in a `CLAUDE.md` / `AGENTS.md` file the LLM reads before acting.

## Two layers: retrieval vs. research

The toolchain has two distinguishable layers, and the wiki's sources sit at different
points on it:

1. **The retrieval layer** (Karpathy's core claim). At small scale (~100 articles), an
   LLM auto-maintaining **index files + per-document summaries** is enough to answer
   complex questions — no fancy [[retrieval-augmented-generation]] required. This is the
   layer *this very wiki* runs on, plus the `qmd` search tool.
2. **The research layer** (Schrepel's contribution). Adding an explicit
   [[knowledge-graph]] turns the system from a retrieval tool into a
   hypothesis-generation instrument via the [[six-step-research-protocol]], with the
   [[hypothesis-register]] and [[graph-diagnostics]] preserving and measuring findings
   over time. Its orientation is [[absence-first-research]] — the most useful output is a
   structural map of what the corpus *doesn't* say.

The boundary between the two is a scale/purpose question (see
[[karpathy-vs-schrepel-digital-brain]] and the open questions below): index-and-summarize
suffices until the corpus is large enough — or the task analytical enough — that the
graph earns its cost.

## The enabling assumption: vibe coding

A throughline across all three sources is [[vibe-coding]] (a term
[[andrej-karpathy]] coined). The custom CLIs that extend a knowledge base — Karpathy's
"small naive search engine," this wiki's `qmd`, Schrepel's corpus-download scripts — are
assumed to be cheaply vibe-coded. This is what makes the whole toolchain assemblable "by
someone comfortable with a computer" rather than a software team, and underwrites the
product thesis in [[raw-directory-as-product]].

## Who built the pieces

- [[andrej-karpathy]] — originated the [[digital-brain]] / [[llm-knowledge-base]]
  methodology; coined [[vibe-coding]]; joined [[anthropic]] (maker of [[claude-code]]) in
  2026.
- [[thibault-schrepel]] — formalized the methodology into a reproducible research
  pipeline.
- [[safi-shamsi]] — built [[graphify]], the graph-extraction engine.
- **Microsoft** — [[markitdown]] (the conversion step).

## Open threads

- When does the retrieval layer stop scaling and the graph layer become necessary? (See
  [[open-questions-llm-knowledge-bases]], [[open-questions-digital-brain-research]].)
- Karpathy's "further exploration" — synthetic data + finetuning to bake a corpus into
  model weights — would add a *third* layer beyond retrieval and graph. His 2026 move to
  [[anthropic]]'s pretraining team makes this thread worth watching.

## Related Pages
- [[llm-knowledge-base]]
- [[digital-brain]]
- [[knowledge-graph]]
- [[karpathy-vs-schrepel-digital-brain]]
- [[karpathy-llm-knowledge-bases]]
- [[schrepel-digital-brain-for-research]]
- [[graphify]]
- [[markitdown]]
- [[claude-code]]
- [[obsidian]]
- [[vibe-coding]]
- [[six-step-research-protocol]]
- [[retrieval-augmented-generation]]
