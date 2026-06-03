---
title: "Schrepel — Building a Digital Brain for Research"
tags: [llm, knowledge-management, knowledge-graph, research-methodology, legal-tech, antitrust, source]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Schrepel — Building a Digital Brain for Research

Summary of **Thibault Schrepel**, *"Building a Digital Brain for Research: A Guide to
Queryable Knowledge Graphs"* (April 2026; forthcoming, *Network Law Review*, Spring
2026). The paper documents a reproducible pipeline that turns a folder of PDFs into a
queryable [[knowledge-graph]] + wiki, and extends [[andrej-karpathy]]'s
[[digital-brain]] / [[llm-knowledge-base]] methodology from a *retrieval* system into a
*hypothesis-generation* instrument.

## What a "digital brain" is

A personal knowledge infrastructure built from documents you trust: it maps connections
between sources, surfaces patterns and inconsistencies, and generates answers on demand
with references to the underlying material. The output is "a private, queryable
Wikipedia" that generates wiki pages on demand, each feeding back into the corpus. See
[[digital-brain]].

## The five-step pipeline (+ maintenance)

1. **Collect** — gather source PDFs, organized into thematic subfolders.
2. **Convert** — PDFs → Markdown via [[markitdown]] (Microsoft), automated and parallel.
3. **Graph** — build a [[knowledge-graph]] with [[graphify]] (Safi Shamsi), which
   dispatches up to 31 parallel AI agents to extract concepts/relationships, merges into
   a NetworkX graph, clusters with **Leiden community detection**, and exports
   interactive HTML + queryable JSON + a Markdown audit report.
4. **Wiki** — generate Wikipedia-style articles per thematic cluster, cross-linked, with
   a master index ([[centrality-weighted-wiki-generation]]).
5. **Query** — ask questions of the corpus through Claude Code; answers are grounded
   exclusively in the source documents (graph navigation constrains the AI to extracted
   content).
- **Maintenance** — drop new documents in and re-run; an SHA-256 cache means only
  new/changed files are reprocessed, so sessions resume exactly where they left off.

Stack: Python 3.10+, [[markitdown]], [[graphify]], [[claude-code]], [[obsidian]].
Claude Pro suffices for a few hundred docs; Claude Max recommended for the initial
build. Scales from <5 min (20–100 docs) to ~1 day (10,000 docs).

## The author's six research-specific contributions

Schrepel is explicit that the underlying methodology is Karpathy's, Graphify is
Shamsi's, and MarkItDown is Microsoft's; his contribution is six *adaptations for
research*, not original technical work:

1. **Schema design procedure** ([[research-schema-design]]) — the `CLAUDE.md` schema is
   the only instrument to shape the graph *before* it is built. Four design choices:
   authority weighting, absence-as-a-query-target, conceptual anchors, and claim-level
   extraction.
2. **Centrality-weighted wiki generation** ([[centrality-weighted-wiki-generation]]) —
   each article is built primarily from the **["god nodes"](../concepts/god-nodes.md)**
   (most-connected sources) in its cluster, not from all sources equally.
3. **Six-step query protocol** ([[six-step-research-protocol]]) — turns the graph into a
   hypothesis-generation instrument.
4. **Claim-level extraction** ([[claim-level-extraction]]) — moves the unit of analysis
   from documents to propositions, exposing incompatibilities document-level graphs hide.
5. **Persistent hypothesis register** ([[hypothesis-register]]) — stores every
   query-generated conjecture in `hypotheses.md` and re-tests it as the corpus grows.
6. **Complexity-theoretic diagnostic layer** ([[graph-diagnostics]]) — measures the
   graph's network properties (scale-free? small-world? community entropy) and reports
   what they imply about the field.

## The six-step query protocol (the heart of the method)

Organized around an **["absence-first"](../concepts/absence-first-research.md)**
orientation — in a mature field, the most useful finding is a *gap*:
1. Identify the **god nodes** (highest-degree concepts) — what the field treats as
   foundational.
2. Identify **disconnected components** — frontiers and dead ends.
3. Query for **absent paths** — two concepts that theory says should connect but the
   literature hasn't (a paper waiting to be written).
4. **Cross-corpus divergence** — compare two graphs (e.g. scholarship vs. regulatory
   decisions) on the same domain.
5. **Authority-chain conflict check** — where different authority levels state
   contradictory positions (sites of doctrinal evolution).
6. **Health check** — concepts referenced everywhere but never defined (the field's
   assumed knowledge).

## Applied results & use cases

- On a **674-file research corpus** (~9.5M words / ~12.7M raw tokens): Graphify
  extracted ~56K tokens (225× compression) → 1,037 nodes, 1,231 edges, 80 communities,
  in 3–5 min with 31 parallel agents.
- A second implementation: a **European Commission competition-decisions** corpus
  (downloaded via a custom script from the EU Open Data Portal).
- Use cases: decision-consistency checks for agencies/courts, legal practice & peer
  review, team/institutional deployment (a regulator publishing a queryable corpus), and
  **regulatory mapping** across the eight EU digital regulations (DGA, DMA, DSA, DORA,
  Chips Act, Data Act, AI Act, CRA) to surface conflicting definitions and coverage gaps.

## Appendix findings (illustrative research notes)

- **Appendix A — Computational Antitrust** (synthesized across 508 EC decisions,
  1977–2025): the Commission's enforcement toolkit is predominantly **qualitative and
  documentary**. It *evaluates* parties' econometrics (e.g. critiquing Intel's
  regression in AT.37990) rather than *generating* its own; no cartel-screening
  algorithms, ML bid-rigging detection, or proprietary monitoring appear in the
  decisional record. Algorithms are the *object* of investigation (Google Ads, Amazon
  Buy Box), not the investigative tool. Google Adtech (2025) is the most technically
  sophisticated decision and may signal where the gap begins to close.
- **Appendix B — Ecosystem Analysis** (flagship digital decisions, 2004–2025): the
  Commission shows **emerging but inconsistent ecosystem thinking**. Apple Mobile
  Payments (AT.40452, 2024) is the only decision where ecosystem lock-in drives *market
  definition* (via an after-market analogy); elsewhere (Google Android, Google Adtech)
  ecosystem framing is background while abuse counts stay product-by-product. No unified
  ecosystem theory of harm; remedies are behavioural (access/interoperability), never
  structural separation.

## Relationship to Karpathy's post

This paper is the formalized, research-grade descendant of
[[karpathy-llm-knowledge-bases]]. Karpathy described an informal personal workflow;
Schrepel adds a named toolchain ([[graphify]] + [[markitdown]]), an explicit
[[knowledge-graph]] layer with centrality/community structure, and a research protocol.
Both keep a `raw/` folder of immutable sources and an LLM-maintained wiki, and both note
incremental, cache-backed updates. See [[karpathy-vs-schrepel-digital-brain]].

## Related Pages
- [[digital-brain]]
- [[knowledge-graph]]
- [[graphify]]
- [[markitdown]]
- [[thibault-schrepel]]
- [[research-schema-design]]
- [[six-step-research-protocol]]
- [[god-nodes]]
- [[centrality-weighted-wiki-generation]]
- [[claim-level-extraction]]
- [[hypothesis-register]]
- [[graph-diagnostics]]
- [[absence-first-research]]
- [[karpathy-llm-knowledge-bases]]
- [[karpathy-vs-schrepel-digital-brain]]
