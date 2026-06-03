---
title: "Claim-Level Extraction"
tags: [knowledge-graph, research-methodology, extraction, concept]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Claim-Level Extraction

The fourth of Thibault Schrepel's six contributions in
[[schrepel-digital-brain-for-research]]. It moves the unit of analysis in the
[[knowledge-graph]] **from documents to propositions**.

## How it works

For each document, the AI extracts a list of **affirmative propositions**. Each
proposition carries:
- a **premise**,
- an **inference** drawn from that premise, and
- a **pointer to the in-document evidence** that supports it.

Each proposition is attached to its document node as a **child node**, and proposition
nodes are queryable alongside concept nodes. The [[six-step-research-protocol]] then runs
at *claim granularity*.

## Why it matters

Treating each paper as a single node hides its propositional content. Two papers that
look connected at the document level often defend **incompatible claims** at the
propositional level. An absent path between two *claims* therefore carries different
meaning than an absent path between two *documents* — claim-level graphs make visible the
incompatibilities that document-level graphs hide.

## Related Pages
- [[schrepel-digital-brain-for-research]]
- [[knowledge-graph]]
- [[six-step-research-protocol]]
- [[research-schema-design]]
