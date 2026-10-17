# Solution to Problem 3: A Rational Function

## 1. Problem Statement

Perform a complete mathematical analysis of the rational function:
$$
f(x) = \frac{x + 1}{x - 2}
$$

1. Determine the maximal domain of definition $\mathcal{D}_f$.
2. Find the intercepts with the coordinate axes (zeros and $y$-intercept).
3. Determine all vertical, horizontal, or oblique asymptotes by evaluating the relevant one-sided and infinite limits.
4. Compute the first derivative $f'(x)$ and determine the intervals of monotonicity and the presence of any extrema.
5. Analyze concavity using the second derivative $f''(x)$.
6. Provide an ASCII graph sketch summarizing all identified asymptotic and monotonic features.

---

## 2. Theoretical Background and Concepts

1. **Domain of a Rational Function:**
   The function is defined for all real numbers where the denominator does not vanish: $Q(x) \neq 0$.

2. **Asymptotes of Rational Functions:**
   - **Vertical Asymptote ($x = c$):** Occurs where the denominator has a non-removable zero ($Q(c) = 0, P(c) \neq 0$), yielding $\lim_{x \to c^\pm} f(x) = \pm\infty$.
   - **Horizontal Asymptote ($y = L$):** Occurs if $\lim_{x \to \pm\infty} f(x) = L$ is finite. For $\frac{P(x)}{Q(x)}$ where $\deg(P) = \deg(Q)$, the asymptote is the ratio of the leading coefficients.

3. **Hyperbolic Form Decomposition:**
   A homographic function $\frac{ax + b}{cx + d}$ can be decomposed via algebraic division into:
   $$
   f(x) = y_0 + \frac{k}{x - x_0}
   $$
   revealing that its graph is a standard rectangular hyperbola centered at $(x_0, y_0)$.

4. **Monotonicity from the Quotient Rule:**
   $$
   f'(x) = \frac{P'(x)Q(x) - P(x)Q'(x)}{[Q(x)]^2}
   $$
   Because $[Q(x)]^2 > 0$ on $\mathcal{D}_f$, the sign of $f'(x)$ is determined entirely by its numerator.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Determine the Domain $\mathcal{D}_f$

Set the denominator to zero:
$$
x - 2 = 0 \iff x = 2
$$
The function is undefined at $x = 2$.
Therefore, the domain is:
$$
\mathcal{D}_f = \mathbb{R} \setminus \{2\} = (-\infty, 2) \cup (2, \infty)
$$

---

### Step 2: Intercepts with the Coordinate Axes

1. **$x$-intercept (Zero of the function):**
   Set $f(x) = 0$:
   $$
   \frac{x + 1}{x - 2} = 0 \iff x + 1 = 0 \iff x = -1
   $$
   The zero is at $(-1, 0)$.

2. **$y$-intercept:**
   Evaluate at $x = 0 \in \mathcal{D}_f$:
   $$
   f(0) = \frac{0 + 1}{0 - 2} = -\frac{1}{2} = -0.5
   $$
   The $y$-intercept is at $(0, -0.5)$.

---

### Step 3: Analysis of Asymptotes

1. **Vertical Asymptote at $x = 2$:**
   Examine one-sided limits as $x \to 2$:
   - As $x \to 2^-$ ($x < 2$): Numerator $x + 1 \to 3 > 0$, Denominator $x - 2 \to 0^-$.
     $$
     \lim_{x \to 2^-} \frac{x + 1}{x - 2} = \frac{3}{0^-} = -\infty
     $$
   - As $x \to 2^+$ ($x > 2$): Numerator $x + 1 \to 3 > 0$, Denominator $x - 2 \to 0^+$.
     $$
     \lim_{x \to 2^+} \frac{x + 1}{x - 2} = \frac{3}{0^+} = +\infty
     $$
   The vertical line **$x = 2$** is a vertical asymptote.

2. **Horizontal Asymptote as $x \to \pm\infty$:**
   Divide numerator and denominator by $x$:
   $$
   \lim_{x \to \pm\infty} \frac{x + 1}{x - 2} = \lim_{x \to \pm\infty} \frac{1 + \frac{1}{x}}{1 - \frac{2}{x}} = \frac{1 + 0}{1 - 0} = 1
   $$
   The horizontal line **$y = 1$** is a horizontal asymptote in both directions ($x \to +\infty$ and $x \to -\infty$).

3. **Oblique Asymptote:**
   Since degrees of numerator and denominator are equal ($\deg P = \deg Q = 1$), there is no oblique asymptote.

---

### Step 4: Derivative, Monotonicity, and Extrema

Apply the quotient rule to $f(x) = \frac{x + 1}{x - 2}$:
$$
f'(x) = \frac{\frac{d}{dx}[x + 1](x - 2) - (x + 1)\frac{d}{dx}[x - 2]}{(x - 2)^2} = \frac{(1)(x - 2) - (x + 1)(1)}{(x - 2)^2}
$$
Simplify the numerator:
$$
(x - 2) - (x + 1) = x - 2 - x - 1 = -3
$$
Thus:
$$
f'(x) = \frac{-3}{(x - 2)^2}
$$

**Sign Analysis of $f'(x)$:**
- The numerator is constant: $-3 < 0$.
- The denominator is a square: $(x - 2)^2 > 0$ for all $x \neq 2$.
- Consequently:
  $$
  f'(x) < 0 \quad \forall x \in \mathcal{D}_f
  $$

**Monotonicity Conclusion:**
- The function $f(x)$ is **strictly decreasing** on $(-\infty, 2)$.
- The function $f(x)$ is **strictly decreasing** on $(2, \infty)$.
*(Important note: $f$ is not decreasing on the union $(-\infty, 2) \cup (2, \infty)$ because $f(1) = -2$ while $f(3) = 4 > -2$).*
- Because $f'(x) \neq 0$ everywhere and no interior points in $\mathcal{D}_f$ fail to have a derivative, there are **no local extrema**.

---

### Step 5: Second Derivative and Concavity

Differentiate $f'(x) = -3(x - 2)^{-2}$:
$$
f''(x) = -3 \cdot (-2)(x - 2)^{-3} = \frac{6}{(x - 2)^3}
$$
- For $x < 2$: $(x - 2)^3 < 0 \implies f''(x) < 0$ (the graph is **concave downward** $\cap$).
- For $x > 2$: $(x - 2)^3 > 0 \implies f''(x) > 0$ (the graph is **concave upward** $\cup$).
- At $x = 2$, concavity flips, but because $x = 2 \notin \mathcal{D}_f$, there is **no inflection point**.

---

### Step 6: Hyperbolic Canonical Form and Graph Sketch

Perform division:
$$
f(x) = \frac{(x - 2) + 3}{x - 2} = 1 + \frac{3}{x - 2}
$$
This represents the standard hyperbola $y = \frac{3}{x}$ translated horizontally by $+2$ and vertically by $+1$.

**ASCII Graph Sketch:**
```text
                       y               : (Vertical Asymptote x = 2)
                       ^               :
                   5   |               :   | (Right branch: decreases from +inf)
                   4   |               :   * (3, 4)
                   3   |               :    \
                   2   |               :     * (5, 2)
   - - - - - - - - 1 - + - - - - - - - : - - - \ - - - - - - (y = 1) Horizontal Asymptote
             (-1,0)    |               :        ------ (approaches y = 1 from above, stays > 1)
   ------------*-------+---------------+---------------------> x
             -1        | (0, 0)        : 2       3     4     5
                       |* (0, -0.5)    :
                  -1   |               :
                       |               :
                  -2   |       * (1,-2):
                       |        \      :
                  -3   |         \     :
                       |          |    : (Left branch: plunges to -inf as x -> 2-)
                       v          v    :
```
*Labels:* Vertical asymptote $x = 2$ (dashed); horizontal asymptote $y = 1$ (dashed); zero at $(-1, 0)$ strictly to the left of the $y$-axis; $y$-intercept at $(0, -0.5)$; point $(1, -2)$ with left branch decreasing toward $-\infty$ as $x \to 2^-$; right branch decreasing from $+\infty$ near $x = 2^+$, passing through $(3, 4)$ and $(5, 2)$, and approaching $y = 1$ asymptotically from above without ever crossing $y = 1$ or the $x$-axis.

---

## 4. Verification and Consistency Checks

1. **Table of Values Across the Domain:**
   | $x$ | $-4$ | $-1$ | $0$ | $1$ | $1.9$ | $2.1$ | $3$ | $5$ |
   |:---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
   | $f(x) = 1 + \frac{3}{x-2}$ | $0.5$ | $0$ | $-0.5$ | $-2$ | $-29$ | $+31$ | $4$ | $2$ |
   | $f'(x) = \frac{-3}{(x-2)^2}$ | $-0.083$ | $-0.333$ | $-0.75$ | $-3.0$ | $-300$ | $-300$ | $-3.0$ | $-0.333$ |

   All values strictly decrease on each branch, matching our analytical results.

2. **Intersection with Horizontal Asymptote Check:**
   Set $f(x) = 1$:
   $$
   1 + \frac{3}{x - 2} = 1 \implies \frac{3}{x - 2} = 0 \implies \text{No solution}
   $$
   The curve never crosses its horizontal asymptote $y = 1$, which is fully consistent with the hyperbolic structure.
