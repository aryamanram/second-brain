---
title: "MarkItDown"
tags: [tool, markdown, pdf, ingest, entity]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# MarkItDown

A Python utility developed by **Microsoft** (github.com/microsoft/markitdown, MIT
license; >110,000 GitHub stars as of April 2026) that converts documents to Markdown.
Supports PDF, Word, PowerPoint, Excel, HTML, and more. Install:
`pip3 install 'markitdown[pdf]'`.

In [[schrepel-digital-brain-for-research]] it is the **Convert** step: PDFs are
converted to Markdown before entering the [[knowledge-graph]], because feeding raw PDFs
to an LLM means it "reads layout noise rather than content" and consumes more tokens.
Markdown preserves document structure (headings, lists, tables) while removing layout
information (fonts, page breaks, columns) that carries no semantic value.

The guide runs it via a parallel `batch_convert.py` script with a `SKIP_DONE` flag so
conversion is safe to re-run after interruption.

## Related Pages
- [[schrepel-digital-brain-for-research]]
- [[knowledge-graph]]
- [[graphify]]
