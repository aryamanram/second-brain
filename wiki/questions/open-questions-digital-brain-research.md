---
title: "Open Questions: Digital Brain for Research"
tags: [questions, knowledge-graph, research-methodology, antitrust]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Open Questions: Digital Brain for Research

Research gaps and open questions surfaced by [[schrepel-digital-brain-for-research]].

## On the methodology

1. **Graph vs. index-and-summarize, by scale.** Schrepel adds an explicit
   [[knowledge-graph]] where [[karpathy-llm-knowledge-bases]] found index files
   sufficient. At what corpus size / task type does the graph layer earn its cost? See
   [[open-questions-llm-knowledge-bases]] and [[karpathy-vs-schrepel-digital-brain]].
2. **Extraction faithfulness.** Claim-level extraction and absent-path findings depend on
   the AI extracting propositions and relationships correctly. How are extraction errors
   (missed edges, hallucinated propositions) detected and bounded? A flat degree
   distribution is flagged as a symptom, but what else?
3. **Absent paths: gap vs. extraction failure.** An "absent path" is treated as a
   literature gap — but it could equally be an extraction miss. How to distinguish a
   genuine theoretical gap from a graph artifact?

## On the antitrust findings (from the appendices)

4. **Is the Commission's hidden infrastructure computational?** Appendix A concludes the
   *published* record shows no computational antitrust methodology, but cannot assess
   whether DG COMP's unpublished detection/screening infrastructure is more sophisticated.
   See [[computational-antitrust]].
5. **Will Article 102 adopt ecosystem-level harm?** Appendix B's after-market analogy
   (Apple Mobile Payments) and the DMA gatekeeper logic suggest a path to a unified
   ecosystem theory of harm, but Article 102 enforcement hasn't adopted it. Does Google
   Adtech / Google AI mark the turn? See [[ecosystem-theory-of-harm]].

## Related Pages
- [[schrepel-digital-brain-for-research]]
- [[knowledge-graph]]
- [[computational-antitrust]]
- [[ecosystem-theory-of-harm]]
- [[karpathy-vs-schrepel-digital-brain]]
- [[open-questions-llm-knowledge-bases]]
