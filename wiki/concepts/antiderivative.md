---
title: "Antiderivative"
tags: [concept, calculus, mathematics, integration]
date_created: 2026-06-19
date_updated: 2026-06-19
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Antiderivative

An **antiderivative** of a function $f$ on an interval is a function $F$ whose [[derivative]] is $f$: $F'(x)=f(x)$. Antidifferentiation reverses differentiation. If $F$ is one antiderivative of $f$, then **every** antiderivative has the form $F(x)+C$ for an arbitrary constant $C$ (a consequence of the [[mean-value-theorem|Mean Value Theorem]]); this family is the **indefinite integral**
$$\int f(x)\,dx=F(x)+C.$$

**Antiderivative vs. integral:** the indefinite integral denotes the family of antiderivatives (a *function*), whereas the [[definite-integral|definite integral]] $\int_a^b f\,dx$ is a *number* (a limit of Riemann sums). The two are bridged by the [[fundamental-theorem-of-calculus|Fundamental Theorem of Calculus]]: $\int_a^b f(x)\,dx=F(b)-F(a)$, so a definite integral is evaluated by finding any antiderivative. This is why techniques for *finding* antiderivatives (substitution, integration by parts, partial fractions) are central to integration.

In [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] antiderivatives are introduced in [[ch03-applications-of-differentiation|§3.9]] and are the object sought throughout [[ch04-integrals|Ch.4]] and the techniques chapter [[ch07-techniques-of-integration|Ch.7]].

## Related Pages
- [[derivative]] — antidifferentiation is its inverse
- [[definite-integral]] — a number, evaluated via an antiderivative
- [[fundamental-theorem-of-calculus]] — connects antiderivatives to definite integrals
- [[chain-rule]] · [[mean-value-theorem]] — substitution reverses the chain rule; the "+C" follows from the MVT
- [[ch04-integrals]] · [[ch07-techniques-of-integration]] — finding antiderivatives
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — source
