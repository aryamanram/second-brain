# LLM Wiki Schema

## Overview
This is a personal knowledge base.
The wiki is maintained by you (the LLM). The human collects sources and asks questions.
You do all summarizing, cross-referencing, filing, and maintenance.

## Directory Structure
- `raw/` — Immutable source documents. Never modify these. Subfolders by type:
  - `raw/articles/`, `raw/papers/`, `raw/notes/`, `raw/transcripts/`, `raw/assets/` — shorter sources.
  - `raw/books/` — full-length books (often large, graphics/equation-heavy PDFs/EPUBs). These get a dedicated ingest workflow (see "Book Ingest Workflow"), not the standard one.
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
- Book pages: each book gets its own folder `wiki/sources/[book-slug]/` containing:
  - `_hub.md` — the book hub page (overview, table of contents, links to every chapter page).
  - `_progress.md` — the ingest progress/manifest file (see "Book Ingest Workflow"). Underscore-prefixed so it sorts first.
  - `chNN-[chapter-slug].md` — one page per chapter (e.g. `ch03-derivatives.md`).
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

This standard workflow is for shorter, mostly-text sources (articles, papers, notes). For anything in `raw/books/`, use the Book Ingest Workflow below instead.

## Book Ingest Workflow
Books in `raw/books/` are large and often graphics/equation-heavy (textbooks, technical books). Two hard rules:

1. **Never flatten a graphics/equation-heavy book with `pdftotext`/`markitdown`.** Plain text extraction silently corrupts equations and drops every figure, which poisons the wiki. Do NOT create a text-extraction sidecar `.md` for such books.
2. **Ingest with vision, not text extraction.** Render the relevant pages to images and read the actual rendered pages, so graphs, figures, and equations are visible.

### Rendering pages for vision
- Use `pdftoppm` (installed) to render pages to PNG at ~200 DPI, e.g.:
  `pdftoppm -png -r 200 -f <firstpage> -l <lastpage> "raw/books/<book>.pdf" /tmp/<book>-pg`
- Then Read the generated `/tmp/<book>-pg-NN.png` images directly.
- Transcribe equations to LaTeX. Describe important figures/graphs in prose (they can't live in `.md`); never silently drop a figure.

### Chunked, resumable, chapter-by-chapter ingest
Large books are ingested **one chapter at a time** so context stays small and the job can be left running (and safely resumed after any interruption). State lives on disk, never only in context.

On first ingest of a book:
1. Render the table of contents / front matter to find chapter boundaries and page ranges.
2. Create the book folder `wiki/sources/[book-slug]/` with:
   - `_hub.md` — overview + full chapter list (each chapter wikilinked, even before it's written).
   - `_progress.md` — a manifest table: for each chapter, its page range and status (`pending` / `done`), plus a "Next chapter" pointer. This file is the source of truth for where the loop is.
3. Append a `book-ingest-start` entry to `log.md`.

Each iteration (one chapter):
1. Read `_progress.md` to find the next `pending` chapter and its page range.
2. Render that chapter's pages with `pdftoppm`; Read the images.
3. Create `chNN-[chapter-slug].md` (summary, key equations in LaTeX, described figures, worked-example takeaways). Create/update relevant `concepts/` and `entities/` pages and wire `[[wikilinks]]` both ways, including to the `_hub.md`.
4. Update `_progress.md`: mark the chapter `done`, advance the "Next chapter" pointer.
5. Append a one-line `log.md` entry for the chapter.
6. Continue to the next chapter, or stop if the human asked for a bounded range.

When all chapters are `done`: update `index.md` (add the hub + notable concept pages), append a `book-ingest-complete` entry to `log.md`, and run `qmd update && qmd embed`.

### Resumability
Because `_progress.md` records exact status on disk, ingest can be killed and resumed at any point — the next run reads `_progress.md` and continues from the first `pending` chapter. Never assume in-context memory of progress.

### Search & reading notes
- The raw book PDF/EPUB is **not** qmd-indexed (qmd indexes `.md` only), but every per-chapter wiki page is — so the book is searchable through its wiki pages.
- The recommended Obsidian reader/annotator for these PDFs is **PDF++** (already installed in this vault). Human highlights/annotations made in PDF++ become linked notes in the vault; treat them as a priority signal for what to capture during ingest.

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