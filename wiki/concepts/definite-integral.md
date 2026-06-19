---
title: "Definite Integral"
tags: [calculus, mathematics, integration, foundational-concept]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Definite Integral

The **definite integral** of $f$ from $a$ to $b$ is the limit of Riemann sums:
$$\int_a^b f(x)\,dx = \lim_{n\to\infty}\sum_{i=1}^n f(x_i^*)\,\Delta x, \qquad \Delta x = \frac{b-a}{n},$$
when the limit exists (then $f$ is **integrable**). It is a number, not a function. Geometrically it is the **net area** between $y=f(x)$ and the $x$-axis on $[a,b]$ (area above minus area below). Continuous functions (and those with finitely many jumps) are integrable.

The integral is evaluated in practice via the [[fundamental-theorem-of-calculus]]: find an antiderivative $F$ and compute $F(b)-F(a)$. It is the integration counterpart of the [[limit]]-based definition of the derivative, and the area-problem half of calculus previewed in [[ch00-preview]].

## Related Pages
- [[ch04-integrals]] — Stewart Calculus 9e, §4.1–4.2 (definition)
- [[fundamental-theorem-of-calculus]] — how the integral is actually computed
- [[limit]] — the integral is defined as a limit of sums
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]]
