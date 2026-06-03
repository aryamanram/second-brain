# Operation Log

Chronological record of all wiki operations.

## [2026-04-15] init | Wiki created
- Created folder structure and schema.
- Ready for first source ingest.

## [2026-05-30] ingest | raw/articles/Post by @karpathy on X.md
- Ingested Karpathy's X post on LLM Knowledge Bases (the only un-indexed source in raw/).
- Created source: [[karpathy-llm-knowledge-bases]].
- Created entities: [[andrej-karpathy]], [[obsidian]].
- Created concepts: [[llm-knowledge-base]], [[incremental-compilation]], [[wiki-linting]], [[raw-directory-as-product]], [[retrieval-augmented-generation]].
- Created questions: [[open-questions-llm-knowledge-bases]].
- Updated index.md.

## [2026-05-30] ingest | raw/papers/Building a Digital Brain for Research.pdf
- Ingested Schrepel's "Building a Digital Brain for Research" (installed poppler to read the 37-page PDF).
- Created source: [[schrepel-digital-brain-for-research]].
- Created entities: [[thibault-schrepel]], [[graphify]], [[markitdown]], [[claude-code]].
- Created concepts: [[digital-brain]], [[knowledge-graph]], [[god-nodes]], [[research-schema-design]], [[centrality-weighted-wiki-generation]], [[claim-level-extraction]], [[six-step-research-protocol]], [[hypothesis-register]], [[graph-diagnostics]], [[absence-first-research]], [[computational-antitrust]], [[ecosystem-theory-of-harm]].
- Created comparison: [[karpathy-vs-schrepel-digital-brain]].
- Created questions: [[open-questions-digital-brain-research]].
- Backlinked from existing pages: [[andrej-karpathy]], [[llm-knowledge-base]], [[obsidian]].
- NOTE: this entry was reconstructed after the fact during the 2026-05-31 lint (index.md and log.md had not been updated at ingest time).

## [2026-05-31] lint | full health check + fixes
- Ran full lint: broken links, orphans, contradictions, missing pages, stale index/log/search.
- Fixed broken wikilinks: [[god-nodes]] typo in hypothesis-register; de-linked prose "wikilinks"/"double-bracket" mentions in obsidian and wiki-linting.
- Rebuilt index.md to list all 33 pages (was listing only 9).
- Reconstructed the missing Schrepel ingest log entry (above).
- Created 5 gap-filling pages: [[safi-shamsi]], [[leiden-community-detection]], [[scale-free-network]], [[small-world-network]], [[institutional-memory-audit]]; wired inbound links so none are orphans.
- De-orphaned [[open-questions-digital-brain-research]] via cross-link from [[open-questions-llm-knowledge-bases]].
- Re-synced qmd collections (update + embed).

## [2026-06-01] ingest | raw/articles/Andrej Karpathy.md
- Ingested the Wikipedia biography of Andrej Karpathy (biographical backfill for the existing entity page).
- Created source: [[wikipedia-andrej-karpathy]].
- Created concept: [[vibe-coding]] (Karpathy-coined; ties together both Karpathy sources).
- Created entities: [[anthropic]], [[openai]], [[tesla]], [[eureka-labs]], [[fei-fei-li]], [[stanford-university]], [[university-of-toronto]].
- Substantially expanded existing entity [[andrej-karpathy]] with a Biography section; added [[vibe-coding]] backlinks from [[karpathy-llm-knowledge-bases]] and [[anthropic]] backlink from [[claude-code]].
- Updated index.md (42 pages total). Lint clean: 0 broken links, 0 orphans.

## [2026-06-01] lint | full health check (clean) + polish
- Ran full lint across all dimensions: 0 broken links, 0 orphans, all frontmatter/Related/sources valid, index fully covers all pages, no contradictions, no future dates.
- Polish 1: added missing [[stanford-university]] backlinks from [[thibault-schrepel]] (Stanford affiliations were plain text).
- Polish 2: created first synthesis page [[llm-knowledge-base-toolchain]] (wiki/syntheses/) tying together the toolchain (markitdown/graphify/claude-code/obsidian/vibe-coding) and the retrieval-vs-research layers; linked it from [[llm-knowledge-base]] and [[karpathy-vs-schrepel-digital-brain]].
- Updated index.md (43 pages total; Syntheses section now populated). Re-synced qmd.

## [2026-06-03] ingest | raw/papers/obsidian-lazy-method-brief.pdf
- Ingested Bryce Robbie's "The Lazy Obsidian Method" field note (2-page PDF).
- Created source: [[lazy-obsidian-method-brief]].
- Created entities: [[bryce-robbie]], [[kepano]], [[obsidian-skills]], [[qmd]].
- Created concepts: [[lazy-obsidian-method]], [[para-method]], [[maintenance-cadence]].
- Backlinked from existing pages: [[obsidian]], [[graphify]], and the synthesis [[llm-knowledge-base-toolchain]] (added a "packaged instantiation" subsection + tobi/qmd and kepano builders).
- Notable: the brief names three tools this wiki already uses (Obsidian, Graphify, QMD); gave QMD its own entity page since the wiki depends on it.
- Updated index.md (51 pages total). Lint clean: 0 broken links, 0 orphans.