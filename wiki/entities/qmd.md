---
title: "QMD"
tags: [tool, search, markdown, retrieval, entity]
date_created: 2026-06-03
date_updated: 2026-06-03
sources: [raw/papers/obsidian-lazy-method-brief.pdf]
---

# QMD

A markdown search/retrieval tool (github.com/tobi/qmd, by **tobi**). In
[[lazy-obsidian-method-brief]] it is the **"Search" layer** of the
[[lazy-obsidian-method]] stack — "better markdown retrieval as the vault grows" — added
at step 7, after [[graphify]].

## Use in this wiki

This knowledge base itself runs `qmd` as its search tool (configured in `CLAUDE.md`). It
provides:
- `qmd search "keywords"` — BM25 keyword search (raw or wiki collections),
- `qmd query "..."` — semantic search with LLM reranking, and
- `qmd embed` / `qmd update` — re-indexing after each ingest.

So this brief names a tool the wiki already depends on; the ingest workflow runs
`qmd update` + `qmd embed` after every source is filed. Note that `qmd`'s `**/*.md` glob
means non-markdown raw sources (e.g. PDFs) are searchable via their wiki source page
rather than directly.

## Related Pages
- [[lazy-obsidian-method]]
- [[lazy-obsidian-method-brief]]
- [[graphify]]
- [[obsidian]]
- [[retrieval-augmented-generation]]
