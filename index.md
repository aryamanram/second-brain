# Wiki Index

Master index of all pages in this knowledge base.
Updated by the LLM after every ingest operation.

## Sources

- [[karpathy-llm-knowledge-bases]] — Karpathy's X post on using LLMs to build/maintain personal knowledge bases (the pattern this wiki implements). `raw/articles/Post by @karpathy on X.md`
- [[schrepel-digital-brain-for-research]] — Schrepel's methodology guide turning a PDF corpus into a queryable knowledge graph + wiki; extends Karpathy into a research instrument. `raw/papers/Building a Digital Brain for Research.pdf`
- [[wikipedia-andrej-karpathy]] — Wikipedia biography of Karpathy: life, education, OpenAI/Tesla/Anthropic career, "vibe coding." `raw/articles/Andrej Karpathy.md`

## Entities

- [[andrej-karpathy]] — AI researcher (@karpathy); author of the LLM knowledge bases workflow; coined "digital brain" and "vibe coding."
- [[thibault-schrepel]] — Legal scholar (antitrust/computational antitrust); author of the digital-brain research guide.
- [[safi-shamsi]] — Developer of Graphify, the knowledge-graph builder.
- [[fei-fei-li]] — Computer-vision researcher; Karpathy's Stanford PhD adviser.
- [[graphify]] — AI-assistant skill (runs in Claude Code) that builds a knowledge graph from a file corpus.
- [[markitdown]] — Microsoft Python utility converting PDFs/Office docs to Markdown.
- [[claude-code]] — Anthropic's agentic coding assistant; the AI runtime for the pipeline (and this wiki).
- [[obsidian]] — Markdown knowledge-management app used as the wiki frontend.
- [[anthropic]] — AI company behind Claude/Claude Code; Karpathy joined its pretraining team in 2026.
- [[openai]] — AI lab Karpathy co-founded (2015–2017; returned 2023–2024).
- [[tesla]] — Where Karpathy was Director of AI / Autopilot Vision (2017–2022).
- [[eureka-labs]] — Karpathy's AI-education company (founded 2024).
- [[stanford-university]] — Karpathy's PhD (2015) and where he taught CS 231n; also Schrepel's affiliation.
- [[university-of-toronto]] — Karpathy's undergraduate institution (CS + Physics, 2009).

## Concepts

- [[llm-knowledge-base]] — LLM-built-and-maintained wiki compiled from raw sources.
- [[digital-brain]] — Karpathy-coined personal knowledge infrastructure; a "private, queryable Wikipedia."
- [[knowledge-graph]] — Structured network of concepts/documents extracted from a corpus; the layer between raw docs and wiki.
- [[incremental-compilation]] — Human-in-the-loop, one-source-at-a-time compilation of the wiki.
- [[wiki-linting]] — LLM health checks for data integrity and new-article candidates.
- [[raw-directory-as-product]] — "Every business has a raw/ directory; compiling it is the product."
- [[retrieval-augmented-generation]] — RAG, and why index-and-summarize beat it at small scale here.
- [[research-schema-design]] — Shaping the graph before it's built via the CLAUDE.md schema (Schrepel contribution 1).
- [[centrality-weighted-wiki-generation]] — Building each wiki article from its cluster's god nodes (contribution 2).
- [[six-step-research-protocol]] — Querying the graph to generate hypotheses, not just retrieve (contribution 3).
- [[claim-level-extraction]] — Moving the unit of analysis from documents to propositions (contribution 4).
- [[hypothesis-register]] — Persistent, re-tested store of query-generated conjectures (contribution 5).
- [[graph-diagnostics]] — Complexity-theoretic measurement of the graph's network properties (contribution 6).
- [[god-nodes]] — Highest-degree, most foundational nodes in the knowledge graph.
- [[absence-first-research]] — The principle that, in mature fields, the most useful finding is a gap.
- [[institutional-memory-audit]] — The six-step protocol applied to an institution's own decisional corpus.
- [[leiden-community-detection]] — Graph-clustering algorithm Graphify uses to form thematic clusters.
- [[scale-free-network]] — Power-law degree distribution; a graph-diagnostics benchmark.
- [[small-world-network]] — Short path length + high clustering; a graph-diagnostics benchmark.
- [[computational-antitrust]] — Appendix A finding: EC enforcement is documentary, not computational.
- [[ecosystem-theory-of-harm]] — Appendix B finding: EC ecosystem reasoning is emerging but fragmented.
- [[vibe-coding]] — Karpathy-coined term for building software by prompting AI; the enabling assumption behind these pipelines.

## Syntheses

- [[llm-knowledge-base-toolchain]] — How the tools, concepts, and people fit into one end-to-end system; the retrieval vs. research layers.

## Comparisons

- [[karpathy-vs-schrepel-digital-brain]] — Informal personal workflow vs. formal graph-based research methodology.

## Questions

- [[open-questions-llm-knowledge-bases]] — Batch size, RAG scaling limits, finetuning, the product opportunity.
- [[open-questions-digital-brain-research]] — Graph-vs-index by scale, extraction faithfulness, and the antitrust open threads.
