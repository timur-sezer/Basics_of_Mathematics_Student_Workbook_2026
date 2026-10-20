# Solution to Problem 12: A Function with an Absolute Value

## 1. Problem Statement

Analyze the absolute value function:
$$
f(x) = |x^2 - 4|
$$

1. Analyze and sketch the base polynomial $p(x) = x^2 - 4$.
2. Explain the geometric and algebraic effect of applying the absolute value operator to $p(x)$.
3. Write $f(x)$ as an explicit piecewise function without absolute value bars.
4. Identify the points where the derivative does not exist. Compute the one-sided derivatives at these points to prove non-differentiability analytically.
5. Provide a geometric justification for why the derivative fails to exist at these points and connect this to Fermat's theorem on extrema.

---

## 2. Theoretical Background and Concepts

1. **The Absolute Value Transformation:**
   For any real function $p(x)$:
   $$
   f(x) = |p(x)| = \begin{cases} p(x), & \text{if } p(x) \ge 0 \\ -p(x), & \text{if } p(x) < 0 \end{cases}
   $$
   Geometrically, the operation preserves the portions of the graph lying on or above the $x$-axis ($y \ge 0$), and reflects the portions lying below the $x$-axis ($y < 0$) upward across the $x$-axis.

2. **Differentiability and Corner Points (Cusps):**
   A continuous function is differentiable at $x_0$ if and only if the left-hand and right-hand derivatives exist and are equal:
   $$
   f'_-(x_0) = f'_+(x_0)
   $$
   If $p(x_0) = 0$ and $p'(x_0) = m \neq 0$, the base curve $y = p(x)$ crosses the $x$-axis transversally at non-zero slope $m$.
   The absolute value operator reflects the portion below the axis, causing the incoming and outgoing one-sided slopes at $x_0$ to have opposite signs:
   $$
   \{- |m|, +|m|\}
   $$
   Because $-|m| \neq +|m|$ (since $m \neq 0$), a **sharp corner (kink)** is created at $(x_0, 0)$, rendering the function non-differentiable at $x_0$.

3. **Fermat's Theorem for Critical Points:**
   A local extremum of a function on an open interval can occur at:
   - **Stationary points:** where $f'(x) = 0$.
   - **Singular points:** where $f'(x)$ does not exist.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Analysis of the Base Parabola $p(x) = x^2 - 4$

1. **Features of $p(x)$:**
   - Parabola opening upward with vertex at $V(0, -4)$.
   - Roots (zeros):
     $$
     x^2 - 4 = 0 \iff (x - 2)(x + 2) = 0 \iff x = -2 \quad \text{or} \quad x = 2
     $$
   - Sign of $p(x)$:
     - On $(-\infty, -2) \cup (2, \infty)$: $p(x) > 0$.
     - On $(-2, 2)$: $p(x) < 0$ (the parabolic trough dips below the $x$-axis, reaching $-4$ at $x = 0$).

2. **Required Sketch of Base Parabola $p(x) = x^2 - 4$:**
```text
                                  y
                                  ^
              4   \               |               /
              2    \              |              /
   -----------------*-------------+-------------*------------------> x
                 (-2, 0)          | (0, 0)    (2, 0)
             -2      \            |            /
                      \           |           /
             -4 -------+----------*----------+---------------------- y = -4
                       |       V(0, -4)      |
```
*Labels:* Vertex $V(0, -4)$ located on the $y$-axis ($x = 0$); roots at $(-2, 0)$ and $(2, 0)$; negative parabolic trough on $(-2, 2)$ dipping below the $x$-axis.

---

### Step 2: Piecewise Formulation of $f(x) = |x^2 - 4|$

Applying the definition of the absolute value:
$$
f(x) = \begin{cases} x^2 - 4, & \text{if } x^2 - 4 \ge 0 \iff x \in (-\infty, -2] \cup [2, \infty) \\ -(x^2 - 4) = 4 - x^2, & \text{if } x^2 - 4 < 0 \iff x \in (-2, 2) \end{cases}
$$

**Effect of the Absolute Value (Reflection):**
- For $|x| \ge 2$, $p(x) \ge 0$, so the curve is completely unchanged.
- For $|x| < 2$, $p(x) < 0$; the absolute value reflects the negative parabolic trough upward across the $x$-axis into the **downward-opening arch** $y = 4 - x^2$ with peak (local maximum) at $(0, 4)$.

---

### Step 3: Piecewise Derivative on Open Intervals

Differentiating each branch on the interior of its respective interval:
- For $|x| > 2$ (i.e., $x < -2$ or $x > 2$):
  $$
  f'(x) = \frac{d}{dx}[x^2 - 4] = 2x
  $$
- For $|x| < 2$ (i.e., $-2 < x < 2$):
  $$
  f'(x) = \frac{d}{dx}[4 - x^2] = -2x
  $$

Setting the derivative to zero on the open intervals:
- On $(-2, 2)$: $-2x = 0 \iff x = 0$.
  At $x = 0$, $f(0) = 4$. Since $f'(x) > 0$ for $x \in (-2, 0)$ and $f'(x) < 0$ for $x \in (0, 2)$, the point $(0, 4)$ is a **strict local maximum**.

---

### Step 4: Analytical Investigation of Non-Differentiability at $x = \pm 2$

We evaluate the one-sided limits of the difference quotient at the two boundary points $x = 2$ and $x = -2$.

#### 1. At $x = 2$:
Notice $f(2) = |2^2 - 4| = 0$.
- **Right-Hand Derivative ($h \to 0^+$, so $x = 2 + h > 2$):**
  $$
  f'_+(2) = \lim_{h \to 0^+} \frac{f(2 + h) - f(2)}{h} = \lim_{h \to 0^+} \frac{((2 + h)^2 - 4) - 0}{h} = \lim_{h \to 0^+} \frac{4h + h^2}{h} = \lim_{h \to 0^+} (4 + h) = +4
  $$
- **Left-Hand Derivative ($h \to 0^-$, so $x = 2 + h < 2$):**
  $$
  f'_-(2) = \lim_{h \to 0^-} \frac{f(2 + h) - f(2)}{h} = \lim_{h \to 0^-} \frac{(4 - (2 + h)^2) - 0}{h} = \lim_{h \to 0^-} \frac{-4h - h^2}{h} = \lim_{h \to 0^-} (-4 - h) = -4
  $$

Because:
$$
f'_-(2) = -4 \neq +4 = f'_+(2)
$$
The two-sided derivative $f'(2)$ **does not exist**.

#### 2. At $x = -2$:
Notice $f(-2) = |(-2)^2 - 4| = 0$.
- **Right-Hand Derivative ($h \to 0^+$, so $x = -2 + h > -2$, inside $(-2, 2)$):**
  $$
  f'_+(-2) = \lim_{h \to 0^+} \frac{4 - (-2 + h)^2}{h} = \lim_{h \to 0^+} \frac{4 - (4 - 4h + h^2)}{h} = \lim_{h \to 0^+} \frac{4h - h^2}{h} = +4
  $$
- **Left-Hand Derivative ($h \to 0^-$, so $x = -2 + h < -2$, inside $(-\infty, -2)$):**
  $$
  f'_-(-2) = \lim_{h \to 0^-} \frac{(-2 + h)^2 - 4}{h} = \lim_{h \to 0^-} \frac{4 - 4h + h^2 - 4}{h} = \lim_{h \to 0^-} (-4 + h) = -4
  $$

Because:
$$
f'_-(-2) = -4 \neq +4 = f'_+(-2)
$$
The two-sided derivative $f'(-2)$ **does not exist**.

---

### Step 5: Geometric Justification and Fermat's Theorem

1. **Geometric Reason for Non-Differentiability:**
   At $x = 2$, the left branch arrives with a steep downward slope $m = -4$, while the right branch departs with a steep upward slope $m = +4$.
   The graph forms a sharp corner at $(2, 0)$ and at $(-2, 0)$. At these corner points, the left-hand and right-hand limiting secant slopes are unequal ($f'_-(2) = -4$ and $f'_+(2) = +4$). Lines passing through the corner with intermediate slopes between $-4$ and $+4$ are supporting lines to the epigraph, not limiting secant lines or tangents; hence no two-sided tangent line exists.

2. **Connection to Fermat's Theorem:**
   - Because $f(x) = |x^2 - 4| \ge 0$ for all $x \in \mathbb{R}$, and $f(\pm 2) = 0$, the points $(-2, 0)$ and $(2, 0)$ are **absolute (global) minima** of $f(x)$.
   - However, at these absolute minima, the derivative is **strictly undefined** ($f'(\pm 2)$ does not exist, rather than being a nonzero value or zero).
   - This provides a stark warning: optimization cannot rely solely on solving $f'(x) = 0$. One must always check the singular points where $f'(x)$ fails to exist.

**ASCII Graph Sketch of $f(x) = |x^2 - 4|$:**
```text
                                  y
                                  ^
              5   \               |               /
              4    \              * (0, 4)       /
                    \           / | \           /
              3      \         /  |  \         /
              2       \       /   |   \       /
              1        \     /    |    \     /
   ---------------------*---'-----+-----`---*----------------------> x
                     (-2, 0)      | (0, 0) (2, 0)
                     Corner                Corner
                  [Global Min]          [Global Min]
```
*Labels:* Peak $(0, 4)$ on the $y$-axis ($x = 0$, local maximum); corners at $(-2, 0)$ and $(2, 0)$ on the $x$-axis (global minima where derivative is undefined); downward-opening arch on $(-2, 2)$; outer upward-opening branches on $(-\infty, -2]$ and $[2, \infty)$ continuously connected to the corners $\pm 2$.

---

## 4. Verification and Consistency Checks

1. **Parity (Even Function) Consistency:**
   $f(-x) = |(-x)^2 - 4| = |x^2 - 4| = f(x)$.
   The function is strictly even.
   The singular points $x = -2$ and $x = 2$ are symmetric reflections of each other, and their one-sided derivatives satisfy the odd-derivative relationship:
   $$
   f'_+(-2) = -f'_-(2) = +4, \qquad f'_-(-2) = -f'_+(2) = -4
   $$
   This confirms the calculations.

2. **Continuity at the Singular Points:**
   - $\lim_{x \to 2^-} f(x) = 4 - 2^2 = 0$.
   - $\lim_{x \to 2^+} f(x) = 2^2 - 4 = 0$.
   - $f(2) = 0$.
   Because the limits agree, $f(x)$ is continuous at $x = 2$. This proves that failure of differentiability is caused entirely by the slope discontinuity (corner), not by any jump or rupture in the graph.
