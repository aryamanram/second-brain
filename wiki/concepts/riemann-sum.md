---
title: "Riemann Sum"
tags: [concept, calculus, mathematics, integration]
date_created: 2026-06-19
date_updated: 2026-06-19
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Riemann Sum

A **Riemann sum** approximates the area under a curve (or, more generally, an integral) by summing the areas of finitely many rectangles. For $f$ on $[a,b]$, partition the interval into $n$ subintervals of width $\Delta x=(b-a)/n$ and choose a **sample point** $x_i^*$ in each:
$$\sum_{i=1}^{n} f(x_i^*)\,\Delta x.$$
Choosing $x_i^*$ as the left endpoint, right endpoint, or midpoint gives the left/right/midpoint sums. The **[[definite-integral|definite integral]]** is the [[limit]] of Riemann sums as the partition is refined:
$$\int_a^b f(x)\,dx=\lim_{n\to\infty}\sum_{i=1}^{n} f(x_i^*)\,\Delta x.$$

**Why it matters:** the Riemann sum *is* the definition of the integral — every integral interpretation (area, volume, mass, work, probability) comes from recognizing a quantity as a limit of such sums. The same construction generalizes directly to **double and triple integrals** (sums over sub-rectangles/boxes) and to **line and surface integrals**.

In [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] Riemann sums define the integral in [[ch04-integrals|§4.2]], recur throughout [[ch05-applications-of-integration|Ch.5]], and reappear as double/triple sums in [[ch15-multiple-integrals|Ch.15]].

## Related Pages
- [[definite-integral]] — defined as the limit of Riemann sums
- [[limit]] — the limiting process that defines the integral
- [[fundamental-theorem-of-calculus]] — the shortcut that avoids computing the limit directly
- [[ch04-integrals]] · [[ch15-multiple-integrals]] — single and multiple integrals as Riemann-sum limits
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — source
