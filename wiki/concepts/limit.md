---
title: "Limit (of a function)"
tags: [calculus, mathematics, limits, foundational-concept]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# Limit (of a function)

The **limit** is the foundational concept of calculus: $\displaystyle\lim_{x\to a} f(x) = L$ means $f(x)$ can be made arbitrarily close to $L$ by taking $x$ sufficiently close to $a$ (but not equal to $a$). The value of $f(a)$ — even whether it is defined — is irrelevant to the limit.

Made rigorous by the **ε–δ definition**: for every $\varepsilon>0$ there is a $\delta>0$ such that if $0<|x-a|<\delta$ then $|f(x)-L|<\varepsilon$. Here $\varepsilon$ is the error tolerance on the output and $\delta$ the required closeness of the input.

Limits are computed via the **Limit Laws** and the Direct Substitution Property (for polynomials/rational functions at points in their domain), with algebra (factoring, rationalizing) used to resolve $0/0$ forms, and the [[squeeze-theorem]] for trapped functions. Limits can be **one-sided** (left/right) and **infinite** (giving vertical asymptotes).

Both pillars of calculus are limits: the **derivative** is the limit of secant slopes (the tangent problem) and the **integral** is the limit of rectangle sums (the area problem) — see [[ch00-preview]].

## Related Pages
- [[ch01-functions-and-limits]] — Stewart Calculus 9e, where limits are defined (§1.5–1.7)
- [[continuity]] — defined as "limit equals function value"
- [[squeeze-theorem]] — a key tool for evaluating limits
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]]
