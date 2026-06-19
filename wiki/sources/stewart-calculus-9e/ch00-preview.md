---
title: "Stewart Calculus 9e — A Preview of Calculus"
tags: [book, calculus, mathematics, limits, source]
date_created: 2026-06-18
date_updated: 2026-06-18
sources: [raw/books/stewart-calculus-9e.pdf]
---

# A Preview of Calculus

Front-matter chapter of [[stewart-calculus-9e/_hub|Stewart, Calculus (9th Edition)]] (printed pp. 1–5; PDF pp. 38–42). It motivates the whole book: calculus is "fundamentally different" from prior math because it is **dynamic** — it deals with change and motion, with quantities that *approach* other quantities. Every main idea is built on the concept of a **limit**.

## What Is Calculus?
The world is continually changing; we want to analyze quantities (populations, temperatures, currency values, falling-object speed) that change continuously. Algebra and analytic geometry are static; calculus extends them to handle change. Two foundational problems organize the subject:
- The **area problem** → leads to *integral calculus*.
- The **tangent problem** → leads to *differential calculus*.

These two problems look unrelated but turn out to be intimately connected (the Fundamental Theorem of Calculus, Ch. 4 / [[ch04-integrals]]).

## The Area Problem
Goes back ~2500 years to the Greek **method of exhaustion**: to find the area $A$ of a region, inscribe polygons whose areas $A_n$ are known and let the number of sides grow.

- *Figure 1* (described): an irregular polygon split into triangles, illustrating $A = A_1 + A_2 + A_3 + A_4 + A_5$ — area by summing triangles.
- *Figure 2* (described): a sequence of regular polygons inscribed in a circle — triangle $A_3$, square $A_4$, pentagon $A_5$, hexagon $A_6$, … up to $A_{12}$ and beyond — visibly filling the circle as $n$ grows.

As $n \to \infty$, $A_n$ approaches the true area. This is written as a **limit**:
$$A = \lim_{n \to \infty} A_n$$
The Greeks did not use limits explicitly; Eudoxus (5th c. BC) used the indirect "method of exhaustion." Applied to a circle of radius $r$, this recovers the familiar $A = \pi r^2$.

- *Figures 3–4* (described): the region under a curve $y = f(x)$, approximated by $n$ rectangles $R_1, R_2, \dots, R_n$; as the rectangles get narrower the approximation improves. The area is
$$A = \lim_{n \to \infty} A_n, \qquad A_n = R_1 + R_2 + \dots + R_n$$
This same rectangle-sum idea (Ch. 4) computes volumes, arc length, water-tank outflow, fuel to launch a rocket, etc.

## The Tangent Problem
To find the tangent line $\ell$ to a curve $y = f(x)$ at a point $P$, take a nearby point $Q$ on the curve and form the **secant line** $PQ$. As $Q \to P$ along the curve, the secant lines rotate toward the tangent as their limiting position.

- *Figures 5–7* (described): point $P$ with tangent $\ell$; successive secants $PQ$ approaching $\ell$ as $Q$ slides toward $P$; the slope triangle with run $x - a$ and rise $f(x) - f(a)$.

The slope $m_{PQ}$ of the secant through $P(a, f(a))$ and $Q(x, f(x))$ is
$$m_{PQ} = \frac{f(x) - f(a)}{x - a}$$
The tangent slope $m$ is the limit of the secant slopes:
$$m = \lim_{Q \to P} m_{PQ} = \lim_{x \to a} \frac{f(x) - f(a)}{x - a}$$
This is the **derivative**. It has many interpretations: instantaneous velocity, rate of a chemical reaction, force direction on a hanging chain (Ch. 1–2, [[ch01-functions-and-limits]], [[ch02-derivatives]]).

## The Connection — and the History
The area and tangent problems are the inverse of each other; recognizing this is the central discovery of calculus, the **Fundamental Theorem of Calculus** (Ch. 4). It lets us evaluate areas by reversing differentiation. [[isaac-newton|Isaac Newton]] (1642–1727) and [[gottfried-leibniz|Gottfried Leibniz]] (1646–1716) independently established it, turning calculus into a tool for real-world problems.

## Ten Motivating Questions
The chapter closes with 10 questions calculus will answer later in the book — e.g. designing a safe roller-coaster transition (§2.3), where a pilot should start descent (§2.3), the highest point of a rainbow (§3.1), work to build the Pyramid of Khufu (§5.4), escape velocity (§7.8), why planets and satellites move in ellipses (§13.4), and maximizing a hydroelectric station's power output (§14.8).

## Key Takeaways
- Calculus = the mathematics of change, built entirely on the **limit**.
- Two pillars: the **area problem** (→ integrals) and the **tangent problem** (→ derivatives).
- They are inverse operations, unified by the **Fundamental Theorem of Calculus**.

## Related Pages
- [[stewart-calculus-9e/_hub|Stewart Calculus 9e]] — book hub
- [[isaac-newton]] · [[gottfried-leibniz]] — independent co-inventors of calculus
- [[ch01-functions-and-limits]] — next chapter; defines the limit rigorously
- [[ch02-derivatives]] — the tangent problem formalized
- [[ch04-integrals]] — the area problem and the Fundamental Theorem of Calculus
