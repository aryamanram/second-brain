---
title: "Stewart Calculus 9e — Ch.16: Vector Calculus"
tags: [book, calculus, mathematics, vector-calculus, line-integrals, surface-integrals, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 16 — Vector Calculus

The final chapter of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 1161–1254; PDF pp. 1198–1291). It develops the calculus of **vector fields** — functions that assign a vector to each point of the plane or space — and integrates them along **curves** (line integrals) and over **surfaces** (surface integrals). The chapter's summit is a family of **fundamental theorems** (Green's, Stokes', the Divergence Theorem) that generalize the [[fundamental-theorem-of-calculus|FTC]]: each relates an integral over a region to an integral over its boundary.

## 16.1 Vector Fields
A **vector field** on $\mathbb{R}^2$ or $\mathbb{R}^3$ assigns a vector $\mathbf{F}(x,y)$ or $\mathbf{F}(x,y,z)$ to each point, written $\mathbf{F}=P\,\mathbf{i}+Q\,\mathbf{j}+R\,\mathbf{k}$ with component (scalar) functions $P,Q,R$. They model velocity (wind, fluid flow), force (gravitational, electric), and more. A **gradient field** $\mathbf{F}=\nabla f$ arises from a scalar **potential function** $f$; such fields are called **conservative**.

## 16.2 Line Integrals
The **line integral** of a scalar function along a curve $C$ (parametrized by $\mathbf{r}(t)$, $a\le t\le b$) integrates with respect to arc length:
$$\int_C f(x,y)\,ds=\int_a^b f(\mathbf{r}(t))\,|\mathbf{r}'(t)|\,dt.$$
The **line integral of a vector field** $\mathbf{F}$ along $C$ measures **work** done by the field on a particle moving along $C$:
$$\int_C \mathbf{F}\cdot d\mathbf{r}=\int_a^b \mathbf{F}(\mathbf{r}(t))\cdot\mathbf{r}'(t)\,dt=\int_C \mathbf{F}\cdot\mathbf{T}\,ds=\int_C P\,dx+Q\,dy+R\,dz.$$
Orientation matters: reversing the curve negates the vector line integral.

## 16.3 The Fundamental Theorem for Line Integrals
For a **conservative** field $\mathbf{F}=\nabla f$, the line integral depends only on the endpoints:
$$\int_C \nabla f\cdot d\mathbf{r}=f(\mathbf{r}(b))-f(\mathbf{r}(a)).$$
This is the FTC for line integrals. Consequences: such integrals are **independent of path**, and around any closed curve $\oint_C\mathbf{F}\cdot d\mathbf{r}=0$. On an open connected region, path-independence ⇔ $\mathbf{F}$ is conservative. A test on a simply-connected domain: $\mathbf{F}=P\mathbf{i}+Q\mathbf{j}$ is conservative iff $\partial P/\partial y=\partial Q/\partial x$. This is the field analogue of **conservation of energy**.

## 16.4 Green's Theorem
**Green's Theorem** (after [[george-green|George Green]]) relates a line integral around a simple closed curve $C$ (positively oriented, counterclockwise) to a double integral over the plane region $D$ it bounds:
$$\oint_C P\,dx+Q\,dy=\iint_D\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)\,dA.$$
It is the two-dimensional case of both Stokes' Theorem and the Divergence Theorem. Among its uses: computing areas via $A=\oint_C x\,dy=-\oint_C y\,dx=\tfrac12\oint_C (x\,dy-y\,dx)$.

## 16.5 Curl and Divergence
With the **del operator** $\nabla=\mathbf{i}\,\partial/\partial x+\mathbf{j}\,\partial/\partial y+\mathbf{k}\,\partial/\partial z$:
- **Curl** (a vector measuring rotation): $\operatorname{curl}\mathbf{F}=\nabla\times\mathbf{F}$. If $\mathbf{F}$ is a conservative field then $\operatorname{curl}\mathbf{F}=\mathbf{0}$; conversely, on all of $\mathbb{R}^3$, $\operatorname{curl}\mathbf{F}=\mathbf{0}$ implies $\mathbf{F}$ is conservative.
- **Divergence** (a scalar measuring net outflow): $\operatorname{div}\mathbf{F}=\dfrac{\partial P}{\partial x}+\dfrac{\partial Q}{\partial y}+\dfrac{\partial R}{\partial z}=\nabla\cdot\mathbf{F}$. A field with $\operatorname{div}\mathbf{F}=0$ is **incompressible**.
- Identity: $\operatorname{div}(\operatorname{curl}\mathbf{F})=0$. Green's Theorem has **vector forms** $\oint_C\mathbf{F}\cdot d\mathbf{r}=\iint_D(\operatorname{curl}\mathbf{F})\cdot\mathbf{k}\,dA$ and $\oint_C\mathbf{F}\cdot\mathbf{n}\,ds=\iint_D\operatorname{div}\mathbf{F}\,dA$.

## 16.6 Parametric Surfaces and Their Areas
A **parametric surface** is given by $\mathbf{r}(u,v)=x(u,v)\mathbf{i}+y(u,v)\mathbf{j}+z(u,v)\mathbf{k}$. The tangent vectors $\mathbf{r}_u,\mathbf{r}_v$ give a normal $\mathbf{r}_u\times\mathbf{r}_v$, and the **surface area** is
$$A(S)=\iint_D|\mathbf{r}_u\times\mathbf{r}_v|\,dA,$$
which specializes to the Ch.15 formula for a graph $z=f(x,y)$.

## 16.7 Surface Integrals
The **surface integral of a scalar function**: $\iint_S f\,dS=\iint_D f(\mathbf{r}(u,v))\,|\mathbf{r}_u\times\mathbf{r}_v|\,dA$ (e.g. mass of a sheet with given density). For an **oriented surface** with unit normal $\mathbf{n}$, the **flux** of a vector field through $S$ is
$$\iint_S \mathbf{F}\cdot d\mathbf{S}=\iint_S \mathbf{F}\cdot\mathbf{n}\,dS=\iint_D \mathbf{F}\cdot(\mathbf{r}_u\times\mathbf{r}_v)\,dA,$$
the rate at which fluid (or electric/heat field) crosses the surface. Non-orientable surfaces (the Möbius strip) have no consistent normal.

## 16.8 Stokes' Theorem
**Stokes' Theorem** (after [[george-stokes|George Stokes]]) is the higher-dimensional generalization of Green's Theorem: it relates the surface integral of the curl over an oriented surface $S$ to the line integral around its boundary curve $C=\partial S$:
$$\oint_C \mathbf{F}\cdot d\mathbf{r}=\iint_S \operatorname{curl}\mathbf{F}\cdot d\mathbf{S}.$$
The circulation of $\mathbf{F}$ around the boundary equals the total "curl flux" through the surface. (Green's Theorem is the flat-surface case.)

## 16.9 The Divergence Theorem
The **Divergence Theorem** (also the Gauss–Ostrogradsky theorem, after [[carl-friedrich-gauss|Gauss]] and Mikhail Ostrogradsky) relates the flux of $\mathbf{F}$ out of a closed surface $S$ to the divergence integrated over the solid region $E$ it encloses:
$$\iint_S \mathbf{F}\cdot d\mathbf{S}=\iiint_E \operatorname{div}\mathbf{F}\,dV.$$
The net outward flux through the boundary equals the total of the field's sources/sinks inside. It is the third member of the Green–Stokes–Divergence family and underlies Gauss's law in electromagnetism and the continuity equation in fluid flow.

## 16.10 Summary
The chapter (and the book) closes by unifying its theorems: Green's, Stokes', and the Divergence Theorem are all instances of one principle — **the integral of a derivative over a region equals an integral of the original function over the boundary** — the multivariable generalization of the [[fundamental-theorem-of-calculus|Fundamental Theorem of Calculus]].

## Key Takeaways
- A **vector field** $\mathbf{F}=P\mathbf{i}+Q\mathbf{j}+R\mathbf{k}$ is integrated along curves (**line integral** $\int_C\mathbf{F}\cdot d\mathbf{r}$ = work) and over surfaces (**flux** $\iint_S\mathbf{F}\cdot d\mathbf{S}$).
- A **conservative** field $\mathbf{F}=\nabla f$ has path-independent line integrals (**FTC for line integrals**), zero circulation on closed curves, and $\operatorname{curl}\mathbf{F}=\mathbf{0}$.
- **Curl** $\nabla\times\mathbf{F}$ (rotation) and **divergence** $\nabla\cdot\mathbf{F}$ (outflow) are the two first-order operators on fields, with $\operatorname{div}(\operatorname{curl}\mathbf{F})=0$.
- The **three big theorems** — Green's ($\oint_C P\,dx+Q\,dy=\iint_D(Q_x-P_y)\,dA$), **Stokes'** ($\oint_C\mathbf{F}\cdot d\mathbf{r}=\iint_S\operatorname{curl}\mathbf{F}\cdot d\mathbf{S}$), and the **Divergence Theorem** ($\iint_S\mathbf{F}\cdot d\mathbf{S}=\iiint_E\operatorname{div}\mathbf{F}\,dV$) — are all generalizations of the FTC: a derivative integrated over a region equals the function on its boundary.

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch15-multiple-integrals]] — previous chapter; double/triple integrals used in every theorem here
- [[ch13-vector-functions]] — parametrized curves $\mathbf{r}(t)$ and $\mathbf{r}'(t)$ underlying line integrals
- [[ch14-partial-derivatives]] — the gradient $\nabla f$; curl and divergence are built from partials
- [[fundamental-theorem-of-calculus]] — the single-variable theorem that Green's, Stokes', and the Divergence Theorem all generalize
- [[george-green]] · [[george-stokes]] · [[carl-friedrich-gauss]] — the mathematicians behind the chapter's three central theorems
