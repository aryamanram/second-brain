---
title: "Research Schema Design"
tags: [knowledge-graph, research-methodology, claude-md, concept]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Research Schema Design

The first of Thibault Schrepel's six contributions in
[[schrepel-digital-brain-for-research]]. The `CLAUDE.md` schema is "the only instrument
through which a researcher can shape the graph before it is built" — everything in it
becomes part of the AI's working context during extraction. A deliberate research schema
changes the output "from a retrieval system to a research instrument."

## Four design choices that distinguish a research schema

1. **Authority weighting** — for corpora mixing authority levels (scholarship,
   administrative decisions, court judgments), encode the hierarchy explicitly so the AI
   doesn't treat a student note as equivalent to a Court of Justice judgment.
   *(Legal-specific; skippable for other fields.)*
2. **Absence as a query target** — instruct the AI to flag what sources *don't* address,
   not just what they say; every wiki article should note which adjacent topics its
   cluster fails to address (see [[absence-first-research]]).
3. **Conceptual anchors** — encode the field's core and contested terms (e.g. for
   antitrust: market definition, theory of harm, standard of proof, efficiency defense)
   so they are extracted as priority nodes, reducing noise and shaping community
   structure.
4. **Claim-level extraction** — instruct extraction of affirmative propositions per
   document (see [[claim-level-extraction]]).

The provided example schema also includes the **Node Centrality Weighting** rule (see
[[centrality-weighted-wiki-generation]], [[god-nodes]]), a "What the sources do not
address" section per article, the [[hypothesis-register]] instruction, and the
[[graph-diagnostics]] module instruction.

## Note

Schrepel stresses this is an *adaptation*, not a new capability — any user could always
put anything in `CLAUDE.md`; the contribution is treating deliberate schema design as a
*required* pipeline step.

## Related Pages
- [[schrepel-digital-brain-for-research]]
- [[claim-level-extraction]]
- [[centrality-weighted-wiki-generation]]
- [[absence-first-research]]
- [[hypothesis-register]]
- [[graph-diagnostics]]
