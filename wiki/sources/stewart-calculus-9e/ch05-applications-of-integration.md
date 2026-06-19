---
title: "Stewart Calculus 9e — Ch.5: Applications of Integration"
tags: [book, calculus, mathematics, integration, volumes, work, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 5 — Applications of Integration

Chapter 5 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 363–410; PDF pp. 400–447). Applies the [[definite-integral]] of [[ch04-integrals|Ch.4]] to geometric and physical quantities. The recurring method: break a quantity $Q$ into many small pieces, approximate each by $f(x_i^*)\Delta x$, form a Riemann sum, take the limit (an integral), and evaluate via the [[fundamental-theorem-of-calculus|FTC]].

## 5.1 Areas Between Curves
The area between $y=f(x)$ (top) and $y=g(x)$ (bottom) over $[a,b]$, with $f(x)\ge g(x)$:
$$A = \int_a^b [f(x)-g(x)]\,dx.$$
If the curves cross, split the interval at the intersection points (integrate $|f-g|$). For regions better described by horizontal slices, integrate with respect to $y$: $A=\int_c^d [x_{\text{right}}-x_{\text{left}}]\,dy$.

## 5.2 Volumes
For a solid with known **cross-sectional area** $A(x)$ perpendicular to the $x$-axis:
$$V = \int_a^b A(x)\,dx.$$
- **Disk method** (solid of revolution about an axis, no gap): $A=\pi[R(x)]^2$, so $V=\int_a^b \pi[R(x)]^2\,dx$.
- **Washer method** (revolution with a hole): $A=\pi([R_{\text{outer}}]^2-[r_{\text{inner}}]^2)$.

## 5.3 Volumes by Cylindrical Shells
An alternative for solids of revolution, integrating along the axis *parallel* to the axis of rotation. A thin shell at radius $x$, height $f(x)$, thickness $dx$ has volume $2\pi x\,f(x)\,dx$, so
$$V = \int_a^b 2\pi x\,f(x)\,dx.$$
Choose shells vs. disks/washers based on which avoids splitting the region or solving for the inverse function (whether the boundary is easier as $y=f(x)$ or $x=g(y)$).

## 5.4 Work
**Work** done by a constant force is $W=Fd$; for a **variable force** $f(x)$ along $[a,b]$:
$$W = \int_a^b f(x)\,dx.$$
- **Hooke's Law:** the force to stretch a spring $x$ beyond natural length is $f(x)=kx$ ($k$ = spring constant), so work $=\int kx\,dx$.
- Problems like lifting a hanging cable or pumping water out of a tank are set up by slicing the load into layers, computing the work $F_i\,d_i$ on each (force × distance), and integrating.

## 5.5 Average Value of a Function
The **average value** of $f$ on $[a,b]$:
$$f_{\text{ave}} = \frac{1}{b-a}\int_a^b f(x)\,dx.$$
**Mean Value Theorem for Integrals:** if $f$ is continuous on $[a,b]$, there exists $c$ in $[a,b]$ with
$$f(c) = f_{\text{ave}}, \quad\text{i.e.}\quad \int_a^b f(x)\,dx = f(c)(b-a).$$
Geometrically, a rectangle of height $f(c)$ over $[a,b]$ has the same area as the region under $f$. It follows from the Mean Value Theorem ([[ch03-applications-of-differentiation|§3.2]]) applied to $F(x)=\int_a^x f$.

## Key Takeaways
- One template — slice, approximate by $f(x_i^*)\Delta x$, sum, take the limit to an integral — yields **area between curves, volume, work, and average value**.
- **Volumes of revolution:** disks/washers (slices ⟂ to the axis) vs. cylindrical shells (slices ∥ to the axis); pick whichever matches the boundary description.
- **Work** generalizes $Fd$ to $\int f(x)\,dx$ for a variable force (Hooke's Law, lifting, pumping).
- The **average value** $\frac{1}{b-a}\int_a^b f$ and its Mean Value Theorem for Integrals connect integrals back to function values.

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch04-integrals]] — previous chapter; the definite integral and FTC applied here
- [[ch06-inverse-functions]] — next chapter; exponential, logarithmic, and inverse trig functions
- [[definite-integral]] · [[fundamental-theorem-of-calculus]] — the tools every application here relies on
