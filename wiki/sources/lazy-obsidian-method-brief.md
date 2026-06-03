---
title: "The Lazy Obsidian Method (Bryce Robbie field note)"
tags: [knowledge-management, obsidian, workflow, personal-knowledge-stack, source]
date_created: 2026-06-03
date_updated: 2026-06-03
sources: [raw/papers/obsidian-lazy-method-brief.pdf]
---

# The Lazy Obsidian Method (Bryce Robbie field note)

Summary of a 2-page field note by [[bryce-robbie]] ("BRYCE ROBBIE | AI · FIELD NOTE,
Issue 01 — Personal Knowledge Stack"), titled **"The Lazy Obsidian Method: A clear setup
for turning messy notes into a useful AI second brain."** It is a practical *stack and
recipe* — not original methodology — that assembles existing tools around
[[andrej-karpathy]]'s LLM-wiki idea.

## Core thesis

> "Capture messy. Process later. Let the vault improve over time."

A deliberately **lazy** (low-maintenance) take on building an AI second brain. At the
centre is Karpathy's [[llm-knowledge-base]] idea — keep raw source material, process what
matters, slowly turn it into structured, connected knowledge. The value is in the
*support layer* around it (structure, search, graph, recurring jobs). The goal "isn't a
perfect second brain on day one" but a system that's easy to use, easy to maintain, and
keeps improving in the background.

## The stack at a glance

| Layer | Tool | What it does |
|---|---|---|
| **Vault** | [[obsidian]] | Local-first markdown notes; the home base |
| **Method** | Karpathy LLM wiki ([[llm-knowledge-base]]) | Capture raw → process → link → compound |
| **Structure** | [[para-method]] | Projects, Areas, Resources, Archive |
| **Workflow** | [[obsidian-skills]] | [[kepano]]'s patterns for working inside the vault |
| **Graph** | [[graphify]] | Surfaces clusters, key nodes, relationships |
| **Search** | [[qmd]] | Better markdown retrieval as the vault grows |

## The "lazy unlock": recurring jobs

The maintenance layer is automated on a cadence (see [[maintenance-cadence]]):

| Cadence | Inputs | Outputs | Purpose |
|---|---|---|---|
| **Daily ingest** | Web clips, notes, voice memos | Cleaned notes, wiki-ready pages, ingest summary | Get messy inputs in — don't overthink |
| **Nightly review** | Daily notes, lessons, agent logs & memory | Refreshed dashboards, memory updates, backups | Tidy-up + critical priority refresh |
| **Weekly vault** | Memory, dashboards, topic gaps | Weekly review, gaps list, next-step items | Set focus areas for the coming week |

## The 10-step setup

1. Set up [[para-method|PARA]] folders (only critical if you have no structure; align
   your agents to it).
2. Create the [[obsidian]] vault (give your agent the relevant skills; ask how it'd work
   best).
3. Capture raw, fast — clips, notes, ideas into a `raw/` folder, Karpathy-style.
4. Promote with the LLM-wiki method — turn the useful raw into linked, structured pages.
5. Add [[obsidian-skills]] — practical vault workflows from [[kepano]].
6. Add [[graphify]] — make the graph view actually informative.
7. Add [[qmd]] — cleaner search and retrieval at scale.
8. Build custom hubs — projects, research, workflows, agent logs, OS.
9. Wire daily / nightly / weekly jobs — the maintenance layer, automated.
10. Review & refine — watch outputs, trim what's noisy, keep what compounds.

## Why this matters here

This brief is effectively a **field-tested instantiation of this wiki's own stack**: it
names [[obsidian]], [[graphify]], and [[qmd]] — all of which this knowledge base uses —
and the Karpathy LLM-wiki method this wiki implements. It adds two ingredients the
existing sources don't emphasize: an explicit folder taxonomy ([[para-method]]) and an
automated [[maintenance-cadence]] (daily/nightly/weekly jobs). See
[[llm-knowledge-base-toolchain]] for how these fit the broader toolchain.

## References (from the brief)

Obsidian (obsidian.md) · Steph Ango / Kepano (stephango.com) · Obsidian Skills
(github.com/kepano/obsidian-skills) · Karpathy LLM wiki (gist.github.com/karpathy) ·
PARA Method (fortelabs.com/blog/para) · Graphify (github.com/safishamsi/graphify) ·
QMD (github.com/tobi/qmd).

## Related Pages
- [[bryce-robbie]]
- [[para-method]]
- [[obsidian-skills]]
- [[kepano]]
- [[qmd]]
- [[maintenance-cadence]]
- [[obsidian]]
- [[graphify]]
- [[llm-knowledge-base]]
- [[llm-knowledge-base-toolchain]]
- [[andrej-karpathy]]
