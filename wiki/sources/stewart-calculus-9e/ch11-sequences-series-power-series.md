---
title: "Stewart Calculus 9e — Ch.11: Sequences, Series, and Power Series"
tags: [book, calculus, mathematics, series, sequences, taylor-series, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 11 — Sequences, Series, and Power Series

Chapter 11 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 761–866; PDF pp. 798–903). Develops **infinite series** — adding infinitely many terms — and the convergence tests that decide when such a sum is finite. The payoff is **power series**, which represent functions as "infinite polynomials"; in particular **Taylor/Maclaurin series** express functions like $e^x$, $\sin x$, $\cos x$ as power series, enabling computation, integration of otherwise-intractable functions, and approximation.

## 11.1 Sequences
A **sequence** $\{a_n\}$ is an ordered list of numbers, a function on the positive integers. It **converges** to $L$ if $\lim_{n\to\infty}a_n=L$, otherwise it diverges. Limit Laws and the **Squeeze Theorem** apply; a continuous function passes through limits ($\lim f(a_n)=f(\lim a_n)$). The **Monotonic Sequence Theorem:** every bounded monotonic sequence converges. (E.g. the Fibonacci sequence is defined recursively $f_n=f_{n-1}+f_{n-2}$.)

## 11.2 Series
A **series** $\sum a_n$ is the sum of a sequence; it **converges** to $s$ if its sequence of **partial sums** $s_n=a_1+\cdots+a_n$ converges to $s$.
- **Geometric series** $\sum_{n=1}^\infty ar^{n-1}=\dfrac{a}{1-r}$ **converges iff $|r|<1$** (diverges otherwise). Equivalently $\sum_{n=0}^\infty x^n=\dfrac{1}{1-x}$ for $|x|<1$.
- **Test for Divergence:** if $\lim_{n\to\infty}a_n\ne 0$ (or doesn't exist), $\sum a_n$ diverges. (Converse false: the **harmonic series** $\sum \frac1n$ diverges even though $a_n\to 0$.)
- Convergent series add/subtract/scale termwise.

## 11.3 The Integral Test and Estimates of Sums
**Integral Test:** if $f$ is continuous, positive, and (ultimately) decreasing with $a_n=f(n)$, then $\sum a_n$ converges **iff** the improper integral $\int_1^\infty f(x)\,dx$ converges. Consequence — the **$p$-series** $\sum \dfrac{1}{n^p}$ converges **iff $p>1$** (the harmonic series is $p=1$, divergent). The integral also gives remainder estimates bounding the error in a partial sum. (The Riemann zeta function $\zeta(s)=\sum 1/n^s$ is defined here.)

## 11.4 The Comparison Tests
For positive-term series:
- **Direct Comparison Test:** if $0\le a_n\le b_n$ and $\sum b_n$ converges, so does $\sum a_n$; if $\sum b_n$ diverges and $a_n\ge b_n$, so does $\sum a_n$.
- **Limit Comparison Test:** if $\lim_{n\to\infty}\dfrac{a_n}{b_n}=c$ with $0<c<\infty$, then $\sum a_n$ and $\sum b_n$ both converge or both diverge. (Compare against a geometric or $p$-series whose behavior is known.)

## 11.5 Alternating Series and Absolute Convergence
- **Alternating Series Test:** $\sum (-1)^{n-1}b_n$ ($b_n>0$) converges if $b_{n+1}\le b_n$ and $\lim b_n=0$. The **Alternating Series Estimation Theorem** bounds the error by the first omitted term: $|R_n|\le b_{n+1}$.
- **Absolute convergence:** $\sum a_n$ is **absolutely convergent** if $\sum|a_n|$ converges — and **absolute convergence implies convergence**. If $\sum a_n$ converges but $\sum |a_n|$ diverges, it is **conditionally convergent** (e.g. the alternating harmonic series $\sum \frac{(-1)^{n-1}}{n}$).

## 11.6 The Ratio and Root Tests
- **Ratio Test:** let $L=\lim_{n\to\infty}\left|\dfrac{a_{n+1}}{a_n}\right|$. If $L<1$, $\sum a_n$ converges absolutely; if $L>1$ (or $\infty$), it diverges; if $L=1$, inconclusive. (Best for factorials and exponentials.)
- **Root Test:** let $L=\lim_{n\to\infty}\sqrt[n]{|a_n|}$; same conclusions. (Best when $a_n$ involves $n$th powers.)

## 11.7 Strategy for Testing Series
No single test works for all series; choose by form — Test for Divergence first; geometric/$p$-series by inspection; Comparison for rational/algebraic terms; Ratio for factorials/exponentials; Alternating Series Test for alternating; Integral Test when $f(n)$ is easily integrated.

## 11.8 Power Series
A **power series** centered at $a$ is $\sum_{n=0}^\infty c_n(x-a)^n$. By the Ratio/Root Test there are exactly three possibilities: it converges only at $x=a$; for all $x$; or for $|x-a|<R$ and diverges for $|x-a|>R$, where $R$ is the **radius of convergence**. The **interval of convergence** is the set of all $x$ where it converges (endpoints checked separately). A power series defines a function on its interval.

## 11.9 Representations of Functions as Power Series
Starting from the geometric series $\dfrac{1}{1-x}=\sum_{n=0}^\infty x^n$ ($|x|<1$), manipulation (substitution, multiplication) gives series for related functions. Crucially, a power series can be **differentiated and integrated term by term** within its radius of convergence (the radius is preserved). This yields, e.g., $\ln(1+x)=\sum (-1)^{n-1}\frac{x^n}{n}$ and $\tan^{-1}x=\sum(-1)^n\frac{x^{2n+1}}{2n+1}$ (Gregory's series; at $x=1$ gives the Leibniz formula for $\pi$).

## 11.10 Taylor and Maclaurin Series
If $f$ has a power series representation at $a$, its coefficients **must** be
$$c_n=\frac{f^{(n)}(a)}{n!}, \qquad f(x)=\sum_{n=0}^\infty \frac{f^{(n)}(a)}{n!}(x-a)^n \quad\text{(Taylor series)}.$$
The **Maclaurin series** is the special case $a=0$. The $n$th **Taylor polynomial** $T_n$ is the partial sum; $f=T_n+R_n$, and $f$ equals its Taylor series iff the remainder $R_n\to 0$. **Taylor's Inequality:** if $|f^{(n+1)}(x)|\le M$ on $|x-a|\le d$, then $|R_n(x)|\le \dfrac{M}{(n+1)!}|x-a|^{n+1}$.

**Key Maclaurin series** (with radius of convergence):
$$e^x=\sum_{n=0}^\infty\frac{x^n}{n!}\ (R=\infty), \quad \sin x=\sum_{n=0}^\infty\frac{(-1)^n x^{2n+1}}{(2n+1)!}\ (R=\infty), \quad \cos x=\sum_{n=0}^\infty\frac{(-1)^n x^{2n}}{(2n)!}\ (R=\infty),$$
plus $\frac{1}{1-x}$, $\ln(1+x)$, $\tan^{-1}x$ ($R=1$), and the **Binomial Series** $(1+x)^k=\sum\binom{k}{n}x^n$ ($|x|<1$). New series come from old by substitution, multiplication, and division.

## 11.11 Applications of Taylor Polynomials
Taylor polynomials $T_n$ approximate functions near $a$; **Taylor's Inequality** (or the Alternating Series Estimation Theorem) bounds the error, letting you choose $n$ for a target accuracy. Used in physics for linearization (special relativity, optics, pendulums, the resistivity of metals) — replacing a complicated function by its first one or two Taylor terms.

## Key Takeaways
- A **series** converges iff its partial sums converge; the **geometric series** ($|r|<1$) and **$p$-series** ($p>1$) are the benchmarks, and the **harmonic series** ($p=1$) diverges.
- Convergence tests: Divergence, Integral, Comparison/Limit Comparison (positive terms), Alternating Series, Ratio, Root — chosen by the series' form (§11.7); **absolute convergence implies convergence**.
- **Power series** $\sum c_n(x-a)^n$ converge on an interval of radius $R$ and can be differentiated/integrated termwise.
- **Taylor/Maclaurin series** $f(x)=\sum\frac{f^{(n)}(a)}{n!}(x-a)^n$ represent functions as infinite polynomials (with $R_n\to 0$); the standard series for $e^x,\sin x,\cos x$ and **Taylor polynomial** approximations (error bounded by Taylor's Inequality) are the chapter's culmination.

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch10-parametric-and-polar]] — previous chapter
- [[ch12-vectors-geometry-of-space]] — next chapter; begins multivariable calculus
- [[ch07-techniques-of-integration]] — the Integral Test uses improper integrals (§7.8)
- [[limit]] — sequences and series are defined via limits
- [[leonhard-euler]] — computed exact sums of $p$-series (e.g. $\sum 1/n^2=\pi^2/6$); $e$ notation
