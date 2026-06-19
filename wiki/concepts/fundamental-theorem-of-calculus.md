---
title: "Fundamental Theorem of Calculus"
tags: [calculus, mathematics, integration, theorem, foundational-concept]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Fundamental Theorem of Calculus (FTC)

The theorem that unifies calculus by showing **differentiation and integration are inverse processes**. Established by [[isaac-newton|Newton]] and [[gottfried-leibniz|Leibniz]] (building on Isaac Barrow).

**Part 1:** if $f$ is continuous on $[a,b]$, then $g(x)=\displaystyle\int_a^x f(t)\,dt$ is differentiable and
$$\frac{d}{dx}\int_a^x f(t)\,dt = f(x).$$
Differentiating an integral with a variable upper limit returns the integrand.

**Part 2:** if $f$ is continuous on $[a,b]$ and $F$ is any antiderivative of $f$, then
$$\int_a^b f(x)\,dx = F(b) - F(a).$$
This makes the [[definite-integral]] computable: antidifferentiate, then evaluate at the endpoints. Both parts require $f$ continuous on $[a,b]$.

The FTC is the central result foreshadowed by the area-vs-tangent connection in [[ch00-preview]] — it links the [[definite-integral|integral]] (area problem) to the derivative (tangent problem).

## Related Pages
- [[ch04-integrals]] — Stewart Calculus 9e, §4.3 (FTC Parts 1 & 2)
- [[definite-integral]] — what the FTC lets you compute
- [[continuity]] — the hypothesis both parts require
- [[isaac-newton]] · [[gottfried-leibniz]] — established the theorem
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]]
