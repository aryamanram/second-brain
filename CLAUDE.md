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
  - Link hygiene: `_hub`/`_progress` are NOT globally unique (every book has them), so always link them folder-qualified — e.g. `[[stewart-calculus-9e/_hub|Stewart Calculus 9e]]`, never bare `[[_hub]]`. Chapter files (`chNN-...`) are slugged with enough of the book/topic to stay globally unique.
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
1. Render the table of contents / front matter to find chapter boundaries and page ranges. **Establish and verify the page offset** (printed page number vs. PDF page number) at two well-separated points before trusting any range.
2. Create the book folder `wiki/sources/[book-slug]/` with:
   - `_hub.md` — overview + full chapter list (each chapter wikilinked, even before it's written).
   - `_progress.md` — the manifest (see "_progress.md is the single source of truth" below).
3. Append a `book-ingest-start` entry to `log.md`.

Each iteration (one chapter):
1. Read `_progress.md` and pick the next chapter = the **first row whose Status is `pending`**, read top-to-bottom (see authority rule below).
2. Mark that row `in-progress` in `_progress.md` *before* rendering.
3. Render that chapter's pages with `pdftoppm` (PDF range taken verbatim from the row); Read the images.
4. Create `chNN-[chapter-slug].md` (summary, key equations in LaTeX, described figures, worked-example takeaways). The page range printed in the chapter page MUST be copied verbatim from the `_progress.md` row — never re-derive it.
5. Promote concepts/entities per the **promotion test** below; wire `[[wikilinks]]` both ways, including the folder-qualified link to the hub (see Naming Conventions).
6. Mark the row `done` in `_progress.md` (only after the page is fully written and linked).
7. Append a one-line `log.md` entry for the chapter.
8. If the chapter count since the last embed has reached 4, run `qmd update && qmd embed` so finished chapters become searchable mid-ingest.
9. Continue to the next chapter, or stop if the human asked for a bounded range. **The loop runs unattended — do not pause to discuss each chapter; surface takeaways only in the per-chapter `log.md` line.**

When all chapters are `done`: update `index.md` (add the hub + any promoted concept pages), append a `book-ingest-complete` entry to `log.md`, and run a final `qmd update && qmd embed`.

### `_progress.md` is the single source of truth
- **The Status column is authoritative.** The next chapter to ingest is always the first row whose Status is `pending`. Any "Next chapter" convenience line is non-binding — if it ever disagrees with the first `pending` row, the table wins.
- **Three statuses:** `pending` → `in-progress` → `done`. Mark `in-progress` immediately before rendering; mark `done` only after the chapter page is fully written and wikilinked.
- **Page ranges live only here.** Chapter pages copy their range verbatim from the manifest; never re-derive ranges in a chapter page (that causes silent drift).

### Promotion test (concepts/entities)
Don't promote every term (avoids stub-spam), but don't leave the book an island either. During book ingest, give a term its own `concepts/` or `entities/` page only when it is **(a)** a named theorem/definition a future non-book source would plausibly link to (e.g. "Intermediate Value Theorem", "Squeeze Theorem", "limit", "continuity"), or **(b)** referenced from ≥2 chapters. Authors and notable historical figures (e.g. Newton, Leibniz) always get `entities/` pages per the standard rule. Everything else stays as bold text in the chapter page. Wire promoted pages into the chapter's Related Pages.

### Resumability
Because `_progress.md` records exact status on disk, ingest can be killed and resumed at any point — the next run reads the Status column and continues from the first `pending` row. **If a row is `in-progress` on resume, discard any partial `chNN` page and redo that chapter from scratch.** Never assume in-context memory of progress.

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

For an in-flight book (one with a `_progress.md` containing `pending`/`in-progress` rows): treat forward-links to not-yet-written `pending` chapters as expected-missing (not broken links), and treat the in-progress book folder as expected-absent from `index.md`. Don't report these as lint errors until the book is complete.

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
- `qmd update` — Re-scan collection folders and refresh the file index (run before `qmd embed` after adding/changing files)
- `qmd embed` — Generate/refresh vector embeddings after ingesting new sources (run after every ingest)

**Collections:**
- `raw` — points to raw/ (immutable sources)
- `wiki` — points to wiki/ (LLM-maintained pages)

**Workflow update:**
- After every ingest, run `qmd embed` to keep the search index current.
- When answering queries, use `qmd query` to find relevant pages instead of reading index.md alone.