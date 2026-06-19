---
title: "Stewart Calculus 9e — Ingest Progress"
tags: [book, ingest-progress, calculus, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Stewart Calculus 9e — Ingest Progress Manifest

Source: `raw/books/stewart-calculus-9e.pdf` (1429 PDF pages). Authors: James Stewart, Daniel Clegg, Saleem Watson. Cengage, 9th ed., 2021.

**Page offset:** PDF page = printed page + 37 (verified at Ch.1 printed 7 → PDF 44, and Ch.11 printed 761 → PDF 798).

**Render command per chapter:**
`pdftoppm -png -r 200 -f <PDF_START> -l <PDF_END> "raw/books/stewart-calculus-9e.pdf" /tmp/cal-pg`
Then Read the `/tmp/cal-pg-*.png` images. For very long chapters (>60 pp), render in sub-batches to keep context manageable.

**Authority:** the Status column below is the single source of truth. Next chapter = first row with Status `pending`. Statuses progress `pending` → `in-progress` → `done`. Page ranges live only in this table; chapter pages copy them verbatim.

**Embed cadence:** run `qmd update && qmd embed` every 4 completed chapters, plus a final embed at completion. (Last embed: 2026-06-18 after Ch.12 — counter reset to 0.)

## Manifest

| # | Chapter | Printed pp | PDF pp | Status | Page file |
|---|---------|-----------|--------|--------|-----------|
| P | A Preview of Calculus | 1–5 | 38–42 | done | ch00-preview.md |
| 1 | Functions and Limits | 7–95 | 44–143 | done | ch01-functions-and-limits.md |
| 2 | Derivatives | 107–208 | 144–245 | done | ch02-derivatives.md |
| 3 | Applications of Differentiation | 209–300 | 246–337 | done | ch03-applications-of-differentiation.md |
| 4 | Integrals | 301–362 | 338–399 | done | ch04-integrals.md |
| 5 | Applications of Integration | 363–410 | 400–447 | done | ch05-applications-of-integration.md |
| 6 | Inverse Functions (Log, Exp, Inverse Trig) | 411–522 | 448–559 | done | ch06-inverse-functions.md |
| 7 | Techniques of Integration | 523–596 | 560–633 | done | ch07-techniques-of-integration.md |
| 8 | Further Applications of Integration | 597–642 | 634–679 | done | ch08-further-applications-of-integration.md |
| 9 | Differential Equations | 643–698 | 680–735 | done | ch09-differential-equations.md |
| 10 | Parametric Equations and Polar Coordinates | 699–760 | 736–797 | done | ch10-parametric-and-polar.md |
| 11 | Sequences, Series, and Power Series | 761–866 | 798–903 | done | ch11-sequences-series-power-series.md |
| 12 | Vectors and the Geometry of Space | 867–926 | 904–963 | done | ch12-vectors-geometry-of-space.md |
| 13 | Vector Functions | 927–970 | 964–1007 | done | ch13-vector-functions.md |
| 14 | Partial Derivatives | 971–1074 | 1008–1111 | done | ch14-partial-derivatives.md |
| 15 | Multiple Integrals | 1075–1160 | 1112–1197 | done | ch15-multiple-integrals.md |
| 16 | Vector Calculus | 1161–1254 | 1198–1291 | done | ch16-vector-calculus.md |

Appendices A–G (Numbers/Inequalities, Coordinate Geometry, Second-Degree Equations, Trigonometry, Sigma Notation, Proofs of Theorems, Answers) are reference material — ingest on demand only, not part of the main chapter loop.

## Loop protocol (per CLAUDE.md "Book Ingest Workflow")
1. Read this file; find the first `pending` row (Status column is authoritative).
2. Mark that row `in-progress` before rendering.
3. Render its PDF page range (verbatim from the row); Read the images.
4. Write the chapter page (`chNN-*.md`): summary, key definitions/theorems, equations in LaTeX, important figures described in prose, worked-example takeaways. Copy the page range verbatim from the row. Promote concepts/entities per the promotion test, then wire `[[wikilinks]]` to/from the hub, concepts, and entities.
5. Mark the row `done` (only after the page is fully written and linked).
6. Append a one-line entry to `log.md`.
7. Every 4 completed chapters, run `qmd update && qmd embed`.
8. Continue to next pending chapter (or stop if a bounded range was requested).

On resume: if a row is `in-progress`, discard any partial `chNN` page and redo that chapter.

When all chapters `done`: update `index.md`, append `book-ingest-complete` to `log.md`, run a final `qmd update && qmd embed`.
