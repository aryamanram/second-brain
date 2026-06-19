---
title: "Stewart Calculus 9e — Ch.7: Techniques of Integration"
tags: [book, calculus, mathematics, integration, techniques, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 7 — Techniques of Integration

Chapter 7 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 523–596; PDF pp. 560–633). Every [[definite-integral|definite integral]] reduces (via the [[fundamental-theorem-of-calculus|FTC]]) to finding an antiderivative, but antiderivatives can be hard. This chapter assembles a toolbox of techniques to transform integrands into forms we can integrate, then closes with two practical extensions: **numerical approximation** when no antiderivative exists in elementary form, and **improper integrals** over infinite intervals or with infinite integrands.

## 7.1 Integration by Parts
The integration analogue of the **Product Rule**. From $(uv)' = u'v + uv'$:
$$\int u\,dv = uv - \int v\,du.$$
Choose $u$ (to differentiate) and $dv$ (to integrate) so the new integral $\int v\,du$ is simpler. A useful heuristic (LIATE) prefers $u$ = Logarithmic, Inverse-trig, Algebraic, Trig, Exponential in that order. Works for $\int x e^x\,dx$, $\int \ln x\,dx$, $\int x^2\sin x\,dx$ (apply repeatedly), and "circular" cases like $\int e^x\sin x\,dx$ (solve algebraically for the original integral). Definite version: $\int_a^b u\,dv = \big[uv\big]_a^b - \int_a^b v\,du$.

## 7.2 Trigonometric Integrals
Systematic strategies for integrals of products of trig functions.
- $\int \sin^m x\cos^n x\,dx$: if a power is **odd**, peel off one factor and convert the rest using $\sin^2+\cos^2=1$, then substitute. If both are **even**, use the half-angle identities $\sin^2 x = \frac{1-\cos 2x}{2}$, $\cos^2 x = \frac{1+\cos 2x}{2}$.
- $\int \tan^m x\sec^n x\,dx$: use $\sec^2 x = 1+\tan^2 x$ and $\frac{d}{dx}\tan x=\sec^2x$, $\frac{d}{dx}\sec x=\sec x\tan x$.
- Products like $\int \sin A\cos B\,dx$ use the product-to-sum identities.

## 7.3 Trigonometric Substitution
For integrands containing $\sqrt{a^2-x^2}$, $\sqrt{a^2+x^2}$, or $\sqrt{x^2-a^2}$, substitute a trig function for $x$ to clear the radical (using the Pythagorean identities):

| Expression | Substitution | Identity used |
|---|---|---|
| $\sqrt{a^2-x^2}$ | $x=a\sin\theta$ | $1-\sin^2\theta=\cos^2\theta$ |
| $\sqrt{a^2+x^2}$ | $x=a\tan\theta$ | $1+\tan^2\theta=\sec^2\theta$ |
| $\sqrt{x^2-a^2}$ | $x=a\sec\theta$ | $\sec^2\theta-1=\tan^2\theta$ |

After integrating in $\theta$, convert back to $x$ using a reference right triangle. E.g. $\int x\sqrt{x^2+2x+4}\,dx$ is handled after completing the square to $(x+1)^2+3$.

## 7.4 Integration of Rational Functions by Partial Fractions
Any rational function $\frac{P(x)}{Q(x)}$ (with $\deg P < \deg Q$; otherwise long-divide first) can be written as a sum of simpler **partial fractions** that each integrate easily:
- Distinct linear factors $\frac{A}{x-a}$ → $\int = A\ln|x-a|$.
- Repeated linear factors $\frac{A}{(x-a)} + \frac{B}{(x-a)^2}+\cdots$.
- Irreducible quadratic factors $\frac{Ax+B}{x^2+bx+c}$ → logs and $\tan^{-1}$ terms.
Solve for the constants by clearing denominators and matching coefficients (or substituting convenient $x$-values). The **rationalizing substitution** extends this to some integrands with roots.

## 7.5 Strategy for Integration
Integration is more art than differentiation — there is no purely mechanical procedure. The recommended approach: (1) simplify the integrand algebraically; (2) look for an obvious **substitution** $u=g(x)$; (3) classify by form (trig, rational, radical, product) to pick a method; (4) try again — manipulate, combine techniques, or relate to an integral already solved. Key fact: **not every elementary function has an elementary antiderivative** (e.g. $\int e^{x^2}\,dx$, $\int \frac{e^x}{x}\,dx$, $\int \frac{\sin x}{x}\,dx$ cannot be expressed in closed form) — motivating §7.7.

## 7.6 Integration Using Tables and Computer Algebra Systems
Tables of integrals (Reference Pages 6–10) and **computer algebra systems** (CAS) extend reach, but require judgment: a CAS may return an answer in an unexpected form (constant of integration absent, or expressed via different but equivalent identities), so results must be checked and sometimes reconciled by hand (e.g. via trig identities or algebraic factoring). Often a table entry still needs a preliminary substitution to match the integrand's form.

## 7.7 Approximate Integration
When an antiderivative is unavailable (or $f$ is known only from data), approximate $\int_a^b f\,dx$ numerically. Partition $[a,b]$ into $n$ subintervals of width $\Delta x=\frac{b-a}{n}$.
- **Midpoint Rule:** $M_n = \Delta x\,[f(\bar x_1)+f(\bar x_2)+\cdots+f(\bar x_n)]$, where $\bar x_i$ is the midpoint of the $i$th subinterval.
- **Trapezoidal Rule:** $T_n = \frac{\Delta x}{2}\,[f(x_0)+2f(x_1)+2f(x_2)+\cdots+2f(x_{n-1})+f(x_n)]$ (averages left and right endpoint sums; approximates the curve by straight chords).
- **Simpson's Rule** (named for Thomas Simpson; $n$ must be **even**): approximates the curve by parabolas through consecutive triples of points:
$$S_n = \frac{\Delta x}{3}\,[f(x_0)+4f(x_1)+2f(x_2)+4f(x_3)+\cdots+2f(x_{n-2})+4f(x_{n-1})+f(x_n)].$$
It is the weighted average $S_{2n}=\tfrac13 T_n + \tfrac23 M_n$, and is far more accurate.

**Error bounds.** If $|f''(x)|\le K$ on $[a,b]$, the Trapezoidal and Midpoint errors satisfy
$$|E_T|\le \frac{K(b-a)^3}{12n^2}, \qquad |E_M|\le \frac{K(b-a)^3}{24n^2}.$$
If $|f^{(4)}(x)|\le K$ on $[a,b]$, Simpson's error satisfies
$$|E_S|\le \frac{K(b-a)^5}{180n^4}.$$
Errors shrink like $1/n^2$ (Trapezoidal/Midpoint) versus $1/n^4$ (Simpson) — doubling $n$ cuts Simpson's error by ~16×. These bounds let you pick $n$ to guarantee a target accuracy.

## 7.8 Improper Integrals
Extend the definite integral to **infinite intervals** (Type 1) and **discontinuous integrands** (Type 2) by taking a limit; the integral **converges** if the limit is a finite number, otherwise **diverges**.

**Type 1 (infinite interval):**
$$\int_a^\infty f(x)\,dx = \lim_{t\to\infty}\int_a^t f(x)\,dx, \qquad \int_{-\infty}^b f(x)\,dx = \lim_{t\to-\infty}\int_t^b f(x)\,dx,$$
and $\int_{-\infty}^\infty f = \int_{-\infty}^a f + \int_a^\infty f$ (converges only if **both** pieces do). Benchmark: $\int_1^\infty \frac{1}{x^p}\,dx$ **converges iff $p>1$** (e.g. $\int_1^\infty \frac{1}{x^2}\,dx=1$ converges; $\int_1^\infty \frac1x\,dx$ diverges). Also $\int_{-\infty}^\infty \frac{1}{1+x^2}\,dx=\pi$.

**Type 2 (discontinuous integrand):** if $f$ has an infinite discontinuity at an endpoint or interior point, define the integral as the limit approaching that point, e.g. $\int_a^b f = \lim_{t\to a^+}\int_t^b f$ when $f$ blows up at $a$. Benchmark: $\int_0^1 \frac{1}{x^p}\,dx$ converges iff $p<1$ (mirror of the Type-1 rule).

**Comparison Theorem:** if $f(x)\ge g(x)\ge 0$ for $x\ge a$, then:
- if $\int_a^\infty f$ **converges**, so does $\int_a^\infty g$ (smaller-than-convergent converges);
- if $\int_a^\infty g$ **diverges**, so does $\int_a^\infty f$ (bigger-than-divergent diverges).
This decides convergence without evaluating the integral (e.g. $\int_0^\infty e^{-x^2}\,dx$ converges by comparison with $e^{-x}$).

## Key Takeaways
- **Integration by parts** ($\int u\,dv = uv-\int v\,du$) reverses the Product Rule; **substitution** (Ch.4) reverses the Chain Rule — the two backbone techniques.
- **Trig integrals**, **trig substitution**, and **partial fractions** convert specific integrand forms into ones we can integrate; §7.5 stresses there is no mechanical algorithm — and that some elementary functions ($e^{x^2}$, $\frac{\sin x}{x}$) have **no elementary antiderivative**.
- **Approximate integration** (Midpoint, Trapezoidal, **Simpson's Rule**) handles integrals with no closed form or known only from data; error bounds ($1/n^2$ vs Simpson's $1/n^4$) let you guarantee accuracy.
- **Improper integrals** extend $\int$ to infinite intervals and infinite integrands via limits (convergent vs divergent); the $1/x^p$ benchmarks and the **Comparison Theorem** settle convergence.

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch06-inverse-functions]] — previous chapter; exp/log/inverse-trig functions appear throughout these techniques
- [[ch08-further-applications-of-integration]] — next chapter; applies these techniques (arc length, surface area, probability)
- [[ch04-integrals]] — the Substitution Rule (§4.5), the first integration technique
- [[definite-integral]] · [[fundamental-theorem-of-calculus]] — every technique serves the goal of evaluating these
