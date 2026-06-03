---
title: "Karpathy on LLM Knowledge Bases (X post)"
tags: [llm, knowledge-management, workflow, obsidian, rag, source]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/articles/Post by @karpathy on X.md]
---

# Karpathy on LLM Knowledge Bases (X post)

Summary of an X post by [[andrej-karpathy]] (published 2026-04-02) describing his
workflow for using LLMs to build and maintain personal [[llm-knowledge-base]]s. The
post is notable because it describes the exact pattern this wiki implements.

## Core idea

A growing share of Karpathy's LLM usage is shifting from *manipulating code* to
*manipulating knowledge* — stored as markdown and images — because recent LLMs are
good at it.

## The workflow, stage by stage

- **Data ingest** — Source documents (articles, papers, repos, datasets, images) are
  indexed into a `raw/` directory. An LLM then incrementally
  ["compiles"](../concepts/incremental-compilation.md) them into a wiki: a tree of
  `.md` files with summaries, backlinks, and concept articles that categorize and link
  the data. He uses the Obsidian Web Clipper to convert web articles to markdown and a
  hotkey to download related images locally so the LLM can reference them. See
  [[incremental-compilation]].
- **IDE** — [[obsidian]] is the frontend for viewing raw data, the compiled wiki, and
  derived visualizations. The LLM writes and maintains all wiki data; he rarely touches
  it directly. Plugins (e.g. Marp for slides) render data in other ways.
- **Q&A** — Once the wiki is large enough (his is ~100 articles / ~400K words), the
  agent can answer complex questions by reading the relevant pages. He expected to need
  fancy [[retrieval-augmented-generation]] but found auto-maintained index files and
  per-document summaries sufficient at this "~small scale."
- **Output** — Answers are rendered as markdown files, Marp slide shows, or matplotlib
  images, viewed back in Obsidian. Outputs are often "filed" back into the wiki, so
  explorations compound and "add up" in the knowledge base.
- **Linting** — LLM ["health checks"](../concepts/wiki-linting.md) find inconsistent
  data, impute missing data (with web search), and surface connections for new article
  candidates — incrementally improving data integrity. See [[wiki-linting]].
- **Extra tools** — He [[vibe-coding|vibe-codes]] additional tools, e.g. a small naive
  search engine over the wiki, used both via web UI and (more often) handed to an LLM via CLI for
  larger queries.
- **Further explorations** — As the repo grows, the natural next step is synthetic data
  generation + finetuning so the LLM "knows" the data in its weights, not just its
  context window.

## TLDR (his words)

Raw data from many sources is collected, compiled by an LLM into a `.md` wiki, operated
on by various CLIs for Q&A and incremental enhancement, all viewable in [[obsidian]].
The human rarely writes or edits the wiki — it's the domain of the LLM. He thinks there
is room for "an incredible new product instead of a hacky collection of scripts."

## Notable points from the comment thread

- **Incremental compilation is human-in-the-loop.** It is *not* fully autonomous. He
  adds every source manually, one at a time, staying in the loop especially early on.
  After a while the LLM "gets" the pattern and the marginal document becomes easy — he
  just says "file this new doc to our wiki: (path)." This argues against large batch
  ingests early. See [[incremental-compilation]].
- **Keep it simple and flat.** No Obsidian CLI; just a nested directory of `.md`,
  `.png`, a few `.csv`/`.py`, with the schema kept current in `AGENTS.md` (the analog
  of this repo's `CLAUDE.md`). LLMs handle this structure easily; custom functions are
  easy to vibe-code.
- **"Every business has a raw/ directory. Nobody's ever compiled it. That's the
  product."** (Krishna Tammireddy; Karpathy agreed.) See
  [[raw-directory-as-product]].
- Another commenter (Nico Cserepy) described maintaining a minimal set of yes/no
  decisions that "fully describe my telos" and dumping all generated data into S3
  tables to always have the right context.

## Related Pages
- [[andrej-karpathy]]
- [[llm-knowledge-base]]
- [[incremental-compilation]]
- [[wiki-linting]]
- [[raw-directory-as-product]]
- [[retrieval-augmented-generation]]
- [[vibe-coding]]
- [[obsidian]]
