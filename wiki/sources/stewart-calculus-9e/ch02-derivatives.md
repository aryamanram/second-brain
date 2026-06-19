---
title: "Stewart Calculus 9e — Ch.2: Derivatives"
tags: [book, calculus, mathematics, derivatives, differentiation, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Chapter 2 — Derivatives

Chapter 2 of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 107–208; PDF pp. 144–245). Begins **differential calculus**: how one quantity changes in relation to another. The central object is the **derivative**, an outgrowth of the tangent and velocity problems from [[ch01-functions-and-limits|Ch.1]]. The chapter defines the derivative, then builds the full toolkit of **differentiation rules** (power, product, quotient, chain) plus trig and implicit differentiation.

## 2.1 Derivatives and Rates of Change
The **tangent line** to $y=f(x)$ at $P(a,f(a))$ is the line through $P$ with slope the limit of secant slopes:
$$m = \lim_{x\to a}\frac{f(x)-f(a)}{x-a} = \lim_{h\to 0}\frac{f(a+h)-f(a)}{h}.$$
The same limit gives the **instantaneous velocity** $v(a)=\lim_{h\to 0}\frac{f(a+h)-f(a)}{h}$ for a position function $s=f(t)$.

**Definition — the derivative of $f$ at $a$:**
$$f'(a) = \lim_{h\to 0}\frac{f(a+h)-f(a)}{h} = \lim_{x\to a}\frac{f(x)-f(a)}{x-a},$$
when the limit exists. Two interpretations: (1) the **slope of the tangent** to $y=f(x)$ at $a$; (2) the **instantaneous rate of change** of $y$ with respect to $x$ at $x=a$. The average rate of change $\Delta y/\Delta x$ over $[x_1,x_2]$ becomes the instantaneous rate as $\Delta x\to 0$. Applications: velocity, **marginal cost** $C'(x)$ in economics, rate of reaction in chemistry, rate of population growth in biology.

## 2.2 The Derivative as a Function
Letting $a$ vary turns the derivative into a new **function**:
$$f'(x) = \lim_{h\to 0}\frac{f(x+h)-f(x)}{h},$$
with domain $\{x \mid f'(x) \text{ exists}\}$ (possibly smaller than that of $f$). The graph of $f'$ can be sketched from the graph of $f$ by reading off tangent slopes.

- **Notations:** $f'(x) = y' = \dfrac{dy}{dx} = \dfrac{df}{dx} = \dfrac{d}{dx}f(x) = Df(x) = D_x f(x)$. The Leibniz $dy/dx$ is suggestive but is a single symbol, not a literal ratio.
- **Differentiability:** $f$ is **differentiable at $a$** if $f'(a)$ exists; differentiable on an interval if differentiable at every interior point.
- **Theorem 4:** if $f$ is differentiable at $a$, then $f$ is **continuous at $a$**. (The converse is false — e.g. $f(x)=|x|$ is continuous but not differentiable at 0.)
- **How differentiability fails** (Figure 7, described): a **corner** (e.g. $|x|$ at 0), a **discontinuity**, or a **vertical tangent** ($|f'(x)|\to\infty$).
- **Higher derivatives:** $f'' = (f')'$ is the **second derivative** $\dfrac{d^2y}{dx^2}$; for position $s(t)$, $v=s'$ is velocity, $a=v'=s''$ is **acceleration**, and $s'''$ is the **jerk** (rate of change of acceleration).

## 2.3 Differentiation Formulas
Rules that avoid computing limits each time:
- **Constant:** $\dfrac{d}{dx}(c)=0$.
- **Power Rule:** $\dfrac{d}{dx}(x^n)=nx^{n-1}$ (for any real $n$; proved via the Binomial Theorem for positive integers, extended later).
- **Constant Multiple:** $\dfrac{d}{dx}[cf]=c\,f'$.
- **Sum / Difference:** $(f\pm g)' = f' \pm g'$.
- **Product Rule:** $\dfrac{d}{dx}[f g] = f g' + g f'$.
- **Quotient Rule:** $\dfrac{d}{dx}\!\left[\dfrac{f}{g}\right] = \dfrac{g f' - f g'}{g^2}$.

Each is proved from the limit definition (the Product Rule via the add-and-subtract $f(x+h)g(x)$ trick). The Quotient Rule extends the Power Rule to negative integer exponents. Application: finding where a curve has **horizontal tangents** (set $dy/dx=0$).

## 2.4 Derivatives of Trigonometric Functions
Two foundational limits (proved geometrically via the Squeeze Theorem in §2.4):
$$\lim_{\theta\to 0}\frac{\sin\theta}{\theta}=1, \qquad \lim_{\theta\to 0}\frac{\cos\theta-1}{\theta}=0.$$
From these, using the addition formula for sine:
$$\frac{d}{dx}(\sin x)=\cos x, \quad \frac{d}{dx}(\cos x)=-\sin x, \quad \frac{d}{dx}(\tan x)=\sec^2 x,$$
and likewise $\dfrac{d}{dx}(\csc x)=-\csc x\cot x$, $\dfrac{d}{dx}(\sec x)=\sec x\tan x$, $\dfrac{d}{dx}(\cot x)=-\csc^2 x$. **Radian measure is required** for these formulas. The two limits also let you evaluate related limits like $\lim_{x\to 0}\frac{\sin 7x}{4x}=\frac74$.

## 2.5 The Chain Rule
For a composite $F = f\circ g$, i.e. $F(x)=f(g(x))$:
$$F'(x) = f'(g(x))\cdot g'(x), \qquad \text{or in Leibniz form}\quad \frac{dy}{dx} = \frac{dy}{du}\,\frac{du}{dx}.$$
"Differentiate the outer function (evaluated at the inner function), times the derivative of the inner function." Combined with the Power Rule it gives the **General Power Rule** $\dfrac{d}{dx}[g(x)]^n = n[g(x)]^{n-1}g'(x)$, and combined with trig derivatives, e.g. $\dfrac{d}{dx}\sin u = \cos u\,\dfrac{du}{dx}$. Example: $\dfrac{d}{dx}\sqrt{x^2+1} = \dfrac{x}{\sqrt{x^2+1}}$.

## 2.6 Implicit Differentiation
When $y$ is defined **implicitly** by a relation in $x$ and $y$ (e.g. $x^2+y^2=25$, or the **folium of Descartes** $x^3+y^3=6xy$) rather than solved as $y=f(x)$, you can still find $dy/dx$: differentiate both sides with respect to $x$, treating $y$ as a function of $x$ (so $\frac{d}{dx}y^n = ny^{n-1}\frac{dy}{dx}$ by the Chain Rule), then solve algebraically for $dy/dx$. This handles curves impossible to solve explicitly (e.g. $\sin(x+y)=y^2\cos x$). **Second derivatives** of implicit functions are found by differentiating $y'$ again and substituting.

## Key Takeaways
- The **derivative** $f'(a)=\lim_{h\to 0}\frac{f(a+h)-f(a)}{h}$ is simultaneously the tangent slope and the instantaneous rate of change.
- **Differentiable ⇒ continuous** (not conversely); differentiability fails at corners, jumps, and vertical tangents.
- The **rule toolkit** — power, constant-multiple, sum/difference, product, quotient, chain — plus trig derivatives lets you differentiate any elementary function without limits.
- The **Chain Rule** is the workhorse for composites; **implicit differentiation** extends differentiation to relations that can't be solved for $y$.

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[ch01-functions-and-limits]] — previous chapter; the limit and the tangent/velocity problems the derivative formalizes
- [[ch03-applications-of-differentiation]] — next chapter; uses derivatives for extrema, shape of graphs, optimization
- [[limit]] · [[squeeze-theorem]] — the derivative is a limit; trig-derivative limits use the Squeeze Theorem
- [[derivative]] · [[chain-rule]] — core concepts promoted from this chapter
- [[isaac-newton]] · [[gottfried-leibniz]] — Leibniz notation $dy/dx$; both developed differential calculus
