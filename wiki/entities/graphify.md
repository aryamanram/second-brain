---
title: "Graphify"
tags: [tool, knowledge-graph, claude-code, skill, entity]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Graphify

An AI coding-assistant **skill** (runs inside [[claude-code]]) that reads a folder of
files and produces a [[knowledge-graph]]. Developed by **[[safi-shamsi]]**
(github.com/safishamsi/graphify, MIT license; >27,000 GitHub stars as of April 2026).
Install: `pip install graphifyy` (note the double "y"), then `graphify install`.

It is the core graph-building component of the pipeline in
[[schrepel-digital-brain-for-research]].

## How it works

Three passes:
1. **Deterministic AST pass** — extracts structure from code files without AI.
2. **Semantic pass** — dispatches parallel AI agents (up to 31 simultaneously); each
   extracts concepts and relationships from its assigned documents and returns
   structured JSON.
3. **Merge** — payloads merged into a **NetworkX** graph, clustered with
   [[leiden-community-detection]], exported as interactive HTML (`graph.html`), queryable JSON
   (`graph.json`, GraphRAG-ready), and a Markdown audit report (`GRAPH_REPORT.md`).

## Key features

- **SHA-256 cache** — each document is processed once and cached; re-runs resume exactly
  where prior sessions ended. Enables incremental, low-cost updates.
- **Query commands** — `/graphify query "..."` traces paths between nodes, finds
  disconnected components, surfaces [[god-nodes]], etc. (the backbone of the
  [[six-step-research-protocol]]).
- **Always-on integration** — `graphify claude install` adds a hook so Claude Code reads
  the graph report before answering, grounding responses in graph structure.
- `--update`, `--wiki`, `--watch`, and `graphify hook install` (rebuild on git commit)
  for maintenance. Supports an OpenAI-compatible mode (GPT Codex).

## Related Pages
- [[schrepel-digital-brain-for-research]]
- [[knowledge-graph]]
- [[markitdown]]
- [[claude-code]]
- [[safi-shamsi]]
- [[leiden-community-detection]]
- [[god-nodes]]
- [[six-step-research-protocol]]
