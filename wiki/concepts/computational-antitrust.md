---
title: "Computational Antitrust (EC enforcement)"
tags: [antitrust, competition-law, european-commission, methodology, concept]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Computational Antitrust (EC enforcement)

Findings from **Appendix A** of [[schrepel-digital-brain-for-research]], a research note
synthesized across **508 European Commission competition decisions (1977–2025)** using
the digital-brain pipeline.

## Headline finding

The Commission's enforcement toolkit is **predominantly qualitative and documentary**.
References to computational or econometric methods are sparse, typically *reactive*
(evaluating parties' submissions rather than deploying Commission-generated models), and
never describe a proactive algorithmic detection infrastructure. **There is no visible
computational antitrust methodology in the decisional record.**

## What the Commission does reference

- **Traffic/click-through analysis** — Google Shopping (AT.39740, 2017): documentary
  before/after comparison, not an econometric model.
- **Cost accounting / data allocation** — Aspen (AT.40394, 2021): volume-based
  allocation = data imputation, not causal inference.
- **Regulatory formulas** — the Merchant Interchange Test in Visa (AT.39398) /
  MasterCard (AT.40049): deterministic arithmetic, not statistical modelling.
- **Third-party surveys** — Apple Mobile Payments (AT.40452, 2024).
- **Critiquing parties' econometrics** — Intel (AT.37990, 2009): the most sustained
  engagement with statistics is a *critique* of Intel's regression (omitted-variable
  bias, specification errors); the Commission's own assessment stayed qualitative.

## What is absent

Across all 508 decisions: no cartel-screening algorithms, ML bid-rigging detection,
algorithmic collusion detection, dawn-raid digital forensics platforms, proprietary
real-time monitoring, or natural-experiment / difference-in-differences methods deployed
*by the Commission itself*. Algorithms appear as the **object** of investigation (Google
Ads AT.40670; Amazon Buy Box AT.40703) — analyzed via internal documents and testimony —
not as the **investigative tool**.

## Why the gap exists

Computational detection (leniency markers, sector-inquiry screens) may predate formal
proceedings and never reach published decisions. DG COMP's Chief Economist Team does use
GUPPI, diversion ratios, and concentration studies, but this feeds internal assessments,
not formal decisional methodology — a **structural** gap. The standard of proof in
CJEU-reviewed administrative proceedings incentivizes documentary evidence that
withstands appeal over disclosure-heavy statistical modelling.

## Emerging signal

Google Adtech (AT.40670, 2025) is the most technically sophisticated decision and implies
access to expert auction modelling; Google AI (AT.40983, 2025) investigates AI training
data and architecture. These may signal where the gap begins to close.

## Related Pages
- [[schrepel-digital-brain-for-research]]
- [[ecosystem-theory-of-harm]]
- [[institutional-memory-audit]]
- [[thibault-schrepel]]
