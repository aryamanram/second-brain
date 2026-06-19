---
title: "Stewart Calculus 9e — Ch.12: Vectors and the Geometry of Space"
tags: [book, calculus, mathematics, vectors, linear-algebra, 3d-geometry, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 12 — Vectors and the Geometry of Space

Chapter 12 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 867–926; PDF pp. 904–963). The gateway to **multivariable calculus**: it sets up three-dimensional space and the algebra of **vectors** (the two products — dot and cross — and their geometric meaning), then uses them to describe lines, planes, and curved surfaces in space.

## 12.1 Three-Dimensional Coordinate Systems
Points in space are located by ordered triples $(a,b,c)$ relative to three mutually perpendicular **coordinate axes** through the origin $O$, oriented by the **right-hand rule**. The three **coordinate planes** ($xy$, $yz$, $xz$) divide space into eight **octants**. The **distance** between $P_1(x_1,y_1,z_1)$ and $P_2(x_2,y_2,z_2)$ is $\sqrt{(x_2-x_1)^2+(y_2-y_1)^2+(z_2-z_1)^2}$; a sphere of radius $r$ centered at $(h,k,l)$ is $(x-h)^2+(y-k)^2+(z-l)^2=r^2$.

## 12.2 Vectors
A **vector** has both magnitude and direction (an arrow); examples include displacement, velocity, force. Vectors are added by the **Triangle Law** / **Parallelogram Law**, and scaled by **scalar multiplication** ($c\mathbf{v}$ stretches by $|c|$, reversing direction if $c<0$). In components $\mathbf{a}=\langle a_1,a_2,a_3\rangle$: add componentwise; the **magnitude** is $|\mathbf{a}|=\sqrt{a_1^2+a_2^2+a_3^2}$. The **standard basis vectors** are $\mathbf{i},\mathbf{j},\mathbf{k}$; a **unit vector** in the direction of $\mathbf{a}$ is $\mathbf{a}/|\mathbf{a}|$. Applications include resolving forces and finding the resultant velocity (e.g. true course of a plane in wind).

## 12.3 The Dot Product
The **dot product** $\mathbf{a}\cdot\mathbf{b}=a_1b_1+a_2b_2+a_3b_3$ (a *scalar*). Geometrically (from the Law of Cosines):
$$\mathbf{a}\cdot\mathbf{b}=|\mathbf{a}|\,|\mathbf{b}|\cos\theta,$$
where $\theta$ is the angle between them — so $\mathbf{a}\cdot\mathbf{b}=0$ iff the vectors are **orthogonal**. The dot product gives angles, and **projections**: the scalar projection $\text{comp}_{\mathbf{a}}\mathbf{b}=\frac{\mathbf{a}\cdot\mathbf{b}}{|\mathbf{a}|}$ and the vector projection $\text{proj}_{\mathbf{a}}\mathbf{b}=\frac{\mathbf{a}\cdot\mathbf{b}}{|\mathbf{a}|^2}\mathbf{a}$. Used to compute **work** $W=\mathbf{F}\cdot\mathbf{D}$.

## 12.4 The Cross Product
The **cross product** $\mathbf{a}\times\mathbf{b}$ is a *vector* **orthogonal to both** $\mathbf{a}$ and $\mathbf{b}$ (direction by the right-hand rule), computed as a symbolic determinant:
$$\mathbf{a}\times\mathbf{b}=\begin{vmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\a_1&a_2&a_3\\b_1&b_2&b_3\end{vmatrix}.$$
Its magnitude is $|\mathbf{a}\times\mathbf{b}|=|\mathbf{a}|\,|\mathbf{b}|\sin\theta$ — the **area of the parallelogram** spanned by $\mathbf{a}$ and $\mathbf{b}$ — so $\mathbf{a}\times\mathbf{b}=\mathbf{0}$ iff the vectors are parallel. It is anticommutative ($\mathbf{b}\times\mathbf{a}=-\mathbf{a}\times\mathbf{b}$). The **scalar triple product** $\mathbf{a}\cdot(\mathbf{b}\times\mathbf{c})$ gives the volume of the parallelepiped. Applications: **torque** $\boldsymbol{\tau}=\mathbf{r}\times\mathbf{F}$. (The cross product is tied to the quaternions of [[william-rowan-hamilton|William Rowan Hamilton]].)

## 12.5 Equations of Lines and Planes
- **Line** through $\mathbf{r}_0=(x_0,y_0,z_0)$ with direction $\mathbf{v}=\langle a,b,c\rangle$: vector form $\mathbf{r}=\mathbf{r}_0+t\mathbf{v}$; **parametric equations** $x=x_0+at$, $y=y_0+bt$, $z=z_0+ct$; **symmetric equations** $\frac{x-x_0}{a}=\frac{y-y_0}{b}=\frac{z-z_0}{c}$.
- **Plane** through $P_0$ with **normal vector** $\mathbf{n}=\langle a,b,c\rangle$: $\mathbf{n}\cdot(\mathbf{r}-\mathbf{r}_0)=0$, i.e. the scalar equation $a(x-x_0)+b(y-y_0)+c(z-z_0)=0$, or $ax+by+cz+d=0$.
- **Distance** from a point $(x_1,y_1,z_1)$ to the plane $ax+by+cz+d=0$ is $\dfrac{|ax_1+by_1+cz_1+d|}{\sqrt{a^2+b^2+c^2}}$. Two planes are parallel if their normals are parallel; the angle between them is the angle between normals.

## 12.6 Cylinders and Quadric Surfaces
- A **cylinder** is a surface of parallel lines (rulings) through a given plane curve (e.g. $z=x^2$ is a parabolic cylinder, with the missing variable indicating the ruling direction).
- A **quadric surface** is the graph of a second-degree equation in $x,y,z$; standard forms include the **ellipsoid** $\frac{x^2}{a^2}+\frac{y^2}{b^2}+\frac{z^2}{c^2}=1$, **elliptic paraboloid** $z=\frac{x^2}{a^2}+\frac{y^2}{b^2}$, **hyperbolic paraboloid** (saddle) $z=\frac{x^2}{a^2}-\frac{y^2}{b^2}$, **cone**, and **hyperboloids** (of one or two sheets). They are sketched from **traces** — the cross-sections in planes parallel to the coordinate planes (the 3D counterparts of the conic sections of [[ch10-parametric-and-polar|§10.5]]).

## Key Takeaways
- **3D coordinate space**: points $(a,b,c)$, the distance formula, and spheres set the stage; the **right-hand rule** orients the axes.
- **Vectors** carry magnitude and direction; the **dot product** $\mathbf{a}\cdot\mathbf{b}=|\mathbf{a}||\mathbf{b}|\cos\theta$ (scalar — angles, projections, work) and the **cross product** $\mathbf{a}\times\mathbf{b}$ (vector orthogonal to both, magnitude $|\mathbf{a}||\mathbf{b}|\sin\theta$ = parallelogram area — torque, normals) are the two essential products.
- **Lines** (vector/parametric/symmetric equations) and **planes** (normal-vector equation, point-to-plane distance) are described with these vectors.
- **Quadric surfaces** (ellipsoid, paraboloids, hyperboloids, cones) are visualized via **traces** — extending conic sections to three dimensions.

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch11-sequences-series-power-series]] — previous chapter
- [[ch13-vector-functions]] — next chapter; vector-valued functions and motion in space
- [[ch10-parametric-and-polar]] — conic sections, generalized here to quadric surfaces
- [[william-rowan-hamilton|William Rowan Hamilton]] — quaternions, precursor of vector analysis (§12.4)
