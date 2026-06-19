---
title: "Derivative"
tags: [concept, calculus, mathematics, differentiation]
date_created: 2026-06-19
date_updated: 2026-06-19
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Derivative

The **derivative** of a function $f$ at a number $a$ is the instantaneous rate of change of $f$ — equivalently, the slope of the tangent line to the graph $y=f(x)$ at the point $(a,f(a))$. It is defined as a [[limit]] of difference quotients:
$$f'(a)=\lim_{h\to 0}\frac{f(a+h)-f(a)}{h}=\lim_{x\to a}\frac{f(x)-f(a)}{x-a},$$
when the limit exists (in which case $f$ is **differentiable** at $a$). Viewing $a$ as variable gives the **derivative function** $f'$, also written $\frac{dy}{dx}$, $\frac{df}{dx}$, or $Df$ (Leibniz / Lagrange / operator notations).

**Key facts:**
- **Differentiability ⇒ [[continuity]]**, but not conversely (e.g. $|x|$ at $0$).
- **Interpretations:** slope of a tangent, velocity (derivative of position), marginal cost, and any instantaneous rate of change.
- **Rules** make computation mechanical: power, constant-multiple, sum, **product**, **quotient**, and the **[[chain-rule|chain rule]]** for compositions. Higher derivatives $f'',f''',\dots$ measure concavity, acceleration, etc.
- The derivative is one of the two central operations of calculus; it is inverse (via the [[fundamental-theorem-of-calculus|Fundamental Theorem of Calculus]]) to the [[definite-integral|integral]]. An **[[antiderivative]]** reverses differentiation.

In [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] the derivative is introduced in [[ch02-derivatives|Ch.2]] and applied throughout — optimization and curve-sketching ([[ch03-applications-of-differentiation|Ch.3]]), motion ([[ch13-vector-functions|Ch.13]]), and, generalized to several variables, the partial derivative and [[gradient]] ([[ch14-partial-derivatives|Ch.14]]).

## Related Pages
- [[limit]] — the derivative is defined as a limit of difference quotients
- [[continuity]] — differentiability implies continuity
- [[chain-rule]] · [[antiderivative]] — the composition rule and the inverse operation
- [[mean-value-theorem]] — relates the derivative to average rate of change
- [[gradient]] — the multivariable generalization (vector of partial derivatives)
- [[fundamental-theorem-of-calculus]] · [[definite-integral]] — differentiation and integration as inverse operations
- [[ch02-derivatives]] · [[ch03-applications-of-differentiation]] — where the derivative is developed
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — source
