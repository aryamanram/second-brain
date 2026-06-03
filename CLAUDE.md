# LLM Wiki Schema

## Overview
This is a personal knowledge base.
The wiki is maintained by you (the LLM). The human collects sources and asks questions.
You do all summarizing, cross-referencing, filing, and maintenance.

## Directory Structure
- `raw/` — Immutable source documents. Never modify these.
- `wiki/` — Your domain. You create and maintain all pages here.
  - `wiki/sources/` — One summary per raw source.
  - `wiki/entities/` — People, companies, orgs, projects.
  - `wiki/concepts/` — Ideas, frameworks, techniques.
  - `wiki/syntheses/` — Cross-cutting analyses.
  - `wiki/comparisons/` — X vs Y pages.
  - `wiki/questions/` — Open questions and research gaps.
- `index.md` — Master index. Update after every ingest.
- `log.md` — Append-only operation log.

## Page Format
Every wiki page should have:
- A YAML frontmatter block with: title, tags, date_created, date_updated, sources
- Wikilinks using [[double brackets]] to connect related pages
- A "Related Pages" section at the bottom

Example:
---
title: "Transformer Architecture"
tags: [deep-learning, attention, neural-networks]
date_created: 2026-04-15
date_updated: 2026-04-15
sources: [raw/papers/attention-is-all-you-need.md]
---

## Naming Conventions
- Source pages: `wiki/sources/[source-title-slugified].md`
- Entity pages: `wiki/entities/[entity-name-slugified].md`
- Concept pages: `wiki/concepts/[concept-name-slugified].md`
- Use lowercase, hyphens for spaces, no special characters.

## Ingest Workflow
When told to ingest a new source:
1. Read the raw source file completely.
2. Discuss key takeaways with the human.
3. Create a summary page in `wiki/sources/`.
4. Create or update relevant entity pages in `wiki/entities/`.
5. Create or update relevant concept pages in `wiki/concepts/`.
6. Add [[wikilinks]] between all related pages.
7. Update `index.md` with new pages.
8. Append an entry to `log.md`.

## Query Workflow
When asked a question:
1. Read `index.md` to find relevant pages.
2. Read those pages.
3. Synthesize an answer with [[wikilinks]] as citations.
4. If the answer is substantial, offer to save it as a new wiki page.

## Lint Workflow
When asked to lint or health-check:
1. Check for broken [[wikilinks]].
2. Find orphan pages (no inbound links).
3. Look for contradictions between pages.
4. Identify important concepts mentioned but lacking their own page.
5. Suggest new questions to investigate or sources to find.
6. Report findings and offer to fix issues.

## Rules
- Never modify files in `raw/`. They are immutable.
- Always use [[wikilinks]] to connect related concepts.
- Flag contradictions explicitly — don't silently overwrite.
- When new information contradicts old, note both and mark the conflict.
- Keep summaries concise but thorough.
- Prefer specificity over vagueness.

## Search Tooling

This wiki has qmd installed for search. Use it instead of manually scanning files.

**Available commands:**
- `qmd search "keywords" -c wiki` — BM25 keyword search (fast, exact terms)
- `qmd search "keywords" -c raw` — Search raw sources
- `qmd query "natural language question"` — Semantic search with LLM reranking
- `qmd embed` — Re-index after ingesting new sources (run after every ingest)

**Collections:**
- `raw` — points to raw/ (immutable sources)
- `wiki` — points to wiki/ (LLM-maintained pages)

**Workflow update:**
- After every ingest, run `qmd embed` to keep the search index current.
- When answering queries, use `qmd query` to find relevant pages instead of reading index.md alone.