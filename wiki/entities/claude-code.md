---
title: "Claude Code"
tags: [tool, ai, agent, anthropic, entity]
date_created: 2026-05-30
date_updated: 2026-05-30
sources: [raw/papers/Building a Digital Brain for Research.pdf]
---

# Claude Code

[[anthropic|Anthropic]]'s agentic coding assistant (docs.anthropic.com/claude-code), used as the AI
runtime for the pipeline in [[schrepel-digital-brain-for-research]]. The
[[graphify]] skill runs inside it; querying the corpus and generating the wiki happen
through Claude Code prompts. It is the only non-free tool in the stack (Claude Pro,
Team, or Max subscription).

In the source, Claude Pro (~$20/mo) is described as sufficient for a few hundred
documents and Claude Max (~$100/mo, higher rate limits) is recommended for the initial
build. The same pipeline reportedly works with GPT Codex via Graphify's
OpenAI-compatible mode. This very knowledge base is itself maintained through Claude
Code (see `CLAUDE.md`).

## Related Pages
- [[anthropic]]
- [[schrepel-digital-brain-for-research]]
- [[graphify]]
- [[digital-brain]]
