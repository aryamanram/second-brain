---
title: "Stewart Calculus 9e — Ch.13: Vector Functions"
tags: [book, calculus, mathematics, vectors, space-curves, curvature, motion, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 13 — Vector Functions

Chapter 13 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 927–970; PDF pp. 964–1007). Applies the calculus of [[ch02-derivatives|Ch.2]]–[[ch04-integrals|Ch.4]] to **vector-valued functions** — functions whose output is a vector in the space of [[ch12-vectors-geometry-of-space|Ch.12]]. These trace **space curves**, and differentiating/integrating them describes the geometry of curves (tangent, curvature) and the **motion of objects** (velocity, acceleration) — culminating in a derivation of Kepler's First Law.

## 13.1 Vector Functions and Space Curves
A **vector function** $\mathbf{r}(t)=\langle f(t),g(t),h(t)\rangle=f(t)\mathbf{i}+g(t)\mathbf{j}+h(t)\mathbf{k}$ assigns a vector to each $t$; its **component functions** $f,g,h$ are ordinary real-valued functions. As $t$ varies, the tip of $\mathbf{r}(t)$ traces a **space curve**. Limits are taken componentwise ($\lim \mathbf{r}(t)=\langle \lim f,\lim g,\lim h\rangle$), and $\mathbf{r}$ is continuous where its components are. Space curves are visualized as the intersection of surfaces (e.g. the helix, the trefoil knot).

## 13.2 Derivatives and Integrals of Vector Functions
The **derivative** $\mathbf{r}'(t)=\lim_{h\to 0}\frac{\mathbf{r}(t+h)-\mathbf{r}(t)}{h}$ is computed componentwise: $\mathbf{r}'(t)=\langle f'(t),g'(t),h'(t)\rangle$. Geometrically $\mathbf{r}'(t)$ is the **tangent vector** to the curve (and the **unit tangent** is $\mathbf{T}(t)=\frac{\mathbf{r}'(t)}{|\mathbf{r}'(t)|}$). Differentiation rules mirror the scalar ones, including product rules for dot and cross products. **Integration** is also componentwise, with an FTC analogue.

## 13.3 Arc Length and Curvature
- **Arc length** of a space curve $\mathbf{r}(t)$ on $[a,b]$:
$$L=\int_a^b |\mathbf{r}'(t)|\,dt = \int_a^b \sqrt{[f'(t)]^2+[g'(t)]^2+[h'(t)]^2}\,dt.$$
A curve can be reparametrized by arc length $s$ (a natural, parametrization-independent parameter).
- **Curvature** $\kappa$ measures how sharply a curve bends — the rate of change of the unit tangent with respect to arc length:
$$\kappa=\left|\frac{d\mathbf{T}}{ds}\right|=\frac{|\mathbf{T}'(t)|}{|\mathbf{r}'(t)|}=\frac{|\mathbf{r}'(t)\times\mathbf{r}''(t)|}{|\mathbf{r}'(t)|^3}.$$
For a plane curve $y=f(x)$: $\kappa=\dfrac{|f''(x)|}{[1+(f'(x))^2]^{3/2}}$.
- **TNB frame:** the unit tangent $\mathbf{T}$, the **principal unit normal** $\mathbf{N}=\frac{\mathbf{T}'}{|\mathbf{T}'|}$, and the **binormal** $\mathbf{B}=\mathbf{T}\times\mathbf{N}$ form a moving orthonormal frame. The plane of $\mathbf{T}$ and $\mathbf{N}$ is the **osculating plane**; the **osculating circle** (radius $1/\kappa$) best fits the curve at a point. The **Frenet-Serret formulas** relate the derivatives of $\mathbf{T},\mathbf{N},\mathbf{B}$ (introducing **torsion** $\tau$).

## 13.4 Motion in Space: Velocity and Acceleration
For a particle with position $\mathbf{r}(t)$:
- **Velocity** $\mathbf{v}(t)=\mathbf{r}'(t)$ (tangent to the path); **speed** $=|\mathbf{v}(t)|=\frac{ds}{dt}$; **acceleration** $\mathbf{a}(t)=\mathbf{v}'(t)=\mathbf{r}''(t)$.
- Integrating recovers velocity and position from acceleration. With **Newton's Second Law** $\mathbf{F}=m\mathbf{a}$, force determines motion (e.g. a centripetal force gives circular motion; **projectile motion** under gravity $\mathbf{a}=-g\mathbf{j}$ gives the parabolic trajectory, with range maximized at launch angle $45°$).
- **Tangential and normal components** of acceleration: $\mathbf{a}=a_T\mathbf{T}+a_N\mathbf{N}$, where $a_T=v'$ (change in speed) and $a_N=\kappa v^2$ (turning) — separating "speeding up" from "changing direction."
- The chapter closes by deriving **Kepler's First Law** (elliptical orbits) from Newton's law of gravitation, following the footsteps of [[isaac-newton|Newton]] and [[johannes-kepler|Kepler]].

## Key Takeaways
- A **vector function** $\mathbf{r}(t)$ traces a **space curve**; limits, derivatives, and integrals are all computed componentwise.
- $\mathbf{r}'(t)$ is the **tangent vector**; **arc length** is $\int|\mathbf{r}'(t)|\,dt$, and **curvature** $\kappa=\frac{|\mathbf{r}'\times\mathbf{r}''|}{|\mathbf{r}'|^3}$ measures bending, with the **TNB frame** (tangent, normal, binormal) and osculating circle describing local geometry.
- **Motion**: velocity $\mathbf{v}=\mathbf{r}'$, speed $|\mathbf{v}|$, acceleration $\mathbf{a}=\mathbf{r}''$; with $\mathbf{F}=m\mathbf{a}$ this models projectiles and orbits.
- Acceleration splits into **tangential** ($a_T=v'$, changing speed) and **normal** ($a_N=\kappa v^2$, changing direction) components; the chapter derives **Kepler's First Law** from gravitation.

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch12-vectors-geometry-of-space]] — previous chapter; the vectors and dot/cross products used throughout
- [[ch14-partial-derivatives]] — next chapter; calculus of functions of several variables
- [[ch10-parametric-and-polar]] — parametric curves and arc length, here in 3D
- [[isaac-newton]] · [[johannes-kepler]] — Newton's Second Law and the derivation of Kepler's First Law (§13.4)
