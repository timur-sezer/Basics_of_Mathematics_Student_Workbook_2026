# Solution to Exercise 7: Limit at a Point and Canceling a Factor

## 1. Problem Statement

Compute the limit of the rational function at the finite point $x = 3$:
$$
\lim_{x \to 3} \frac{x^2 - 4x + 3}{x - 3}
$$

1. Evaluate the limit using algebraic factorization and cancellation.
2. Explain fundamentally why the actual value of the function at $x = 3$ is not needed to compute the limit, and why a limit can exist even if the function is undefined at the point.

---

## 2. Theoretical Background and Concepts

1. **The Indeterminate Form $\frac{0}{0}$:**
   Direct substitution of $x = 3$ into the numerator and denominator gives:
   $$
   \frac{3^2 - 4(3) + 3}{3 - 3} = \frac{9 - 12 + 3}{0} = \frac{0}{0}
   $$
   The form $\frac{0}{0}$ is indeterminate. By Bézout's Little Theorem, if a polynomial $P(x)$ satisfies $P(c) = 0$, then $(x - c)$ is an algebraic factor of $P(x)$:
   $$
   P(x) = (x - c) Q(x)
   $$

2. **Rigorous Definition of a Function Limit (Cauchy):**
   The statement $\lim_{x \to c} f(x) = L$ means that for every $\varepsilon > 0$, there exists $\delta > 0$ such that:
   $$
   0 < |x - c| < \delta \implies |f(x) - L| < \varepsilon
   $$
   The crucial inequality is $0 < |x - c|$. This condition explicitly **excludes the point $x = c$ itself** from consideration. The limit is concerned solely with the values of $f(x)$ as $x$ approaches $c$ through neighboring points, completely independent of the value $f(c)$ (or whether $f(c)$ even exists).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Factor the Numerator

Consider the quadratic polynomial in the numerator:
$$
P(x) = x^2 - 4x + 3
$$
Find its roots using the quadratic formula or factoring by inspection:
- Sum of roots: $r_1 + r_2 = 4$
- Product of roots: $r_1 r_2 = 3$
- The roots are $r_1 = 1$ and $r_2 = 3$.

Thus, the numerator factors as:
$$
x^2 - 4x + 3 = (x - 3)(x - 1)
$$

---

### Step 2: Simplify the Expression in a Punctured Neighborhood

Write the rational function in factored form:
$$
f(x) = \frac{(x - 3)(x - 1)}{x - 3}
$$

In evaluating the limit as $x \to 3$, we examine values of $x$ close to $3$, but **strictly not equal to $3$** ($x \ne 3$).
Because $x \ne 3$, the factor $x - 3 \ne 0$. We can therefore divide numerator and denominator by $x - 3$:
$$
f(x) = x - 1 \quad \text{for all } x \in \mathbb{R} \setminus \{3\}
$$

The function $f(x)$ is algebraically identical to the linear polynomial $g(x) = x - 1$ everywhere except at the single isolated point $x = 3$.

---

### Step 3: Compute the Limit

Since limits depend only on the behavior in a punctured neighborhood ($x \ne 3$), and the polynomial $g(x) = x - 1$ is continuous everywhere:
$$
\lim_{x \to 3} \frac{x^2 - 4x + 3}{x - 3} = \lim_{x \to 3} (x - 1) = 3 - 1 = 2
$$

Thus:
$$
\lim_{x \to 3} \frac{x^2 - 4x + 3}{x - 3} = 2
$$

---

### Step 4: Why the Value at $x = 3$ Is Not Needed

1. **Domain vs. Limit Existence:**
   - The original function $f(x) = \frac{x^2 - 4x + 3}{x - 3}$ has domain $D_f = \mathbb{R} \setminus \{3\}$. At $x = 3$, division by zero occurs; $f(3)$ is completely undefined.
   - Despite $f(3)$ not existing, the limit $\lim_{x \to 3} f(x) = 2$ exists unconditionally.
2. **The Role of the Punctured Neighborhood:**
   - The definition of limit asks: *"Can we make $f(x)$ as close to $2$ as desired by picking $x$ sufficiently close to $3$?"*
   - For any $x$ near $3$ (such as $x = 2.999$ or $x = 3.001$), $f(x) = x - 1$ evaluates to $1.999$ or $2.001$, which is arbitrarily close to $2$.
   - What happens *at* $x = 3$ is irrelevant to the question of what happens *near* $x = 3$.
3. **Removable Discontinuity:**
   Geometrically, the graph of $f(x)$ is a straight line $y = x - 1$ with a single "hole" (removable discontinuity) at the point $(3, 2)$. The limit simply identifies the coordinates of this missing point.

---

## 4. Verification and Consistency Checks

1. **Numerical Table of Approaching Values:**

| Approaching from Left ($x < 3$) | $f(x) = \frac{x^2 - 4x + 3}{x - 3}$ | Approaching from Right ($x > 3$) | $f(x) = \frac{x^2 - 4x + 3}{x - 3}$ |
| :---: | :---: | :---: | :---: |
| $x = 2.9$ | $1.900000$ | $x = 3.1$ | $2.100000$ |
| $x = 2.99$ | $1.990000$ | $x = 3.01$ | $2.010000$ |
| $x = 2.999$ | $1.999000$ | $x = 3.001$ | $2.001000$ |
| $x = 2.9999$ | $1.999900$ | $x = 3.0001$ | $2.000100$ |
| $x \to 3^-$ | $\to 2$ | $x \to 3^+$ | $\to 2$ |

Both one-sided numerical progressions converge symmetrically to $2.0000$.

2. **$\varepsilon$-$\delta$ Proof:**
   Given any $\varepsilon > 0$, we require $|f(x) - 2| < \varepsilon$ whenever $0 < |x - 3| < \delta$.
   For $x \ne 3$:
   $$
   |f(x) - 2| = |(x - 1) - 2| = |x - 3|
   $$
   Thus, choosing $\delta = \varepsilon$ guarantees that if $0 < |x - 3| < \delta$, then $|f(x) - 2| = |x - 3| < \varepsilon$.
   This confirms that the limit is $2$.
