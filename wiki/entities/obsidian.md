---
title: "Obsidian"
tags: [tool, markdown, knowledge-management, entity]
date_created: 2026-05-30
date_updated: 2026-06-03
sources: [raw/articles/Post by @karpathy on X.md, raw/papers/Building a Digital Brain for Research.pdf]
---

# Obsidian

A markdown-based note-taking / knowledge-management application built around a local
folder of `.md` files and double-bracket wikilinks. In the ingested source, [[andrej-karpathy]]
uses Obsidian as the **IDE "frontend"** for an [[llm-knowledge-base]]:

- Viewing raw data, the compiled wiki, and derived visualizations.
- Rendering data in other ways via plugins (e.g. **Marp** for slide shows).
- Viewing LLM outputs (markdown, slides, matplotlib images) that are then "filed" back
  into the wiki.

He deliberately avoids the Obsidian CLI to keep the system "super simple and flat" — the
wiki is just a directory of files the LLM maintains. This repo similarly uses Obsidian
(note the `.obsidian/` directory) as its frontend.

In [[schrepel-digital-brain-for-research]], Obsidian plays the same role: the `wiki/`
folder is opened "as vault," and Obsidian's **graph view** renders cross-links between
topic pages, mirroring the underlying [[knowledge-graph]] community structure.

## Related Pages
- [[karpathy-llm-knowledge-bases]]
- [[schrepel-digital-brain-for-research]]
- [[lazy-obsidian-method]]
- [[obsidian-skills]]
- [[andrej-karpathy]]
- [[llm-knowledge-base]]
- [[knowledge-graph]]
