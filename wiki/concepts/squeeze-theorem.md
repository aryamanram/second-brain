---
title: "Squeeze Theorem"
tags: [calculus, mathematics, limits, theorem]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Squeeze Theorem

Also called the Sandwich (or Pinching) Theorem. If $f(x) \le g(x) \le h(x)$ for all $x$ near $a$ (except possibly at $a$) and
$$\lim_{x\to a} f(x) = \lim_{x\to a} h(x) = L,$$
then $\displaystyle\lim_{x\to a} g(x) = L$. The middle function is "squeezed" between two functions that converge to the same limit, so it is forced to that [[limit]] too.

Canonical application: $\displaystyle\lim_{x\to 0} x^2\sin(1/x) = 0$, shown via $-x^2 \le x^2\sin(1/x) \le x^2$ (the product rule fails here because $\lim_{x\to 0}\sin(1/x)$ does not exist).

## Related Pages
- [[ch01-functions-and-limits]] — Stewart Calculus 9e, §1.6 (Theorem 3)
- [[limit]] — the Squeeze Theorem is a tool for evaluating limits
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]]
