---
title: "Stewart Calculus 9e — Ch.6: Inverse Functions (Exp, Log, Inverse Trig)"
tags: [book, calculus, mathematics, exponential, logarithm, inverse-trig, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 6 — Inverse Functions: Exponential, Logarithmic, and Inverse Trigonometric Functions

Chapter 6 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 411–522; PDF pp. 448–559). The unifying theme is **inverse functions**: the most important pair is the exponential $f(x)=b^x$ and its inverse the logarithm $g(x)=\log_b x$. The chapter develops the properties, derivatives, and integrals of exponential, logarithmic, inverse-trigonometric, and hyperbolic functions, and closes with **L'Hospital's Rule**. (This edition offers two routes — exp-first §6.2–6.4 or log-as-integral §6.2*–6.4*; the results are the same.)

## 6.1 Inverse Functions and Their Derivatives
- A function is **one-to-one** if it never takes the same value twice: $f(x_1)\ne f(x_2)$ when $x_1\ne x_2$. **Horizontal Line Test:** one-to-one iff no horizontal line meets the graph more than once.
- The **inverse** $f^{-1}$ of a one-to-one $f$ satisfies $f^{-1}(y)=x \iff f(x)=y$, with $\text{domain}(f^{-1})=\text{range}(f)$ and vice versa. **Cancellation:** $f^{-1}(f(x))=x$ and $f(f^{-1}(x))=x$. (Caution: $f^{-1}\ne 1/f$.)
- To find $f^{-1}$: write $y=f(x)$, solve for $x$, swap $x$ and $y$. The graph of $f^{-1}$ is the reflection of $f$ across $y=x$.

## 6.2 Exponential Functions and Their Derivatives
$f(x)=b^x$ ($b>0$). Defined for irrational $x$ as a limit of rational powers, giving a continuous function on $\mathbb{R}$ with range $(0,\infty)$. **Laws of Exponents** hold. For $b>1$ it increases; $0<b<1$ decreases; $b=1$ constant. The $x$-axis is a horizontal asymptote.
- Derivative: $\dfrac{d}{dx}b^x = b^x\ln b$. The special base $e$ is the one making the factor $\ln b = 1$, so $\boxed{\dfrac{d}{dx}e^x = e^x}$ — the function equal to its own derivative.

## 6.3 The Natural Exponential Function
$e^x$ is the inverse of $\ln x$: $e^x=y \iff \ln y = x$, with cancellation $\ln(e^x)=x$ and $e^{\ln x}=x$ ($x>0$). $e^0=1$, $\ln e = 1$.

## 6.4 General Logarithmic and Logarithmic/Natural-Log Functions
- $\log_b x = \dfrac{\ln x}{\ln b}$ (change of base). Derivative: $\dfrac{d}{dx}\log_b x = \dfrac{1}{x\ln b}$, and the natural case $\boxed{\dfrac{d}{dx}\ln x = \dfrac{1}{x}}$.
- **Laws of Logarithms:** $\ln(xy)=\ln x+\ln y$, $\ln(x/y)=\ln x-\ln y$, $\ln(x^r)=r\ln x$.
- **Natural log as an integral** (the §6.2* route): $\ln x = \displaystyle\int_1^x \frac{1}{t}\,dt$, $x>0$; then $\frac{d}{dx}\ln x = \frac1x$ follows from FTC, and $e$ is defined by $\ln e = 1$ ($e\approx 2.71828$, irrational).
- Key integrals: $\displaystyle\int \frac{1}{x}\,dx = \ln|x| + C$ and $\displaystyle\int \tan x\,dx = \ln|\sec x| + C$.

## 6.5 Exponential Growth and Decay
A quantity with rate of change proportional to its size satisfies $\dfrac{dy}{dt}=ky$, whose solution is $y(t)=y_0 e^{kt}$ ($y_0$ = initial amount). $k>0$ → growth (population), $k<0$ → decay. Applications: population growth, **radioactive decay / half-life**, radiocarbon dating, Newton's Law of Cooling, **continuously compounded interest** $A=A_0 e^{rt}$.

## 6.6 Inverse Trigonometric Functions
Defined by restricting domains so the trig functions become one-to-one: $\sin^{-1}$ (range $[-\frac\pi2,\frac\pi2]$), $\cos^{-1}$ (range $[0,\pi]$), $\tan^{-1}$ (range $(-\frac\pi2,\frac\pi2)$, domain $\mathbb{R}$). **Derivatives:**
$$\frac{d}{dx}\sin^{-1}x = \frac{1}{\sqrt{1-x^2}}, \quad \frac{d}{dx}\cos^{-1}x = -\frac{1}{\sqrt{1-x^2}}, \quad \frac{d}{dx}\tan^{-1}x = \frac{1}{1+x^2},$$
with $\sec^{-1}$, $\csc^{-1}$, $\cot^{-1}$ analogous. (These reverse to give important integrals like $\int\frac{dx}{1+x^2}=\tan^{-1}x+C$.)

## 6.7 Hyperbolic Functions
Combinations of $e^x$ and $e^{-x}$ that obey trig-like identities: $\sinh x = \frac{e^x-e^{-x}}{2}$, $\cosh x = \frac{e^x+e^{-x}}{2}$, $\tanh x = \frac{\sinh x}{\cosh x}$. Identity: $\cosh^2 x - \sinh^2 x = 1$ (points $(\cosh t,\sinh t)$ lie on a hyperbola — hence "hyperbolic"). A hanging cable forms a **catenary** $y=c+a\cosh(x/a)$. **Derivatives:** $\frac{d}{dx}\sinh x=\cosh x$, $\frac{d}{dx}\cosh x=\sinh x$, $\frac{d}{dx}\tanh x=\text{sech}^2 x$. Inverse hyperbolic functions are defined and differentiated similarly.

## 6.8 Indeterminate Forms and L'Hospital's Rule
For limits of the **indeterminate forms** $\frac00$ or $\frac{\infty}{\infty}$: if $f,g$ are differentiable and the form is indeterminate at $a$, then
$$\lim_{x\to a}\frac{f(x)}{g(x)} = \lim_{x\to a}\frac{f'(x)}{g'(x)}$$
provided the right-hand limit exists (or is $\pm\infty$). Proved via **Cauchy's Mean Value Theorem**. Other indeterminate forms ($0\cdot\infty$, $\infty-\infty$, $0^0$, $\infty^0$, $1^\infty$) are converted into $\frac00$ or $\frac\infty\infty$ first (e.g. by combining fractions or taking logarithms). Shows, e.g., that exponentials beat any power and logarithms grow slower than any power.

## Key Takeaways
- **Inverse functions** (one-to-one, Horizontal Line Test, reflection across $y=x$) frame the whole chapter.
- The exp/log pair: $\frac{d}{dx}e^x=e^x$, $\frac{d}{dx}\ln x=\frac1x$, $\frac{d}{dx}b^x=b^x\ln b$, $\frac{d}{dx}\log_b x=\frac{1}{x\ln b}$; plus $\int\frac1x dx=\ln|x|+C$.
- **Exponential growth/decay** $y=y_0e^{kt}$ models populations, half-life, cooling, and compound interest.
- **Inverse trig** derivatives supply key integrals ($\frac{1}{\sqrt{1-x^2}}$, $\frac{1}{1+x^2}$); **hyperbolic** functions mirror trig via $e^{\pm x}$.
- **L'Hospital's Rule** evaluates $\frac00$ and $\frac\infty\infty$ (and, after conversion, all indeterminate forms).

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch05-applications-of-integration]] — previous chapter
- [[ch07-techniques-of-integration]] — next chapter; integration techniques (many use these functions)
- [[fundamental-theorem-of-calculus]] — defines $\ln x$ as an integral (§6.2* route)
- [[limit]] — L'Hospital's Rule evaluates indeterminate limits
