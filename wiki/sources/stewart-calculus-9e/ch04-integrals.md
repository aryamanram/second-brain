---
title: "Stewart Calculus 9e — Ch.4: Integrals"
tags: [book, calculus, mathematics, integration, fundamental-theorem, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 4 — Integrals

Chapter 4 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 301–362; PDF pp. 338–399). Introduces the **integral**, the second central idea of calculus, via the area problem. Its climax is the **Fundamental Theorem of Calculus**, which reveals that differentiation ([[ch02-derivatives|Ch.2]]) and integration are inverse processes — the connection previewed in [[ch00-preview]].

## 4.1 The Area and Distance Problems
The **area** $A$ under a continuous curve $y=f(x)$ from $a$ to $b$ is defined as a limit of sums of rectangle areas. Divide $[a,b]$ into $n$ strips of width $\Delta x = \frac{b-a}{n}$; the right-endpoint sum is $R_n = \sum_{i=1}^n f(x_i)\Delta x$ (left sum $L_n$ analogously). As $n\to\infty$ both converge to the same value:
$$A = \lim_{n\to\infty} R_n = \lim_{n\to\infty} L_n = \lim_{n\to\infty}\sum_{i=1}^n f(x_i^*)\Delta x,$$
where $x_i^*$ is any **sample point** in the $i$th subinterval. The same limit-of-sums idea computes **distance** from a velocity function.

## 4.2 The Definite Integral
**Definition:** if $f$ is defined on $[a,b]$, the **definite integral** of $f$ from $a$ to $b$ is
$$\int_a^b f(x)\,dx = \lim_{n\to\infty}\sum_{i=1}^n f(x_i^*)\Delta x,$$
provided the limit exists (then $f$ is **integrable**). The sum $\sum f(x_i^*)\Delta x$ is a **Riemann sum** (after Bernhard Riemann). The symbol $\int$ is an integral sign; $f(x)$ the integrand; $a,b$ the limits of integration; $dx$ indicates the variable. The integral is a number, independent of the variable's name.

- **Interpretation:** if $f\ge 0$, the integral is the area under the curve; if $f$ takes both signs, it is the **net area** $A_1 - A_2$ (area above the axis minus area below).
- **Theorem 3 (integrability):** if $f$ is continuous on $[a,b]$ (or has only finitely many jump discontinuities), it is integrable.
- **Properties:** $\int_a^a f=0$; $\int_b^a f = -\int_a^b f$; $\int_a^b c\,dx = c(b-a)$; linearity $\int(f\pm g)=\int f \pm \int g$ and $\int cf = c\int f$; and the **additivity** $\int_a^c f + \int_c^b f = \int_a^b f$.

## 4.3 The Fundamental Theorem of Calculus (FTC)
The bridge between the two branches of calculus (established by Newton, Leibniz, and Newton's mentor Isaac Barrow).

**FTC Part 1:** if $f$ is continuous on $[a,b]$, then $g(x)=\displaystyle\int_a^x f(t)\,dt$ is continuous on $[a,b]$, differentiable on $(a,b)$, and
$$g'(x) = f(x), \quad\text{i.e.}\quad \frac{d}{dx}\int_a^x f(t)\,dt = f(x).$$
(Differentiating an integral with variable upper limit returns the integrand. With the Chain Rule it handles variable limits like $\frac{d}{dx}\int_1^{x^4}\sec t\,dt$.)

**FTC Part 2:** if $f$ is continuous on $[a,b]$ and $F$ is **any antiderivative** of $f$ (so $F'=f$), then
$$\int_a^b f(x)\,dx = F(b) - F(a) = \big[F(x)\big]_a^b.$$
This is what makes integrals computable: find an antiderivative, evaluate at the endpoints, subtract. (Caution: it requires $f$ continuous on $[a,b]$ — e.g. $\int_{-1}^{3}\frac{1}{x^2}dx$ is **not** $-\frac43$ because $1/x^2$ is discontinuous at 0.)

## 4.4 Indefinite Integrals and the Net Change Theorem
The **indefinite integral** $\int f(x)\,dx = F(x)+C$ denotes the *family* of all antiderivatives of $f$ (a function, distinct from the *number* $\int_a^b f\,dx$). A **Table of Indefinite Integrals** reverses the differentiation rules:
$$\int x^n\,dx = \frac{x^{n+1}}{n+1}+C\ (n\ne -1), \quad \int \cos x\,dx = \sin x + C, \quad \int \sec^2 x\,dx = \tan x + C, \ \dots$$
**Net Change Theorem:** $\displaystyle\int_a^b F'(x)\,dx = F(b)-F(a)$ — the integral of a rate of change is the net change in the quantity. Applications: $\int_{t_1}^{t_2} V'(t)\,dt$ = net change in volume, $\int_{t_1}^{t_2} v(t)\,dt$ = displacement, etc.

## 4.5 The Substitution Rule
The integration analogue of the Chain Rule. **Indefinite form:** if $u=g(x)$ is differentiable and $f$ continuous,
$$\int f(g(x))\,g'(x)\,dx = \int f(u)\,du.$$
Choose $u$ so that its differential $du=g'(x)\,dx$ appears in the integrand; then "operate with $dx$ and $du$ after integral signs as though they were differentials." E.g. $\int 2x\sqrt{1+x^2}\,dx$ with $u=1+x^2$ gives $\frac23(1+x^2)^{3/2}+C$.

**Definite form (Theorem 5):** change the limits to match $u$:
$$\int_a^b f(g(x))\,g'(x)\,dx = \int_{g(a)}^{g(b)} f(u)\,du.$$
The section closes with using substitution to exploit **symmetry** (even/odd integrands over symmetric intervals).

## Key Takeaways
- The **definite integral** is a limit of Riemann sums; geometrically it's (net) area under a curve.
- The **Fundamental Theorem of Calculus** unifies the subject: Part 1 says differentiating an integral recovers the integrand; Part 2 says a definite integral equals the change in any antiderivative, $F(b)-F(a)$ — making integration practical.
- The **indefinite integral** is the antiderivative family $F(x)+C$; the **Net Change Theorem** reads the integral of a rate as a total change.
- The **Substitution Rule** reverses the Chain Rule and is the first systematic integration technique (more in [[ch07-techniques-of-integration|Ch.7]]).

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch03-applications-of-differentiation]] — previous chapter; antiderivatives (§3.9) feed directly into integration
- [[ch05-applications-of-integration]] — next chapter; integrals for areas between curves, volumes, averages
- [[ch00-preview]] — the area problem and the FTC connection, previewed
- [[definite-integral]] · [[fundamental-theorem-of-calculus]] · [[riemann-sum]] — concept pages promoted from this chapter
- [[limit]] · [[continuity]] — the integral is a limit; the FTC requires continuity
- [[isaac-newton]] · [[gottfried-leibniz]] — established the FTC
