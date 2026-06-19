---
title: "Stewart Calculus 9e — Ch.8: Further Applications of Integration"
tags: [book, calculus, mathematics, integration, arc-length, probability, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 8 — Further Applications of Integration

Chapter 8 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 597–642; PDF pp. 634–679). Continues the "slice, approximate, sum, take the limit" method of [[ch05-applications-of-integration|Ch.5]] into geometry (arc length, surface area), physics/engineering (hydrostatic force, centers of mass), economics/biology, and probability. Several integrals here require the techniques of [[ch07-techniques-of-integration|Ch.7]] (trig substitution, integration by parts, improper integrals).

## 8.1 Arc Length
The **length** of a curve is defined as the limit of the lengths of inscribed polygonal paths. For $y=f(x)$ on $[a,b]$ with $f'$ continuous (a **smooth** curve), the Mean Value Theorem on each subinterval gives $|P_{i-1}P_i|=\sqrt{1+[f'(x_i^*)]^2}\,\Delta x$, and the limit is the **Arc Length Formula:**
$$L = \int_a^b \sqrt{1+[f'(x)]^2}\,dx = \int_a^b \sqrt{1+\left(\frac{dy}{dx}\right)^2}\,dx.$$
For a curve given as $x=g(y)$ on $[c,d]$, $L=\int_c^d \sqrt{1+(dx/dy)^2}\,dy$. The **arc length function** $s(x)=\int_a^x \sqrt{1+[f'(t)]^2}\,dt$ measures length from a starting point; $ds=\sqrt{1+(dy/dx)^2}\,dx$ is the arc length differential. Many arc-length integrals are hard and need numerical methods (§7.7).

## 8.2 Area of a Surface of Revolution
Rotating a smooth curve about an axis generates a surface whose area is found by slicing into thin frustum bands of slant width $ds$ and circumference $2\pi(\text{radius})$. **About the $x$-axis:**
$$S = \int 2\pi y\,ds = \int_a^b 2\pi f(x)\sqrt{1+[f'(x)]^2}\,dx.$$
**About the $y$-axis:** $S=\int 2\pi x\,ds$. In both, the radius is the distance from the axis to the curve, and $ds$ is the arc length differential of §8.1. (Gabriel's horn $y=1/x$ has finite volume but infinite surface area.)

## 8.3 Applications to Physics and Engineering
**Hydrostatic pressure and force.** At depth $d$ in a fluid of mass density $\rho$ (weight density $\delta=\rho g$), the pressure is the same in all directions: $P=\rho g d=\delta d$. The **force** on a vertical submerged plate is found by slicing it horizontally — each strip at depth is approximately at uniform pressure, so $F_i\approx P_i\cdot A_i$ — and integrating $F=\int \delta\,d\,w(d)\,dd$ over the depth range.

**Moments and center of mass.** The **moment** of a system about an axis measures its tendency to rotate. For point masses $m_i$ at $x_i$ on a line, the center of mass is $\bar x=\frac{\sum m_i x_i}{\sum m_i}=\frac{M}{m}$ (the Law of the Lever). In the plane, moments about the axes are $M_y=\sum m_i x_i$ and $M_x=\sum m_i y_i$, with center of mass $\bar x=M_y/m$, $\bar y=M_x/m$. For a flat plate (lamina) of constant density bounded by $y=f(x)$, the **centroid** is
$$\bar x = \frac{1}{A}\int_a^b x\,f(x)\,dx, \qquad \bar y = \frac{1}{A}\int_a^b \tfrac12[f(x)]^2\,dx,$$
where $A$ is the area. (Symmetry: the centroid lies on any axis of symmetry.)

## 8.4 Applications to Economics and Biology
- **Consumer surplus:** if $p(x)$ is the demand function and the market price is $P$ (at sales level $X$), the consumer surplus $\int_0^X [p(x)-P]\,dx$ measures total savings to consumers willing to pay more than $P$. **Producer surplus** is the analogous $\int_0^X [P-p_S(x)]\,dx$.
- **Blood flow:** integrating the laminar-flow velocity profile $v(r)=\frac{P}{4\eta l}(R^2-r^2)$ over the cross-section gives **Poiseuille's Law** for the flux (discharge), $F=\frac{\pi P R^4}{8\eta l}$ — flux scales with the **fourth power** of vessel radius.
- **Cardiac output:** the dye dilution method computes blood flow through the heart by integrating measured dye concentration.

## 8.5 Probability
A **continuous random variable** $X$ is described by a **probability density function** $f$ with $f(x)\ge 0$ and $\int_{-\infty}^\infty f(x)\,dx=1$; then
$$P(a\le X\le b)=\int_a^b f(x)\,dx.$$
- **Mean (expected value):** $\mu = \int_{-\infty}^\infty x\,f(x)\,dx$ — the centroid (balance point) of the density.
- **Exponential density** $f(t)=\begin{cases}0 & t<0\\ ce^{-ct} & t\ge 0\end{cases}$ models waiting times / failure times; its mean is $\mu=1/c$ (evaluated via integration by parts and an improper integral).
- **Normal distribution:** $f(x)=\dfrac{1}{\sigma\sqrt{2\pi}}\,e^{-(x-\mu)^2/(2\sigma^2)}$, the bell curve with mean $\mu$ and **standard deviation** $\sigma$ (controls spread). Because $e^{-x^2}$ has no elementary antiderivative, normal probabilities are evaluated numerically (§7.7) — e.g. ~68% of values lie within one $\sigma$ of the mean.

## Key Takeaways
- **Arc length** $L=\int\sqrt{1+(dy/dx)^2}\,dx$ and **surface area** $S=\int 2\pi(\text{radius})\,ds$ both build on the arc length differential $ds$.
- **Hydrostatic force** ($P=\delta d$, integrate pressure × strip area by depth) and **centers of mass / centroids** ($\bar x=\frac1A\int x f$, $\bar y=\frac1A\int\frac12 f^2$) apply integration to physics and engineering.
- **Economics**: consumer/producer surplus as integrals; **biology**: Poiseuille's Law ($F\propto R^4$) and cardiac output.
- **Probability**: density functions integrate to 1; mean $=\int x f(x)\,dx$; the **exponential** (mean $1/c$) and **normal** (bell curve, evaluated numerically) distributions are the key examples — tying together improper integrals (§7.8) and numerical integration (§7.7).

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch07-techniques-of-integration]] — previous chapter; trig substitution, parts, and improper integrals are used throughout
- [[ch09-differential-equations]] — next chapter; modeling with rates of change
- [[ch05-applications-of-integration]] — the slice-and-integrate template (area, volume, work, average value) extended here
- [[definite-integral]] · [[fundamental-theorem-of-calculus]] — the tools every application relies on
