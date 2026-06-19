---
title: "Stewart Calculus 9e — Ch.10: Parametric Equations and Polar Coordinates"
tags: [book, calculus, mathematics, parametric, polar, conic-sections, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 10 — Parametric Equations and Polar Coordinates

Chapter 10 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 699–760; PDF pp. 736–797). Introduces two new ways to describe curves that the function form $y=f(x)$ cannot — **parametric equations** (curves traced by a moving point) and **polar coordinates** (position by distance and angle) — then extends the tools of calculus (tangents, area, arc length) to each, closing with **conic sections** and their polar equations (the geometry of planetary orbits).

## 10.1 Curves Defined by Parametric Equations
A **parametric curve** is given by $x=f(t)$, $y=g(t)$, where the **parameter** $t$ (often time) traces out points $(x,y)$. This describes curves that fail the Vertical Line Test (loops, self-intersections) and carries direction/timing information. Examples: the **cycloid** (path of a point on a rolling circle), Lissajous figures, and trajectories where $t$ marks position at a given time.

## 10.2 Calculus with Parametric Curves
- **Tangents:** the slope is $\dfrac{dy}{dx}=\dfrac{dy/dt}{dx/dt}$ (where $dx/dt\ne 0$). The second derivative is $\dfrac{d^2y}{dx^2}=\dfrac{\frac{d}{dt}(dy/dx)}{dx/dt}$ (for concavity). Horizontal tangents where $dy/dt=0$; vertical where $dx/dt=0$.
- **Area** under a parametric curve: $A=\int y\,dx=\int_\alpha^\beta g(t)\,f'(t)\,dt$.
- **Arc length** (curve traversed once on $[\alpha,\beta]$): $L=\displaystyle\int_\alpha^\beta \sqrt{\left(\dfrac{dx}{dt}\right)^2+\left(\dfrac{dy}{dt}\right)^2}\,dt$.
- **Surface area** of revolution: $S=\int 2\pi y\,ds$ with $ds$ the parametric arc length differential.

## 10.3 Polar Coordinates
A point is located by $(r,\theta)$: distance $r$ from the **pole** (origin) and angle $\theta$ from the **polar axis**. Conversions: $x=r\cos\theta$, $y=r\sin\theta$, and $r^2=x^2+y^2$, $\tan\theta=y/x$. Polar representations are **not unique** — $(r,\theta)=(r,\theta+2\pi n)$, and negative $r$ points in the opposite direction. **Polar curves** $r=f(\theta)$ include circles, cardioids ($r=1+\sin\theta$), limaçons, and roses ($r=\cos 2\theta$). The slope of a polar curve uses $x=r\cos\theta$, $y=r\sin\theta$ as parametric equations in $\theta$.

## 10.4 Calculus in Polar Coordinates
- **Area** swept by $r=f(\theta)$ from $\theta=a$ to $b$ (built from circular sectors $\frac12 r^2\,d\theta$):
$$A = \int_a^b \tfrac12\,[f(\theta)]^2\,d\theta.$$
Areas between two polar curves subtract the inner from the outer; finding intersection points requires care because of non-unique representations (check the graph, not just simultaneous equations).
- **Arc length** of $r=f(\theta)$: $L=\displaystyle\int_a^b \sqrt{r^2+\left(\dfrac{dr}{d\theta}\right)^2}\,d\theta$.

## 10.5 Conic Sections
The curves formed by slicing a cone — defined by focus/directrix and distance conditions:
- **Parabola:** points equidistant from a **focus** and a **directrix**; standard form $x^2=4py$ (focus $(0,p)$).
- **Ellipse:** points whose distances to two **foci** sum to a constant $2a$; $\dfrac{x^2}{a^2}+\dfrac{y^2}{b^2}=1$.
- **Hyperbola:** points whose distances to two foci have constant *difference*; $\dfrac{x^2}{a^2}-\dfrac{y^2}{b^2}=1$.
These have reflection properties used in telescopes, headlights, and whispering galleries.

## 10.6 Conic Sections in Polar Coordinates
A unified **focus-directrix** definition: a conic is the set of points where the ratio of distance-to-focus to distance-to-directrix is a constant **eccentricity** $e$. Then $e<1$ → ellipse, $e=1$ → parabola, $e>1$ → hyperbola. With the focus at the pole and directrix $x=d$, the polar equation is
$$r = \frac{ed}{1+e\cos\theta}.$$
This is the natural form for **orbits**. **Kepler's Laws** (Johannes Kepler, 1609): (1) planets move in ellipses with the sun at one focus; (2) the radius vector sweeps equal areas in equal times; (3) the square of the orbital period is proportional to the cube of the semi-major axis. Newton later derived all three from his law of gravitation. The points of an orbit nearest/farthest from the focus are **perihelion** ($r=a(1-e)$) and **aphelion** ($r=a(1+e)$).

## Key Takeaways
- **Parametric equations** $x=f(t),y=g(t)$ trace curves a function can't (loops, self-intersections); calculus adapts via $\frac{dy}{dx}=\frac{dy/dt}{dx/dt}$ and $L=\int\sqrt{(dx/dt)^2+(dy/dt)^2}\,dt$.
- **Polar coordinates** $(r,\theta)$ describe position by distance and angle (conversions $x=r\cos\theta$, $y=r\sin\theta$); area is $\frac12\int r^2\,d\theta$, arc length $\int\sqrt{r^2+(dr/d\theta)^2}\,d\theta$. Representations are non-unique — graph before solving for intersections.
- **Conic sections** (parabola, ellipse, hyperbola) unify under one **eccentricity** $e$; in polar form $r=\frac{ed}{1+e\cos\theta}$, the natural language of orbits.
- **Kepler's Laws** describe planetary motion as ellipses with the sun at a focus — derivable from Newton's gravitation.

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch09-differential-equations]] — previous chapter
- [[ch11-sequences-series-power-series]] — next chapter
- [[ch08-further-applications-of-integration]] — arc length and surface area, here recast for parametric/polar curves
- [[johannes-kepler|Johannes Kepler]] — Kepler's Laws of planetary motion (§10.6)
- [[isaac-newton]] — derived Kepler's Laws from the law of gravitation
