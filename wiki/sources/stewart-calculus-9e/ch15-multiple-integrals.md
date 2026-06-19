---
title: "Stewart Calculus 9e — Ch.15: Multiple Integrals"
tags: [book, calculus, mathematics, multivariable, integration, jacobian, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 15 — Multiple Integrals

Chapter 15 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 1075–1160; PDF pp. 1112–1197). Extends the [[definite-integral|definite integral]] to functions of two and three variables — **double** and **triple integrals**. As in one variable, these are limits of Riemann sums, evaluated as **iterated integrals**, and they compute volumes, masses, centers of mass, and more. The chapter develops the change to **polar, cylindrical, and spherical coordinates** and the general **change of variables** via the Jacobian.

## 15.1 Double Integrals over Rectangles
The **double integral** of $f$ over a rectangle $R=[a,b]\times[c,d]$ is the limit of double Riemann sums $\iint_R f(x,y)\,dA=\lim\sum\sum f(x_{ij}^*,y_{ij}^*)\,\Delta A$; for $f\ge 0$ it is the **volume** under the surface $z=f(x,y)$. **Fubini's Theorem** (after Guido Fubini) evaluates it as an **iterated integral** in either order:
$$\iint_R f\,dA=\int_a^b\int_c^d f(x,y)\,dy\,dx=\int_c^d\int_a^b f(x,y)\,dx\,dy.$$

## 15.2 Double Integrals over General Regions
Over a non-rectangular region $D$: a **type I** region ($a\le x\le b$, $g_1(x)\le y\le g_2(x)$) integrates $\int_a^b\int_{g_1(x)}^{g_2(x)}f\,dy\,dx$; a **type II** region (bounded by $x=h_1(y),h_2(y)$) integrates in the other order. Properties mirror single integrals (linearity, additivity over subregions), and $\iint_D 1\,dA=A(D)$ gives the area. Sometimes **reversing the order of integration** makes an otherwise intractable integral evaluable.

## 15.3 Double Integrals in Polar Coordinates
For regions bounded by circles/rays, convert with $x=r\cos\theta$, $y=r\sin\theta$. The crucial point: the area element becomes $dA=r\,dr\,d\theta$ (the extra $r$ must not be omitted):
$$\iint_R f(x,y)\,dA=\int_\alpha^\beta\int_a^b f(r\cos\theta,r\sin\theta)\,r\,dr\,d\theta.$$

## 15.4 Applications of Double Integrals
- **Mass** of a lamina with density $\rho(x,y)$: $m=\iint_D\rho\,dA$.
- **Center of mass:** $\bar x=\frac{1}{m}\iint_D x\,\rho\,dA$, $\bar y=\frac{1}{m}\iint_D y\,\rho\,dA$.
- **Moments of inertia** (second moments): $I_x=\iint_D y^2\rho\,dA$, $I_y=\iint_D x^2\rho\,dA$, and polar moment $I_0=I_x+I_y$.
- **Probability:** joint density functions integrate to 1; expected values are moment integrals (e.g. independent normal random variables).

## 15.5 Surface Area
For a surface $z=f(x,y)$ over a region $D$ with continuous partials:
$$A(S)=\iint_D \sqrt{1+\left(\frac{\partial z}{\partial x}\right)^2+\left(\frac{\partial z}{\partial y}\right)^2}\,dA.$$

## 15.6 Triple Integrals
The **triple integral** $\iiint_E f(x,y,z)\,dV$ over a solid $E$ is the limit of triple Riemann sums, evaluated as an iterated integral over a **type 1/2/3** solid region (one variable bounded by surfaces, projected onto a coordinate plane). $\iiint_E 1\,dV$ gives the **volume** of $E$; mass and centers of mass extend the 2D formulas with a third coordinate.

## 15.7 Triple Integrals in Cylindrical Coordinates
**Cylindrical coordinates** $(r,\theta,z)$ combine polar coordinates in the $xy$-plane with $z$: $x=r\cos\theta$, $y=r\sin\theta$. Natural for solids with an axis of symmetry. Volume element:
$$dV=r\,dz\,dr\,d\theta.$$

## 15.8 Triple Integrals in Spherical Coordinates
**Spherical coordinates** $(\rho,\theta,\phi)$: $\rho=$ distance from origin, $\theta=$ azimuthal angle, $\phi=$ angle from the positive $z$-axis ($0\le\phi\le\pi$). Conversions: $x=\rho\sin\phi\cos\theta$, $y=\rho\sin\phi\sin\theta$, $z=\rho\cos\phi$, with $\rho^2=x^2+y^2+z^2$. Natural for balls and cones. Volume element:
$$dV=\rho^2\sin\phi\,d\rho\,d\theta\,d\phi.$$

## 15.9 Change of Variables in Multiple Integrals
A general substitution $x=g(u,v)$, $y=h(u,v)$ (a $C^1$, one-to-one **transformation** $T$) carries a region $S$ in the $uv$-plane to $R$ in the $xy$-plane. The area scaling factor is the **Jacobian**:
$$\frac{\partial(x,y)}{\partial(u,v)}=\begin{vmatrix}\partial x/\partial u & \partial x/\partial v\\\partial y/\partial u & \partial y/\partial v\end{vmatrix}, \qquad \iint_R f(x,y)\,dA=\iint_S f\big(x(u,v),y(u,v)\big)\left|\frac{\partial(x,y)}{\partial(u,v)}\right|\,du\,dv.$$
The polar, cylindrical, and spherical formulas are special cases (the spherical Jacobian is $\rho^2\sin\phi$). The 3D version uses the analogous $3\times 3$ Jacobian determinant.

## Key Takeaways
- **Double integrals** are limits of Riemann sums giving volume/area; **Fubini's Theorem** evaluates them as **iterated integrals** in either order, over type I/II regions.
- **Coordinate changes** simplify integrals: polar ($dA=r\,dr\,d\theta$), cylindrical ($dV=r\,dz\,dr\,d\theta$), spherical ($dV=\rho^2\sin\phi\,d\rho\,d\theta\,d\phi$) — match the coordinate system to the region's symmetry.
- **Applications**: mass, center of mass, moments of inertia (with density $\rho$), surface area, and probability all become multiple integrals.
- The general **change of variables** scales by the **Jacobian** determinant $\left|\partial(x,y)/\partial(u,v)\right|$ — the unifying principle behind all the coordinate-change formulas.

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch14-partial-derivatives]] — previous chapter; partial derivatives appear in surface area and the Jacobian
- [[ch16-vector-calculus]] — next chapter; integrals over curves and surfaces
- [[ch10-parametric-and-polar]] — polar coordinates, used here for double integrals
- [[definite-integral]] · [[fundamental-theorem-of-calculus]] — the single-variable integral generalized here
- [[ch05-applications-of-integration]] — volumes, mass, and average value, now via multiple integrals
