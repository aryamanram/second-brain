---
title: "Stewart Calculus 9e — Ch.14: Partial Derivatives"
tags: [book, calculus, mathematics, multivariable, partial-derivatives, optimization, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 14 — Partial Derivatives

Chapter 14 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 971–1074; PDF pp. 1008–1111). Extends differential calculus to **functions of several variables**. The core idea is the **partial derivative** — the rate of change with respect to one variable while the others are held fixed — which generalizes to the **gradient**, **directional derivatives**, **tangent planes**, the multivariable **Chain Rule**, and **optimization** (including constrained optimization via Lagrange multipliers).

## 14.1 Functions of Several Variables
A **function of two variables** $f(x,y)$ assigns a number $z$ to each point $(x,y)$ in a domain $D\subseteq\mathbb{R}^2$; functions of three or more variables are analogous. They are studied verbally, numerically (tables), algebraically, and **visually** — via the **graph** (a surface) or **level curves / contour maps** (curves $f(x,y)=k$, like elevation contours; for three variables, **level surfaces**). Example: the **Cobb-Douglas production function** $P(L,K)$.

## 14.2 Limits and Continuity
$\lim_{(x,y)\to(a,b)}f(x,y)=L$ requires $f$ to approach $L$ along **every** path to $(a,b)$. **To show a limit does not exist**, find two paths giving different limits. $f$ is **continuous** at $(a,b)$ if $\lim_{(x,y)\to(a,b)}f(x,y)=f(a,b)$; polynomials and rational functions are continuous on their domains.

## 14.3 Partial Derivatives
The **partial derivative** of $f$ with respect to $x$ holds $y$ constant:
$$f_x(a,b)=\lim_{h\to 0}\frac{f(a+h,b)-f(a,b)}{h}=\frac{\partial z}{\partial x},$$
and $f_y$ analogously. Geometrically, $f_x$ is the slope of the surface in the $x$-direction. **Higher partials** exist ($f_{xx},f_{yy},f_{xy},f_{yx}$); **Clairaut's Theorem** says the mixed partials are equal ($f_{xy}=f_{yx}$) when continuous. Many physical laws are **partial differential equations** (the heat, wave, and Laplace equations).

## 14.4 Tangent Planes and Linear Approximations
For a differentiable $f$, the **tangent plane** to $z=f(x,y)$ at $(a,b)$ is
$$z = f(a,b) + f_x(a,b)(x-a) + f_y(a,b)(y-b).$$
The right side is the **linearization** $L(x,y)$, giving the **linear (tangent-plane) approximation** $f(x,y)\approx L(x,y)$ near $(a,b)$. The **total differential** $dz=f_x\,dx+f_y\,dy$ estimates the change $\Delta z$ and propagated error. ($f$ is **differentiable** at $(a,b)$ if $\Delta z$ has this linear form; continuity of $f_x,f_y$ guarantees it.)

## 14.5 The Chain Rule
For composite functions of several variables, derivatives sum the contributions through each intermediate variable. **General version:** if $u=f(x_1,\dots,x_n)$ and each $x_i=x_i(t_1,\dots,t_m)$, then
$$\frac{\partial u}{\partial t_j}=\frac{\partial u}{\partial x_1}\frac{\partial x_1}{\partial t_j}+\cdots+\frac{\partial u}{\partial x_n}\frac{\partial x_n}{\partial t_j}.$$
Tree diagrams organize the terms. Also yields **implicit differentiation** formulas for $F(x,y)=0$ and $F(x,y,z)=0$.

## 14.6 Directional Derivatives and the Gradient Vector
The **directional derivative** of $f$ in the direction of a unit vector $\mathbf{u}=\langle a,b\rangle$ is $D_{\mathbf{u}}f=f_x a+f_y b$. Collecting the partials gives the **gradient vector**
$$\nabla f = \langle f_x, f_y\rangle \quad(\text{or }\langle f_x,f_y,f_z\rangle), \qquad D_{\mathbf{u}}f=\nabla f\cdot\mathbf{u}.$$
Key facts: $\nabla f$ points in the **direction of fastest increase**, with maximum rate $|\nabla f|$; and $\nabla f$ is **orthogonal to the level curves/surfaces** of $f$ (giving tangent planes to level surfaces).

## 14.7 Maximum and Minimum Values
- **Local extrema** occur only at **critical points** where $\nabla f=\mathbf{0}$ ($f_x=f_y=0$).
- **Second Derivatives Test:** with $D=f_{xx}f_{yy}-(f_{xy})^2$ at a critical point — if $D>0$ and $f_{xx}>0$, local minimum; if $D>0$ and $f_{xx}<0$, local maximum; if $D<0$, **saddle point**; if $D=0$, inconclusive.
- **Absolute extrema** on a closed, bounded set: by the **Extreme Value Theorem** they exist; find them by checking critical points inside and the boundary.

## 14.8 Lagrange Multipliers
To optimize $f(x,y,z)$ subject to a **constraint** $g(x,y,z)=k$: at an extremum the gradients are parallel, so solve
$$\nabla f = \lambda\,\nabla g, \qquad g(x,y,z)=k,$$
where $\lambda$ is the **Lagrange multiplier**. (Geometrically, the level surface of $f$ is tangent to the constraint surface.) Two constraints use $\nabla f=\lambda\nabla g+\mu\nabla h$. A standard method for constrained optimization (resource allocation, geometry, the Cobb-Douglas problem).

## Key Takeaways
- **Functions of several variables** are visualized by surfaces and **level curves/contour maps**; limits must agree along all paths (two paths with different limits ⇒ no limit).
- The **partial derivative** holds other variables fixed; mixed partials commute (Clairaut). The **tangent plane**/**linearization** $z=f(a,b)+f_x(x-a)+f_y(y-b)$ approximates $f$ near a point.
- The **gradient** $\nabla f$ packs the partials: $D_{\mathbf{u}}f=\nabla f\cdot\mathbf{u}$, $\nabla f$ points in the direction of steepest ascent (magnitude $|\nabla f|$) and is orthogonal to level sets.
- **Optimization**: critical points + the **Second Derivatives Test** (discriminant $D$) classify local extrema and saddles; **Lagrange multipliers** ($\nabla f=\lambda\nabla g$) handle constrained optimization.

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch13-vector-functions]] — previous chapter
- [[ch15-multiple-integrals]] — next chapter; integration of multivariable functions
- [[ch12-vectors-geometry-of-space]] — quadric surfaces and vectors underlie graphs, gradients, tangent planes
- [[ch03-applications-of-differentiation]] — single-variable max/min, critical points, and the Second Derivative Test generalized here
- [[gradient]] · [[chain-rule]] · [[derivative]] — the gradient (§14.6) and multivariable chain rule (§14.5) generalize the single-variable derivative
