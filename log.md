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

## [2026-06-18] book-ingest-start | raw/books/stewart-calculus-9e.pdf
- First book ingest. Stewart, Clegg & Watson, *Calculus* 9th ed. (Cengage 2021), 1429 PDF pages.
- Inaugural use of the new Book Ingest Workflow (vision render via pdftoppm, chunked chapter-by-chapter, resumable via on-disk manifest).
- Built book folder `wiki/sources/stewart-calculus-9e/` with [[_hub]] (overview + 16-chapter TOC) and [[_progress]] (manifest; page offset PDF = printed + 37, verified at Ch.1 and Ch.11).
- Ingested chapter: [[ch00-preview|A Preview of Calculus]] (PDF pp. 38–42). Captured the area problem, tangent problem, the limit, and the FTC connection; figures described in prose, limit/derivative formulas in LaTeX.
- Next chapter: 1 — Functions and Limits (PDF 44–143).

## [2026-06-18] book-ingest-chapter | stewart-calculus-9e — A Preview of Calculus
- Wrote [[ch00-preview]]; marked Preview `done` in [[_progress]]; advanced pointer to Ch.1.

## [2026-06-18] book-ingest-chapter | stewart-calculus-9e — Ch.1 Functions and Limits
- Wrote [[ch01-functions-and-limits]] (PDF pp. 44–143, ~100 pp rendered in 3 sub-batches at 200 DPI).
- Covered all 8 sections: four representations of a function, essential-function catalog, transformations/composition, tangent & velocity problems, the limit (one-sided, infinite, asymptotes), Limit Laws + Squeeze Theorem, the ε–δ definition, and continuity + Intermediate Value Theorem. Equations in LaTeX; figures described in prose.
- Marked Ch.1 `done` in [[stewart-calculus-9e/_progress|progress]]; advanced to Ch.2.
- Held for accuracy review (subagent audit) before continuing the loop, per user request.

## [2026-06-18] analysis | stewart-calculus-9e Ch.1 audit + workflow tuning
- Ran 3 subagents: two adversarial math auditors (§1.1–1.4, §1.5–1.8) re-rendered the source and checked every formula/definition/theorem; one workflow/process critic.
- Accuracy verdict: **excellent** both halves. All Limit Laws, the ε–δ definition, Squeeze Theorem, three continuity conditions, and IVT transcribed correctly. Only an example-number mislabel in §1.2 (fixed) and minor omitted examples (floor function). Vision-ingest approach validated.
- CLAUDE.md Book Ingest Workflow hardened from the critique: (1) `_progress.md` Status column is now the single source of truth (non-binding "Next chapter" line); (2) added `in-progress` status + "discard partial, redo on resume" rule; (3) chapter pages must copy page ranges verbatim from the manifest; (4) added a concrete concept/entity **promotion test**; (5) book hub/progress links must be folder-qualified (`[[book-slug/_hub]]`) to avoid collisions across books; (6) Lint Workflow now exempts pending chapters + in-flight book from broken-link/orphan/index checks; (7) `qmd embed` every 4 chapters during ingest; documented `qmd update`.
- Reconciled artifacts: corrected Ch.1 page range (printed 7–95, was 7–106) and §1.2 label; converted all bare `[[_hub]]`/`[[_progress]]` links to folder-qualified.
- Selective promotion applied: created concepts [[limit]], [[continuity]], [[intermediate-value-theorem]], [[squeeze-theorem]] and entities [[james-stewart]], [[isaac-newton]], [[gottfried-leibniz]]; wired bidirectional links; added them + an in-progress Books section to index.md.
- **Fixed a latent qmd config bug:** both `wiki` and `raw` collections pointed at a stale vault path (`Documents/Second-Brain/second-brain`, since moved to `Documents/Obsidian/second-brain`), so search had been silently broken vault-wide (indexing 0 files). Re-pointed both collections, re-embedded. `wiki` now indexes 62 files; verified search returns the new calculus pages.

## [2026-06-18] book-ingest-chapter | stewart-calculus-9e — Ch.2 Derivatives (autonomous /loop)
- First autonomous /loop iteration. Marked Ch.2 `in-progress`, rendered PDF pp. 144–245 (~100 pp, 2 sub-batches at 200 DPI), wrote [[ch02-derivatives]].
- Covered all 6 sections: derivative definition (tangent slope + rate of change), derivative-as-function & differentiability⇒continuity, the rule toolkit (constant/power/sum/product/quotient), trig derivatives + the two trig limits, the Chain Rule, and implicit differentiation. Equations in LaTeX; figures described.
- Marked Ch.2 `done`; manifest advances to Ch.3. 3 chapters done since last embed (embed due after Ch.4 per cadence).

## [2026-06-18] book-ingest-chapter | stewart-calculus-9e — Ch.3 Applications of Differentiation (autonomous /loop)
- Marked Ch.3 `in-progress`, rendered PDF pp. 246–337 (~92 pp, 2 sub-batches at 200 DPI; sampled key definition/theorem pages across the large second batch), wrote [[ch03-applications-of-differentiation]].
- Covered §3.1 extrema + EVT + Fermat + Closed Interval Method, §3.2 Rolle's + Mean Value Theorem, §3.3 I/D + First/Second Derivative + Concavity tests, §3.4 limits at infinity/horizontal asymptotes, §3.5 curve sketching, §3.7 optimization + marginal cost/revenue/profit, §3.8 Newton's Method, §3.9 antiderivatives. Equations in LaTeX.
- Marked Ch.3 `done`; manifest advances to Ch.4. 2 chapters since last embed (Ch.2, Ch.3) — embed due after Ch.4.

## [2026-06-18] book-ingest-chapter | stewart-calculus-9e — Ch.4 Integrals (autonomous, dynamic loop)
- Switched cron loop to dynamic pacing (cancelled fixed 4-min job 08a309ab) and broadened the Bash allowlist (wildcard `pdftoppm *`, `rm`, `qmd`, `grep`) so ingest runs prompt-free while the user is away ~30 min.
- Marked Ch.4 `in-progress`, rendered PDF pp. 338–399 (~62 pp, 2 sub-batches), wrote [[ch04-integrals]].
- Covered §4.1 area/distance as Riemann-sum limit, §4.2 the definite integral + net area + properties, §4.3 **Fundamental Theorem of Calculus Parts 1 & 2**, §4.4 indefinite integrals + table + Net Change Theorem, §4.5 the Substitution Rule (indefinite & definite). Equations in LaTeX.
- Promoted concepts [[definite-integral]], [[fundamental-theorem-of-calculus]] (foundational, future-linkable); wired bidirectional links.
- Marked Ch.4 `done`; manifest advances to Ch.5. Ran `qmd update && qmd embed` at the Ch.4 milestone; embed counter reset.

## [2026-06-18] book-ingest-chapter | stewart-calculus-9e — Ch.5 Applications of Integration (autonomous, dynamic loop)
- Marked Ch.5 `in-progress`, rendered PDF pp. 400–447 (~48 pp), wrote [[ch05-applications-of-integration]].
- Covered §5.1 areas between curves, §5.2 volumes (cross-section/disk/washer), §5.3 cylindrical shells, §5.4 work + Hooke's Law, §5.5 average value + Mean Value Theorem for Integrals. Equations in LaTeX.
- Marked Ch.5 `done`; manifest advances to Ch.6. 1 chapter since last embed.

## [2026-06-18] book-ingest-chapter | stewart-calculus-9e — Ch.6 Inverse Functions (autonomous, dynamic loop)
- Marked Ch.6 `in-progress`, rendered PDF pp. 448–559 (~112 pp, 3 sub-batches; sampled key definition/derivative/integral pages), wrote [[ch06-inverse-functions]].
- Covered §6.1 inverse functions + Horizontal Line Test, §6.2–6.4 exp/log functions + derivatives ($e^x$, $\ln x$, $b^x$, $\log_b x$) + Laws of Logs + ln-as-integral, §6.5 exponential growth/decay $y_0e^{kt}$, §6.6 inverse trig + derivative table, §6.7 hyperbolic functions, §6.8 L'Hospital's Rule. Equations in LaTeX.
- Marked Ch.6 `done`; manifest advances to Ch.7. 2 chapters since last embed (Ch.5, Ch.6).2026-06-18 18:07 book-ingest-chapter: Stewart Calculus 9e Ch.7 Techniques of Integration (PDF 560-633) — integration by parts, trig integrals, trig substitution, partial fractions, strategy, tables/CAS, approximate integration (Midpoint/Trapezoidal/Simpson + error bounds), improper integrals (Type 1/2, Comparison Theorem). No new concept/entity promotions (selective). 7/16 chapters done.
2026-06-18 18:10 book-ingest-chapter: Stewart Calculus 9e Ch.8 Further Applications of Integration (PDF 634-679) — arc length, surface area of revolution, hydrostatic force & centers of mass/centroids, economics (consumer/producer surplus, Poiseuille's Law) & biology, probability (density functions, mean, exponential & normal distributions). No new concept/entity promotions (selective). 8/16 chapters done.
2026-06-18 18:13 book-ingest-chapter: Stewart Calculus 9e Ch.9 Differential Equations (PDF 680-735) — modeling, direction fields & Euler's method, separable equations, population growth (exponential & logistic), first-order linear equations (integrating factor), predator-prey (Lotka-Volterra) systems. Promoted entity: leonhard-euler (historical mathematician). 9/16 chapters done.
2026-06-18 18:16 book-ingest-chapter: Stewart Calculus 9e Ch.10 Parametric Equations and Polar Coordinates (PDF 736-797) — parametric curves, calculus with parametric curves (tangents/area/arc length), polar coordinates, calculus in polar (area, arc length), conic sections, conics in polar (eccentricity, Kepler's Laws). Promoted entity: johannes-kepler (historical figure). 10/16 chapters done.
2026-06-18 18:20 book-ingest-chapter: Stewart Calculus 9e Ch.11 Sequences, Series, and Power Series (PDF 798-903, rendered in 2 batches) — sequences, series, integral/comparison/alternating/ratio/root tests, absolute vs conditional convergence, power series (radius/interval of convergence), function representations, Taylor & Maclaurin series + Taylor's Inequality + standard series table + applications. No new promotions (Euler already promoted). 11/16 chapters done.
2026-06-18 18:24 book-ingest-chapter: Stewart Calculus 9e Ch.12 Vectors and the Geometry of Space (PDF 904-963) — 3D coordinates, vectors, dot product (projections/work), cross product (determinant form, parallelogram area, torque), lines & planes (parametric/symmetric/normal equations, distances), cylinders & quadric surfaces (traces). Promoted entity: william-rowan-hamilton (historical figure). 12/16 chapters done.
2026-06-18 18:27 book-ingest-chapter: Stewart Calculus 9e Ch.13 Vector Functions (PDF 964-1007) — vector functions & space curves, derivatives & integrals (tangent vector), arc length & curvature (TNB frame, osculating circle, Frenet-Serret), motion in space (velocity/speed/acceleration, Newton's 2nd law, projectile motion, tangential/normal components, Kepler's 1st law). No new promotions (Newton/Kepler already promoted). 13/16 chapters done.
2026-06-18 18:46 book-ingest-chapter: Stewart Calculus 9e Ch.14 Partial Derivatives (PDF 1008-1111, 2 batches) — functions of several variables (level curves/contour maps), limits & continuity, partial derivatives (Clairaut, PDEs), tangent planes & linear approximation, chain rule, directional derivatives & gradient, max/min (Second Derivatives Test, saddle points), Lagrange multipliers. No new promotions. 14/16 chapters done.
2026-06-18 18:56 book-ingest-chapter: Stewart Calculus 9e Ch.15 Multiple Integrals (PDF 1112-1197, 2 batches) — double integrals over rectangles (Fubini, iterated integrals) & general regions (type I/II, reversing order), polar double integrals (dA=r dr dθ), applications (mass/center of mass/moments of inertia/probability), surface area, triple integrals, cylindrical & spherical coordinates (dV=ρ²sinφ ...), change of variables (Jacobian). No new promotions. 15/16 chapters done.
2026-06-18 19:05 book-ingest-chapter: Stewart Calculus 9e Ch.16 Vector Calculus (PDF 1198-1291, 2 batches) — vector fields, line integrals (work) & FTC for line integrals (conservative fields/potential functions/path independence), Green's Theorem, curl & divergence (del operator, div(curl F)=0), parametric surfaces & area, surface integrals (flux), Stokes' Theorem, Divergence Theorem (Gauss-Ostrogradsky). Promoted entities: george-green, george-stokes, carl-friedrich-gauss (historical figures, theorem namesakes). 16/16 chapters done.
2026-06-18 19:05 book-ingest-complete: Stewart Calculus 9e fully ingested — Preview + Ch.1-16 (all single- and multivariable calculus). 17 chapter pages in wiki/sources/stewart-calculus-9e/, hub + progress manifest, 8 promoted entities (Stewart, Newton, Leibniz, Euler, Kepler, Hamilton, Green, Stokes, Gauss) and 4 promoted concepts (limit, continuity, IVT, squeeze theorem). index.md Books section updated to fully-ingested. Running final qmd update && qmd embed (also satisfies the every-4-chapters cadence: Ch.13,14,15,16).
