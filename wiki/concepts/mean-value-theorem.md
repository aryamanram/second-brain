---
title: "Mean Value Theorem"
tags: [concept, calculus, mathematics, differentiation, theorem]
date_created: 2026-06-19
date_updated: 2026-06-19
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Mean Value Theorem

The **Mean Value Theorem (MVT)** states: if $f$ is [[continuity|continuous]] on $[a,b]$ and differentiable on $(a,b)$, then there exists a number $c\in(a,b)$ with
$$f'(c)=\frac{f(b)-f(a)}{b-a}.$$
Geometrically, at some interior point the tangent line is parallel to the secant line through the endpoints — the instantaneous rate of change equals the average rate of change somewhere on the interval. The special case $f(a)=f(b)$ is **Rolle's Theorem** (some $c$ has $f'(c)=0$).

**Why it matters:** the MVT is the workhorse behind much of differential calculus theory. Its corollaries justify everyday facts: if $f'(x)=0$ throughout an interval then $f$ is constant; if two functions have equal derivatives they differ by a constant (the basis for "$+C$" in [[antiderivative|antiderivatives]]); and the sign of $f'$ determines where $f$ increases or decreases. It is also used to prove the [[fundamental-theorem-of-calculus|Fundamental Theorem of Calculus]].

In [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] the MVT appears in [[ch03-applications-of-differentiation|§3.2]] and is invoked across the applications and integration chapters.

## Related Pages
- [[derivative]] — the MVT relates instantaneous to average rate of change
- [[continuity]] — a hypothesis of the theorem
- [[antiderivative]] — the "equal derivatives ⇒ differ by a constant" corollary
- [[fundamental-theorem-of-calculus]] — proved using the MVT
- [[ch03-applications-of-differentiation]] — where the MVT is developed
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — source
