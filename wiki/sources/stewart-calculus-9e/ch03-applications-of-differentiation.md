---
title: "Stewart Calculus 9e — Ch.3: Applications of Differentiation"
tags: [book, calculus, mathematics, optimization, curve-sketching, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 3 — Applications of Differentiation

Chapter 3 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 209–300; PDF pp. 246–337). Now that the differentiation rules of [[ch02-derivatives|Ch.2]] are in hand, this chapter puts derivatives to work: locating **maxima and minima**, determining the **shape of a graph**, solving **optimization** problems, and approximating roots and antiderivatives. The central theoretical fact underpinning most of it is the **Mean Value Theorem**.

## 3.1 Maximum and Minimum Values
- **Absolute (global) maximum/minimum:** $f(c)$ with $f(c)\ge f(x)$ (resp. $\le$) for all $x$ in the domain $D$. **Local (relative)** extrema require the inequality only for $x$ *near* $c$.
- **Extreme Value Theorem (Theorem 3):** if $f$ is continuous on a closed interval $[a,b]$, then $f$ attains an absolute max and an absolute min on $[a,b]$. (Both hypotheses — continuity and closed interval — are needed.)
- **Fermat's Theorem (Theorem 4):** if $f$ has a local max or min at $c$ and $f'(c)$ exists, then $f'(c)=0$. (Converse false — $f'(c)=0$ doesn't guarantee an extremum, e.g. $x^3$ at 0.)
- **Critical number:** a number $c$ in the domain where $f'(c)=0$ or $f'(c)$ does not exist. Local extrema occur only at critical numbers.
- **Closed Interval Method** for the absolute extrema of a continuous $f$ on $[a,b]$: evaluate $f$ at all critical numbers in $(a,b)$ and at the endpoints $a,b$; the largest value is the absolute max, the smallest the absolute min.

## 3.2 The Mean Value Theorem
- **Rolle's Theorem:** if $f$ is continuous on $[a,b]$, differentiable on $(a,b)$, and $f(a)=f(b)$, then there is a $c$ in $(a,b)$ with $f'(c)=0$.
- **Mean Value Theorem (MVT):** if $f$ is continuous on $[a,b]$ and differentiable on $(a,b)$, then there is a $c$ in $(a,b)$ with
$$f'(c) = \frac{f(b)-f(a)}{b-a}, \quad\text{equivalently}\quad f(b)-f(a) = f'(c)(b-a).$$
Geometrically: some tangent is parallel to the secant through the endpoints. (Proved from Rolle's via an auxiliary function.) Key consequence: **if $f'(x)=0$ throughout an interval, $f$ is constant there**; if $f'=g'$ then $f$ and $g$ differ by a constant. The MVT is the engine behind the tests below.

## 3.3 What Derivatives Tell Us About the Shape of a Graph
- **Increasing/Decreasing (I/D) Test:** $f'>0$ on an interval ⇒ $f$ increasing there; $f'<0$ ⇒ decreasing.
- **First Derivative Test:** at a critical number $c$, if $f'$ changes $+\to-$ then local max; $-\to+$ then local min; no sign change ⇒ neither.
- **Concavity Test:** $f''>0$ on $I$ ⇒ graph **concave upward** on $I$; $f''<0$ ⇒ **concave downward**. An **inflection point** is where concavity changes.
- **Second Derivative Test:** if $f'(c)=0$ and $f''(c)>0$ ⇒ local min at $c$; if $f''(c)<0$ ⇒ local max. (Inconclusive if $f''(c)=0$.)

## 3.4 Limits at Infinity; Horizontal Asymptotes
$\displaystyle\lim_{x\to\infty}f(x)=L$ means $f(x)$ can be made arbitrarily close to $L$ by taking $x$ large enough; the line $y=L$ is a **horizontal asymptote**. (Precise version: for every $\varepsilon>0$ there is $N$ with $|f(x)-L|<\varepsilon$ when $x>N$.) Computed by dividing numerator and denominator by the highest power of $x$, e.g. $\lim_{x\to\infty}\frac{3x^2-x-2}{5x^2+4x+1}=\frac35$. Infinite limits at infinity ($\lim_{x\to\infty}f(x)=\infty$) are also defined.

## 3.5 Summary of Curve Sketching
A checklist combining the chapter's tools to sketch $y=f(x)$: domain, intercepts, symmetry, asymptotes (horizontal/vertical, and **slant** asymptotes when $\deg(\text{num})=\deg(\text{den})+1$), intervals of increase/decrease (I/D Test), local extrema (First Derivative Test), concavity and inflection points (Concavity Test). (§3.6 covers graphing with calculus and technology together.)

## 3.7 Optimization Problems
Applying the extrema methods to "find the best outcome" problems (minimize cost/area/distance, maximize area/volume/revenue). General approach: introduce variables, write the quantity to optimize as a function of one variable using a constraint, find its absolute extremum (often via the Closed Interval Method or First Derivative Test for an interval). **Business/economics:** with cost $C(x)$, **marginal cost** is $C'(x)$; revenue $R(x)=x\,p(x)$ (demand/price function $p$), **marginal revenue** $R'(x)$; profit $P(x)=R(x)-C(x)$, **marginal profit** $P'(x)$. Maximize revenue/profit by setting the marginal function to zero.

## 3.8 Newton's Method
An iterative method (Newton–Raphson) to approximate a root of $f(x)=0$ when it can't be solved exactly. Starting from an initial guess $x_1$, follow the tangent line to its $x$-intercept to get a better estimate:
$$x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)} \quad (f'(x_n)\ne 0).$$
If the $x_n$ converge to $r$, then $\lim_{n\to\infty}x_n = r$. Convergence depends on a good starting point (it can fail, e.g. if $f'(x_n)=0$ or the iterates diverge).

## 3.9 Antiderivatives
A function $F$ is an **antiderivative** of $f$ on an interval $I$ if $F'(x)=f(x)$ for all $x$ in $I$. **Theorem 1:** if $F$ is one antiderivative of $f$, the most general antiderivative is $F(x)+C$ ($C$ an arbitrary constant) — a consequence of the MVT corollary (two functions with equal derivatives differ by a constant). Antidifferentiation formulas reverse the differentiation rules: e.g. an antiderivative of $x^n$ ($n\ne -1$) is $\frac{x^{n+1}}{n+1}$, of $\cos x$ is $\sin x$, of $\sec^2 x$ is $\tan x$. An **initial condition** (e.g. $f(1)=2$) pins down the constant $C$, giving a particular solution. This is the gateway to integration ([[ch04-integrals|Ch.4]]) and **differential equations**.

## Key Takeaways
- **Extrema** live at critical numbers (Fermat); the **Closed Interval Method** finds absolute extrema on $[a,b]$.
- The **Mean Value Theorem** is the load-bearing theorem: it yields the I/D, First-Derivative, and Concavity tests and the "constant if $f'=0$" corollary.
- The **first derivative** governs increase/decrease and local extrema; the **second derivative** governs concavity and inflection (and gives the Second Derivative Test).
- Practical payoffs: **optimization** (best outcome under a constraint), **Newton's Method** (root-finding), and **antiderivatives** (reversing differentiation, the bridge to integration).

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch02-derivatives]] — previous chapter; the differentiation rules applied here
- [[ch04-integrals]] — next chapter; antiderivatives lead into the definite integral and the FTC
- [[limit]] — limits at infinity / horizontal asymptotes
- [[intermediate-value-theorem]] · [[continuity]] — kin of the Extreme Value Theorem (continuity on a closed interval)
- [[mean-value-theorem]] · [[antiderivative]] — the MVT (§3.2) and antiderivatives (§3.9), promoted from this chapter
