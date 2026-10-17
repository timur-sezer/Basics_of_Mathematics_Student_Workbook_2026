# Solution to Exercise 9: One-Sided Limits and an Asymptote

## 1. Problem Statement

Given the rational function:
$$
f(x) = \frac{1}{x - 2}
$$

1. Analyze the left-hand limit $\lim_{x \to 2^-} f(x)$ and the right-hand limit $\lim_{x \to 2^+} f(x)$.
2. Determine whether the two-sided limit $\lim_{x \to 2} f(x)$ exists.
3. Interpret the analytical results geometrically and identify any vertical asymptotes of the graph.

---

## 2. Theoretical Background and Concepts

1. **One-Sided Limits:**
   - **Right-hand limit ($x \to c^+$):** $x$ approaches $c$ strictly from values greater than $c$ ($x > c$, so $x - c > 0$).
   - **Left-hand limit ($x \to c^-$):** $x$ approaches $c$ strictly from values less than $c$ ($x < c$, so $x - c < 0$).

2. **Criterion for the Existence of a Two-Sided Limit:**
   A two-sided limit $\lim_{x \to c} f(x) = L$ exists (where $L$ may be a finite number or $\pm\infty$) if and only if **both one-sided limits exist and are identical**:
   $$
   \lim_{x \to c} f(x) = L \iff \lim_{x \to c^-} f(x) = L \quad \text{and} \quad \lim_{x \to c^+} f(x) = L
   $$
   If the left-hand and right-hand limits differ, the two-sided limit does not exist.

3. **Definition of a Vertical Asymptote:**
   The line $x = c$ is a **vertical asymptote** of the function $f(x)$ if at least one of the following one-sided limit conditions holds:
   $$
   \lim_{x \to c^+} f(x) = \pm\infty \quad \text{or} \quad \lim_{x \to c^-} f(x) = \pm\infty
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Right-Hand Limit ($x \to 2^+$)

When $x$ approaches $2$ from the right:
- $x > 2 \implies x - 2 > 0$.
- The denominator $x - 2$ approaches zero through strictly positive values:
  $$
  x - 2 \to 0^+
  $$
- The numerator is constant and positive ($+1$).
- Dividing a positive constant by an arbitrarily small positive quantity yields arbitrarily large positive values:
  $$
  \lim_{x \to 2^+} \frac{1}{x - 2} = +\infty
  $$

---

### Step 2: Compute the Left-Hand Limit ($x \to 2^-$)

When $x$ approaches $2$ from the left:
- $x < 2 \implies x - 2 < 0$.
- The denominator $x - 2$ approaches zero through strictly negative values:
  $$
  x - 2 \to 0^-
  $$
- The numerator is constant and positive ($+1$).
- Dividing a positive constant by an arbitrarily small negative quantity yields arbitrarily large negative values:
  $$
  \lim_{x \to 2^-} \frac{1}{x - 2} = -\infty
  $$

---

### Step 3: Existence of the Two-Sided Limit

Compare the two one-sided limits:
$$
\lim_{x \to 2^+} f(x) = +\infty, \qquad \lim_{x \to 2^-} f(x) = -\infty
$$
Because the two one-sided limits point to opposite infinities:
$$
+\infty \ne -\infty
$$
**Conclusion:**
The two-sided limit $\lim_{x \to 2} \frac{1}{x - 2}$ **does not exist** (neither as a finite real number nor as an extended real infinity).

---

### Step 4: Geometric Interpretation and Vertical Asymptote

1. **Vertical Asymptote:**
   Because $\lim_{x \to 2^+} f(x) = +\infty$ and $\lim_{x \to 2^-} f(x) = -\infty$, the vertical line:
   $$
   x = 2
   $$
   is a **vertical asymptote** for the graph of $f(x)$.
2. **Behavior of the Hyperbola:**
   - The graph of $f(x) = \frac{1}{x - 2}$ is a standard rectangular hyperbola $y = \frac{1}{x}$ shifted $2$ units to the right.
   - As one walks along the curve from the right towards $x = 2$, the graph shoots upwards asymptotically towards $+\infty$, hugging the right side of the vertical line $x = 2$.
   - As one walks along the curve from the left towards $x = 2$, the graph plunges downwards asymptotically towards $-\infty$, hugging the left side of the vertical line $x = 2$.
   - This mismatch creates an infinite, non-removable (essential) discontinuity at $x = 2$.

3. **Required Graphical Sketch of $y = \frac{1}{x - 2}$:**
```text
                      y
                      ^               : (Vertical Asymptote x = 2)
                      |               :
                      |               :    | (Right branch -> +inf as x -> 2+)
                    2 |               :    |
                      |               :   /
                    1 |               :  * (3, 1)
                      |               : /  
   -------------------+---------------+----\-----------------> x (Horizontal Asymptote y = 0)
                 (0,0)|           1   : 2   \  3       4
             (0,-0.5)*|               :      ------- (approaches y = 0+)
                      |  * (1, -1)    :
                   -1 | /             :
                      |/              :
      - - - - - - - - |               :    | (Left branch -> -inf as x -> 2-)
      (approaches 0-) |               :    v
```
*Labels:* Vertical asymptote $x = 2$ (dashed); horizontal asymptote $y = 0$ ($x$-axis); left branch strictly below $y = 0$ for $x < 2$ passing through $(0, -0.5)$ and $(1, -1)$ and plunging to $-\infty$ as $x \to 2^-$; right branch strictly above $y = 0$ for $x > 2$ descending from $+\infty$ as $x \to 2^+$ and passing through $(3, 1)$ toward $y = 0^+$.

---

## 4. Verification and Consistency Checks

1. **Numerical Table of Approaching Values:**

| Approaching from Left ($x < 2$) | Value $f(x) = \frac{1}{x - 2}$ | Approaching from Right ($x > 2$) | Value $f(x) = \frac{1}{x - 2}$ |
| :---: | :---: | :---: | :---: |
| $x = 1.9$ | $\frac{1}{-0.1} = -10$ | $x = 2.1$ | $\frac{1}{0.1} = +10$ |
| $x = 1.99$ | $\frac{1}{-0.01} = -100$ | $x = 2.01$ | $\frac{1}{0.01} = +100$ |
| $x = 1.999$ | $\frac{1}{-0.001} = -1{,}000$ | $x = 2.001$ | $\frac{1}{0.001} = +1{,}000$ |
| $x = 1.9999$ | $\frac{1}{-0.0001} = -10{,}000$ | $x = 2.0001$ | $\frac{1}{0.0001} = +10{,}000$ |
| $x \to 2^-$ | $\to -\infty$ | $x \to 2^+$ | $\to +\infty$ |

2. **Odd Symmetry Around the Center Point $(2, 0)$:**
   Notice that for any displacement $h > 0$:
   $$
   f(2 + h) = \frac{1}{(2 + h) - 2} = \frac{1}{h}
   $$
   $$
   f(2 - h) = \frac{1}{(2 - h) - 2} = -\frac{1}{h} = -f(2 + h)
   $$
   Because $f(2 - h) = -f(2 + h)$, the function is point-symmetric across $(2, 0)$. This anti-symmetry guarantees that if the right-hand limit diverges to $+\infty$, the left-hand limit must diverge to $-\infty$.
