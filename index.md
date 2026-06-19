# Wiki Index

Master index of all pages in this knowledge base.
Updated by the LLM after every ingest operation.

## Sources

- [[karpathy-llm-knowledge-bases]] — Karpathy's X post on using LLMs to build/maintain personal knowledge bases (the pattern this wiki implements). `raw/articles/Post by @karpathy on X.md`
- [[schrepel-digital-brain-for-research]] — Schrepel's methodology guide turning a PDF corpus into a queryable knowledge graph + wiki; extends Karpathy into a research instrument. `raw/papers/Building a Digital Brain for Research.pdf`
- [[wikipedia-andrej-karpathy]] — Wikipedia biography of Karpathy: life, education, OpenAI/Tesla/Anthropic career, "vibe coding." `raw/articles/Andrej Karpathy.md`
- [[lazy-obsidian-method-brief]] — Bryce Robbie field note: a low-maintenance stack (Obsidian + Karpathy wiki + PARA + Graphify + QMD) with automated daily/nightly/weekly jobs. `raw/papers/obsidian-lazy-method-brief.pdf`

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
- [[bryce-robbie]] — Author of the "Lazy Obsidian Method" field note.
- [[kepano]] — Steph Ango; creator of Obsidian Skills.
- [[obsidian-skills]] — Kepano's vault workflow patterns (the "Workflow" layer).
- [[qmd]] — Markdown search/retrieval tool (by tobi); the search layer, also used by this wiki.
- [[james-stewart]] — Mathematician; lead author of *Calculus* (the textbook being ingested).
- [[isaac-newton]] — Co-inventor of calculus (1642–1727).
- [[gottfried-leibniz]] — Co-inventor of calculus (1646–1716).
- [[leonhard-euler]] — Euler's method for differential equations (1707–1783).
- [[johannes-kepler]] — Kepler's Laws of planetary motion (1571–1630).
- [[william-rowan-hamilton]] — quaternions, origin of the cross product (1805–1865).
- [[george-green]] — Green's Theorem (1793–1841).
- [[george-stokes]] — Stokes' Theorem (1819–1903).
- [[carl-friedrich-gauss]] — the Divergence Theorem (1777–1855).

## Books

- [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] — **fully ingested** chapter-by-chapter (vision render): Preview + Ch.1–16, single- and multivariable calculus. See [[stewart-calculus-9e/_progress|progress manifest]]. `raw/books/stewart-calculus-9e.pdf`

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
- [[lazy-obsidian-method]] — Bryce Robbie's low-maintenance recipe assembling existing tools around Karpathy's LLM-wiki idea.
- [[para-method]] — Projects/Areas/Resources/Archive folder taxonomy; the "Structure" layer.
- [[maintenance-cadence]] — Automated daily/nightly/weekly recurring jobs; the "lazy unlock."
- [[limit]] — The foundational concept of calculus; $f(x)$ approaching $L$ as $x\to a$ (ε–δ).
- [[continuity]] — "Limit equals function value"; no break in the graph.
- [[intermediate-value-theorem]] — A continuous function on $[a,b]$ attains every value between $f(a)$ and $f(b)$.
- [[squeeze-theorem]] — A function trapped between two others sharing a limit shares that limit.
- [[derivative]] — Instantaneous rate of change / tangent slope; limit of difference quotients.
- [[chain-rule]] — Differentiates compositions; reversed, it is $u$-substitution.
- [[mean-value-theorem]] — Some interior tangent is parallel to the secant; the workhorse of differential calculus.
- [[antiderivative]] — Reverses differentiation; the indefinite integral $\int f\,dx = F+C$.
- [[definite-integral]] — A number: the limit of Riemann sums (area under a curve).
- [[riemann-sum]] — Rectangle-sum approximation whose limit defines the integral.
- [[fundamental-theorem-of-calculus]] — Differentiation and integration are inverse operations.
- [[gradient]] — Vector of partial derivatives; direction of steepest ascent (multivariable derivative).

## Syntheses

- [[llm-knowledge-base-toolchain]] — How the tools, concepts, and people fit into one end-to-end system; the retrieval vs. research layers.

## Comparisons

- [[karpathy-vs-schrepel-digital-brain]] — Informal personal workflow vs. formal graph-based research methodology.

## Questions

- [[open-questions-llm-knowledge-bases]] — Batch size, RAG scaling limits, finetuning, the product opportunity.
- [[open-questions-digital-brain-research]] — Graph-vs-index by scale, extraction faithfulness, and the antitrust open threads.
