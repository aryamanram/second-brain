---
title: "Chain Rule"
tags: [concept, calculus, mathematics, differentiation]
date_created: 2026-06-19
date_updated: 2026-06-19
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chain Rule

The **chain rule** differentiates a **composite function**. If $y=f(u)$ and $u=g(x)$ are differentiable, then $y=f(g(x))$ is differentiable and
$$\frac{dy}{dx}=\frac{dy}{du}\cdot\frac{du}{dx},\qquad\text{equivalently}\qquad \big(f\circ g\big)'(x)=f'\big(g(x)\big)\,g'(x).$$
In words: the [[derivative]] of a composition is the outer derivative (evaluated at the inner function) times the inner derivative.

**Why it matters:**
- It is the engine behind most nontrivial differentiation, and the basis of **implicit differentiation** and **related rates**.
- Reversed, it becomes **substitution** ($u$-substitution), the most important technique of integration.
- It generalizes to several variables (the multivariable chain rule with tree diagrams) and underlies **backpropagation** in neural networks.

In [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] the chain rule is introduced in [[ch02-derivatives|§2.5]], reappears as $u$-substitution in [[ch04-integrals|Ch.4]] and the techniques of [[ch07-techniques-of-integration|Ch.7]], and is generalized to functions of several variables in [[ch14-partial-derivatives|§14.5]].

## Related Pages
- [[derivative]] — the operation the chain rule extends to compositions
- [[antiderivative]] — substitution is the chain rule run backwards
- [[ch02-derivatives]] · [[ch14-partial-derivatives]] — single- and multivariable chain rule
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — source
