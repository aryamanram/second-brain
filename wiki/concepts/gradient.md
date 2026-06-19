---
title: "Gradient"
tags: [concept, calculus, mathematics, multivariable, vector-calculus]
date_created: 2026-06-19
date_updated: 2026-06-19
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Gradient

The **gradient** of a scalar function $f$ of several variables is the vector of its first-order partial [[derivative|derivatives]]:
$$\nabla f=\langle f_x, f_y\rangle\quad\text{(two variables)},\qquad \nabla f=\langle f_x, f_y, f_z\rangle\quad\text{(three variables)},$$
formed with the **del operator** $\nabla=\langle\partial/\partial x,\partial/\partial y,\partial/\partial z\rangle$. It is the multivariable generalization of the derivative.

**Key facts:**
- The **directional derivative** in the direction of a unit vector $\mathbf{u}$ is $D_{\mathbf u}f=\nabla f\cdot\mathbf u$.
- $\nabla f$ points in the **direction of steepest increase** of $f$, and its magnitude $|\nabla f|$ is the maximum rate of increase.
- $\nabla f$ is **orthogonal to the level curves/surfaces** of $f$, which gives tangent planes to level surfaces and makes the gradient the basis of **gradient descent** in optimization and machine learning.
- A vector field that is a gradient, $\mathbf F=\nabla f$, is **conservative**, with $f$ its potential function (the link from the gradient to [[ch16-vector-calculus|vector calculus]]).

In [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] the gradient is introduced in [[ch14-partial-derivatives|§14.6]] and is central to conservative fields and the curl/divergence operators in [[ch16-vector-calculus|Ch.16]].

## Related Pages
- [[derivative]] — the gradient generalizes the derivative to several variables
- [[ch14-partial-derivatives]] — gradient, directional derivatives, steepest ascent (§14.6)
- [[ch16-vector-calculus]] — gradient (conservative) vector fields and potential functions
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — source
