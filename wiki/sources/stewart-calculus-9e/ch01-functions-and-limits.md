---
title: "Stewart Calculus 9e — Ch.1: Functions and Limits"
tags: [book, calculus, mathematics, functions, limits, continuity, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 1 — Functions and Limits

Chapter 1 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 7–95; PDF pp. 44–143). Establishes the two foundational objects of calculus — **functions** and **limits** — and ends with **continuity** and the **Intermediate Value Theorem**. Limits underlie every later branch (derivatives, integrals, series), so this chapter is the bedrock of the book.

## 1.1 Four Ways to Represent a Function
A **function** $f$ assigns to each element $x$ in a set $D$ (the **domain**) exactly one element $f(x)$ in a set $E$. The set of attained values $\{f(x) \mid x \in D\}$ is the **range**; $x$ is the **independent variable**, $y = f(x)$ the **dependent variable**.

Four representations: **verbally** (description), **numerically** (table), **visually** (graph), **algebraically** (formula). Examples span all four — area of a circle $A = \pi r^2$ (formula), world population $P(t)$ (table), cost of mailing $C(w)$ (table/step), seismic acceleration $a(t)$ (graph).

- **Vertical Line Test** (Figure 13): a curve in the $xy$-plane is the graph of a function of $x$ iff no vertical line meets it more than once.
- **Difference quotient** $\dfrac{f(a+h)-f(a)}{h}$ is introduced (Example 3) — it recurs constantly in Ch. 2.
- **Piecewise functions** (e.g. the absolute value $|x| = x$ if $x\ge 0$, $-x$ if $x<0$), **even** ($f(-x)=f(x)$, symmetric about the $y$-axis) and **odd** ($f(-x)=-f(x)$, symmetric about the origin) functions, and **increasing/decreasing** functions are all defined here.
- *Figures (described):* machine and arrow diagrams for $f$; graphs illustrating domain/range, the parabola $x = y^2$ failing the vertical line test, and even/odd symmetry.

## 1.2 Mathematical Models: A Catalog of Essential Functions
A **mathematical model** describes a real phenomenon via a function. The **modeling process** (Figure 1, described): real-world problem → *formulate* → mathematical model → *solve* → mathematical conclusions → *interpret* → real-world predictions → *test* → loop. A model is an idealization; a good one is accurate enough to be useful.

Catalog of **essential functions** (summarized in Table 3 with graphs):
- **Linear:** $f(x)=mx+b$; constant rate of change $m$ (slope).
- **Polynomials:** $P(x)=a_n x^n + \dots + a_1 x + a_0$, degree $n$, leading coefficient $a_n$; degree 1 = linear, 2 = quadratic (parabola), 3 = cubic.
- **Power functions:** $f(x)=x^a$. For $a=n$ (positive integer), $a=1/n$ (**root functions** $\sqrt[n]{x}$), $a=-1$ (**reciprocal** $1/x$, a hyperbola — Boyle's Law $V=C/P$), $a=-2$ (**inverse square** — gravitation, illumination $I=C/x^2$).
- **Rational functions:** ratio of polynomials $P(x)/Q(x)$.
- **Algebraic functions:** built from polynomials by $+,-,\times,\div$ and roots.
- **Trigonometric:** $\sin x$, $\cos x$ (period $2\pi$, $-1\le\sin x\le 1$), $\tan x = \sin x/\cos x$ (period $\pi$). **Radian measure always.**
- **Exponential:** $f(x)=b^x$, $b>0$. **Logarithmic:** $f(x)=\log_b x$, inverse of exponential.
- **Transcendental** = non-algebraic (trig, exponential, log).

**Linear regression** / **least squares** introduced via a CO₂-vs-time dataset (Mauna Loa); distinguishes **interpolation** (estimating within the data) from **extrapolation** (predicting outside it, riskier). A falling ball (dropped from the CN Tower, ≈450 m) is modeled by a quadratic $h = 449.36 + 0.96t - 4.90t^2$.

## 1.3 New Functions from Old Functions
**Transformations** of $y=f(x)$ (with $c>0$):
- **Shifts:** $f(x)+c$ up, $f(x)-c$ down, $f(x-c)$ right, $f(x+c)$ left.
- **Stretch/shrink:** $cf(x)$ vertical stretch by $c$; $f(cx)$ horizontal shrink by $c$.
- **Reflections:** $-f(x)$ about the $x$-axis; $f(-x)$ about the $y$-axis.

**Combinations:** $(f+g)$, $(f-g)$, $(fg)$, $(f/g)$ with domains given by intersections (and $g\ne 0$ for the quotient).

**Composition:** $(f\circ g)(x) = f(g(x))$; domain = all $x$ in domain of $g$ such that $g(x)$ is in domain of $f$. *Figure (described):* the $f\circ g$ "machine" feeding $g$'s output into $f$.

## 1.4 The Tangent and Velocity Problems
Motivates limits concretely. **Tangent** (Latin *tangens*, "touching"): the tangent to $y=x^2$ at $P(1,1)$ is the limiting position of **secant lines** $PQ$ as $Q\to P$. The secant slope $m_{PQ}=\dfrac{x^2-1}{x-1}$ approaches $2$, so the tangent slope is
$$m = \lim_{Q\to P} m_{PQ} = \lim_{x\to 1}\frac{x^2-1}{x-1} = 2.$$
**Velocity:** average velocity over $[5, 5+h]$ for a ball dropped from the CN Tower ($s(t)=4.9t^2$) approaches the **instantaneous velocity** $49\text{ m/s}$ at $t=5$ as the interval shrinks. Tangent and velocity are the same limit idea — pursued rigorously next.

## 1.5 The Limit of a Function
**Intuitive definition:** $\displaystyle\lim_{x\to a} f(x) = L$ means $f(x)$ can be made arbitrarily close to $L$ by taking $x$ sufficiently close to $a$ (but $x\ne a$). The value (or existence) of $f(a)$ is irrelevant.

- Warned that **tables/graphs can mislead** (Examples 3 & 5: $\sin(\pi/x)$ oscillates and $\lim_{x\to 0}\sin(\pi/x)$ does not exist; naive tables can suggest a wrong limit). Numerical guessing has pitfalls.
- **One-sided limits:** left-hand $\lim_{x\to a^-}f(x)=L$ and right-hand $\lim_{x\to a^+}f(x)=L$. The Heaviside function $H(t)$ ($0$ for $t<0$, $1$ for $t\ge 0$) has $\lim_{t\to 0^-}H=0$, $\lim_{t\to 0^+}H=1$.
- **Theorem (3):** $\displaystyle\lim_{x\to a}f(x)=L \iff \lim_{x\to a^-}f(x)=L=\lim_{x\to a^+}f(x)$.
- **Infinite limits / vertical asymptotes:** $\lim_{x\to a}f(x)=\infty$ means $f(x)$ grows without bound; e.g. $\lim_{x\to 0}1/x^2=\infty$. The line $x=a$ is a **vertical asymptote** if any one-sided limit there is $\pm\infty$ (e.g. $\tan x$ at $x=\pi/2+n\pi$).

## 1.6 Calculating Limits Using the Limit Laws
**Limit Laws** (for constant $c$, assuming the limits exist):
1. Sum: $\lim(f+g)=\lim f+\lim g$
2. Difference: $\lim(f-g)=\lim f-\lim g$
3. Constant Multiple: $\lim(cf)=c\lim f$
4. Product: $\lim(fg)=\lim f\cdot\lim g$
5. Quotient: $\lim(f/g)=\dfrac{\lim f}{\lim g}$ (if $\lim g\ne 0$)
6. Power: $\lim[f(x)]^n=[\lim f]^n$; 7. Root: $\lim\sqrt[n]{f}=\sqrt[n]{\lim f}$.
Special limits: $\lim_{x\to a}c=c$, $\lim_{x\to a}x=a$, $\lim_{x\to a}x^n=a^n$, $\lim_{x\to a}\sqrt[n]{x}=\sqrt[n]{a}$.

**Direct Substitution Property:** if $f$ is a polynomial or rational function and $a$ is in its domain, $\lim_{x\to a}f(x)=f(a)$. When substitution gives $0/0$, use algebra first (factor / rationalize) — e.g. $\lim_{x\to 1}\dfrac{x^2-1}{x-1}=\lim_{x\to 1}(x+1)=2$, and $\lim_{x\to 0}\dfrac{\sqrt{t^2+9}-3}{t^2}=\frac16$ by rationalizing.

Also: if $f(x)=g(x)$ for $x\ne a$, their limits at $a$ agree. One-sided Limit Laws (Theorem 1) let you compute $\lim|x|/x$-type limits.

**Squeeze Theorem (Theorem 3):** if $f(x)\le g(x)\le h(x)$ near $a$ and $\lim_{x\to a}f(x)=\lim_{x\to a}h(x)=L$, then $\lim_{x\to a}g(x)=L$. Used to show $\lim_{x\to 0}x^2\sin(1/x)=0$ via $-x^2\le x^2\sin(1/x)\le x^2$.

## 1.7 The Precise Definition of a Limit (ε–δ)
The intuitive language ("close to") is made rigorous:
$$\lim_{x\to a}f(x)=L \;\text{ means: for every } \varepsilon>0 \text{ there is } \delta>0 \text{ such that if } 0<|x-a|<\delta \text{ then } |f(x)-L|<\varepsilon.$$
$\varepsilon$ is the **error tolerance** on $f(x)$; $\delta$ is how close $x$ must be to $a$. *Figures (described):* the band $L-\varepsilon < y < L+\varepsilon$ forcing an interval $a-\delta < x < a+\delta$; a smaller $\varepsilon$ demands a smaller $\delta$. Precise versions are also given for one-sided limits and infinite limits ($f(x)>N$, $f(x)<N$).

## 1.8 Continuity
**Definition 1:** $f$ is **continuous at $a$** if $\displaystyle\lim_{x\to a}f(x)=f(a)$. This requires three things: (1) $f(a)$ is defined, (2) $\lim_{x\to a}f(x)$ exists, (3) the two are equal. Geometrically, the graph has no break at $a$ — drawable without lifting the pen.

**Types of discontinuity** (Figure 3, described): **removable** (a hole, fixable by redefining one value), **jump** (left/right limits differ — e.g. Heaviside), **infinite** (e.g. $1/x^2$ at 0).

- **Continuity from the right/left** (Definition 2); **continuous on an interval** (Definition 3).
- **Theorem 4:** if $f,g$ continuous at $a$, so are $f+g$, $f-g$, $cf$, $fg$, and $f/g$ (if $g(a)\ne 0$).
- **Theorem 5:** polynomials are continuous on $\mathbb{R}$; rational functions are continuous on their domains.
- **Theorem 7:** polynomials, rational, root, and trigonometric functions are continuous on their domains.
- **Theorem 8:** $\lim_{x\to a}f(g(x))=f\big(\lim_{x\to a}g(x)\big)$ for $f$ continuous (the limit symbol moves inside a continuous function).
- **Theorem 9:** a composition of continuous functions is continuous.

**Intermediate Value Theorem (Theorem 10):** if $f$ is continuous on $[a,b]$ and $N$ is any value between $f(a)$ and $f(b)$ (with $f(a)\ne f(b)$), then there is a $c$ in $(a,b)$ with $f(c)=N$. A continuous function takes every intermediate value — the basis for locating roots (sign-change ⇒ a zero exists in between). Continuity is required (Figure 8, described: a jump can skip the value $N$).

## Key Takeaways
- A function maps each input to exactly one output; four representations (verbal/numerical/visual/algebraic) and the vertical-line test.
- The **limit** is the central new idea, motivated by the tangent and velocity problems, made computable by the **Limit Laws** + Direct Substitution + algebra, and made rigorous by the **ε–δ definition**.
- **Continuity** = "limit equals function value"; closed under arithmetic and composition; polynomials/rationals/roots/trig are continuous on their domains.
- The **Squeeze Theorem** and **Intermediate Value Theorem** are the chapter's two workhorse theorems.

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch00-preview]] — previous chapter; the tangent and area problems that motivate limits
- [[ch02-derivatives]] — next chapter; the difference quotient and tangent-slope limit become the derivative
- [[limit]] · [[continuity]] · [[intermediate-value-theorem]] · [[squeeze-theorem]] — concept pages promoted from this chapter
