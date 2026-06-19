---
title: "Stewart Calculus 9e — Ch.9: Differential Equations"
tags: [book, calculus, mathematics, differential-equations, modeling, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 9 — Differential Equations

Chapter 9 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 643–698; PDF pp. 680–735). A **differential equation** is an equation containing an unknown function and its derivatives. Because so many physical laws relate a quantity to its rate of change, differential equations are the language of mathematical modeling. This chapter introduces how they arise, how to picture and approximate solutions, and two solvable families (separable and first-order linear).

## 9.1 Modeling with Differential Equations
A model expresses a real-world rule as an equation in an unknown function and its derivatives; a **solution** is a function satisfying it (usually a whole **family** with arbitrary constants, narrowed by **initial conditions**).
- **Exponential growth:** $\dfrac{dP}{dt}=kP$, solutions $P(t)=Ce^{kt}$ — rate proportional to size (unlimited resources).
- **Logistic growth:** $\dfrac{dP}{dt}=kP\!\left(1-\dfrac{P}{M}\right)$ — incorporates **carrying capacity** $M$; growth slows as $P\to M$. Equilibrium solutions $P=0$ and $P=M$.
- **Spring (Hooke's Law):** restoring force $-kx$ gives $m\dfrac{d^2x}{dt^2}=-kx$, a second-order equation.

## 9.2 Direction Fields and Euler's Method
Most differential equations can't be solved by an explicit formula, so we study solutions graphically and numerically.
- **Direction (slope) field:** for $y'=F(x,y)$, draw a short segment of slope $F(x,y)$ at a grid of points; solution curves flow tangent to the field, revealing their shape without a formula.
- **Euler's method:** a numerical scheme that steps along the slope field. Starting from $(x_0,y_0)$ with step $h$: $y_{n+1}=y_n+h\,F(x_n,y_n)$, $x_{n+1}=x_n+h$. Smaller $h$ → more accurate (estimates approach the exact curve as $h\to 0$). Named for [[leonhard-euler|Leonhard Euler]].

## 9.3 Separable Equations
A **separable equation** can be written $\dfrac{dy}{dx}=g(x)\,f(y)$ — the right side factors into a function of $x$ times a function of $y$. Solve by separating variables and integrating both sides:
$$\int h(y)\,dy = \int g(x)\,dx, \qquad h(y)=\frac{1}{f(y)}.$$
This yields the solution implicitly (often solvable for $y$). Applications: orthogonal trajectories, mixing problems, Newton's Law of Cooling, electric circuits. (Technique traced to James Bernoulli, 1690, and Leibniz, 1694.)

## 9.4 Models for Population Growth
- The **natural growth** model $\dfrac{dP}{dt}=kP$ (separable) gives $P(t)=P_0 e^{kt}$ — the relative growth rate $\frac{dP/dt}{P}=k$ is constant.
- The **logistic differential equation** $\dfrac{dP}{dt}=kP\!\left(1-\dfrac{P}{M}\right)$ (proposed by Pierre-François Verhulst, 1840s) is separable; via [[ch07-techniques-of-integration|partial fractions]] it solves to the **logistic function**
$$P(t)=\frac{M}{1+Ae^{-kt}}, \qquad A=\frac{M-P_0}{P_0},$$
an S-shaped curve with $\lim_{t\to\infty}P(t)=M$. Below $M$ the population grows; above $M$ it declines toward $M$.

## 9.5 Linear Equations
A **first-order linear** equation has the form $\dfrac{dy}{dx}+P(x)\,y=Q(x)$. Solve by multiplying through by the **integrating factor**
$$I(x)=e^{\int P(x)\,dx},$$
which makes the left side an exact derivative $\dfrac{d}{dx}[I(x)\,y]$, so that $I(x)\,y=\int I(x)\,Q(x)\,dx$. Then divide by $I(x)$. Applications include electric circuits ($L\frac{dI}{dt}+RI=E(t)$).

## 9.6 Predator-Prey Systems
For two interacting species (prey $R$, predator $W$), a single equation isn't enough — we need a **system** of differential equations. The **Lotka-Volterra equations** (Volterra, 1860–1940):
$$\frac{dR}{dt}=kR-aRW, \qquad \frac{dW}{dt}=-rW+bRW,$$
with $k,r,a,b>0$: prey grow but are eaten ($-aRW$); predators die out but thrive on prey ($+bRW$). Explicit formulas are usually impossible, so we analyze solutions in the **phase plane** ($RW$-plane): equilibrium points (e.g. constant coexistence), and closed **phase trajectories** showing the populations cycle periodically.

## Key Takeaways
- A **differential equation** relates an unknown function to its derivatives; modeling translates physical laws (growth, springs, circuits, ecosystems) into them, with **initial conditions** selecting one solution from the family.
- When no formula exists, **direction fields** show solution shape and **Euler's method** approximates numerically ($y_{n+1}=y_n+hF(x_n,y_n)$).
- **Separable** equations ($\frac{dy}{dx}=g(x)f(y)$) solve by integrating both sides; **first-order linear** equations solve via the integrating factor $e^{\int P\,dx}$.
- Population models: exponential $P_0 e^{kt}$ (unlimited) vs **logistic** $\frac{M}{1+Ae^{-kt}}$ (carrying capacity $M$); **Lotka-Volterra** predator-prey systems cycle, studied via phase trajectories.

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch08-further-applications-of-integration]] — previous chapter
- [[ch10-parametric-and-polar]] — next chapter; parametric curves and polar coordinates
- [[ch07-techniques-of-integration]] — partial fractions solve the logistic equation; integration techniques solve separable/linear equations
- [[ch06-inverse-functions]] — exponential growth/decay ($\frac{dy}{dt}=ky$, $y=y_0 e^{kt}$) introduced there is the simplest differential equation
- [[leonhard-euler|Leonhard Euler]] — Euler's method (§9.2)
