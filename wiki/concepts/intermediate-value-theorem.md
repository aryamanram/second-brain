---
title: "Intermediate Value Theorem"
tags: [calculus, mathematics, continuity, theorem]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Intermediate Value Theorem (IVT)

If $f$ is **continuous** on the closed interval $[a,b]$ and $N$ is any number between $f(a)$ and $f(b)$ (with $f(a)\ne f(b)$), then there exists a number $c$ in the open interval $(a,b)$ with $f(c)=N$.

Intuitively, a continuous function takes on every value between its endpoint values — its graph cannot skip a horizontal level without crossing it. The classic application is **root-locating**: if $f$ is continuous and changes sign on $[a,b]$, then $f$ has a zero in $(a,b)$. [[continuity]] is essential — a function with a jump can skip the value $N$.

## Related Pages
- [[ch01-functions-and-limits]] — Stewart Calculus 9e, §1.8 (Theorem 10)
- [[continuity]] — the hypothesis the theorem requires
- [[limit]]
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]]
