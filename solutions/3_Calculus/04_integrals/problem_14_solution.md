# Solution to Problem 14: A Piecewise-Defined Function

## 1. Problem Statement

Given the piecewise-defined function on $[-1, 3]$:
$$
f(x) = \begin{cases} x + 1, & -1 \le x < 1 \\ 2, & 1 \le x \le 3 \end{cases}
$$

1. Analyze the continuity of the function at the boundary point $x = 1$.
2. Sketch the graph of the function on $[-1, 3]$.
3. Apply the interval additivity property of definite integrals to split the integral across the piecewise sub-domains.
4. Compute the exact value of:
   $$
   \int_{-1}^{3} f(x) \, dx
   $$
5. Verify the computed integral value using elementary Euclidean geometry (areas of basic geometric figures).

---

## 2. Theoretical Background and Concepts

1. **Interval Additivity of Definite Integrals:**
   If a function $f(x)$ is integrable on $[a, b]$, and $c \in (a, b)$, then:
   $$
   \int_a^b f(x) \, dx = \int_a^c f(x) \, dx + \int_c^b f(x) \, dx
   $$
   This property allows any integral of a piecewise-defined function to be split at its definition boundaries into standard, single-formula integrals.

2. **Continuity at Piecewise Junctions:**
   A piecewise function defined on adjacent intervals $[a, c)$ and $[c, b]$ is continuous at $c$ if:
   $$
   \lim_{x \to c^-} f(x) = \lim_{x \to c^+} f(x) = f(c)
   $$
   If this holds, the graph joins seamlessly without a jump or gap.

3. **Geometric Interpretation of Definite Integrals:**
   For a non-negative function $f(x) \ge 0$, the definite integral $\int_a^b f(x) \, dx$ equals the physical area under the curve. When the graph consists of line segments, the area can be computed independently using standard geometric formulas for triangles, rectangles, and trapezoids.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Continuity Analysis at the Transition Point $x = 1$

1. **Left-Hand Limit ($x \to 1^-$):**
   Using the first branch $f(x) = x + 1$:
   $$
   \lim_{x \to 1^-} f(x) = \lim_{x \to 1^-} (x + 1) = 1 + 1 = 2
   $$

2. **Right-Hand Limit and Function Value at $x = 1$:**
   Using the second branch $f(x) = 2$:
   $$
   \lim_{x \to 1^+} f(x) = \lim_{x \to 1^+} (2) = 2, \qquad f(1) = 2
   $$

3. **Conclusion:**
   $$
   \lim_{x \to 1^-} f(x) = \lim_{x \to 1^+} f(x) = f(1) = 2
   $$
   The function is **continuous at $x = 1$** (and everywhere on $[-1, 3]$). The linear segment connects continuously with the horizontal segment at the point $(1, 2)$.

---

### Step 2: Graph Sketch of $f(x)$ on $[-1, 3]$

- **Branch 1 (Linear on $[-1, 1]$):** Straight line segment from $(-1, 0)$ to $(1, 2)$.
- **Branch 2 (Constant on $[1, 3]$):** Horizontal plateau at height $y = 2$ from $(1, 2)$ to $(3, 2)$.

```text
                            y
                            ^
         2                  |         *-------------------* (3, 2)
                            |    /    | (1, 2)            |
         1           (0, 1) *         |                   |
                       /    |         |                   |
   ---------------*---------+---------+-------------------+-----------> x
               (-1, 0)      0         1                   3
                  |<------- base 2 ------>|<---------------- base 2 --------------->|
                       Triangle                  Rectangle
                       Area = 2                  Area = 4
```
*Labels:* Vertical axis is located at $x = 0$, passing through $(0, 1)$ on the curve and meeting the $x$-axis at $(0, 0)$; linear branch begins at $(-1, 0)$ strictly to the left of the $y$-axis, passes continuously through $(0, 1)$ on the $y$-axis, and reaches $(1, 2)$; constant horizontal plateau extends from $(1, 2)$ to $(3, 2)$ at uniform height $2$; triangle on $[-1, 1]$ has base $2$ and height $2$ (Area $= 2$); rectangle on $[1, 3]$ has base $2$ and height $2$ (Area $= 4$).

---

### Step 3: Splitting the Integral

By the additivity property of definite integrals, split at the junction point $x = 1$:
$$
\int_{-1}^3 f(x) \, dx = \int_{-1}^1 f(x) \, dx + \int_1^3 f(x) \, dx
$$

Substitute the specific branch formulas into each integral:
$$
\int_{-1}^3 f(x) \, dx = \int_{-1}^1 (x + 1) \, dx + \int_1^3 2 \, dx
$$

---

### Step 4: Analytical Evaluation of Both Integrals

1. **Evaluate the First Integral ($I_1 = \int_{-1}^1 (x + 1) \, dx$):**
   $$
   \int_{-1}^1 (x + 1) \, dx = \left[\frac{x^2}{2} + x\right]_{-1}^1
   $$
   Evaluate at upper limit $x = 1$:
   $$
   F_1(1) = \frac{1^2}{2} + 1 = \frac{1}{2} + 1 = \frac{3}{2}
   $$
   Evaluate at lower limit $x = -1$:
   $$
   F_1(-1) = \frac{(-1)^2}{2} + (-1) = \frac{1}{2} - 1 = -\frac{1}{2}
   $$
   Compute the difference:
   $$
   I_1 = \frac{3}{2} - \left(-\frac{1}{2}\right) = \frac{3}{2} + \frac{1}{2} = 2
   $$

2. **Evaluate the Second Integral ($I_2 = \int_1^3 2 \, dx$):**
   $$
   \int_1^3 2 \, dx = \Big[2x\Big]_1^3 = 2(3) - 2(1) = 6 - 2 = 4
   $$

3. **Sum the Results:**
   $$
   \int_{-1}^3 f(x) \, dx = I_1 + I_2 = 2 + 4 = 6
   $$

The exact value of the integral is:
$$
\mathbf{\int_{-1}^3 f(x) \, dx = 6}
$$

---

### Step 5: Geometric Verification

Because $f(x) \ge 0$ everywhere on $[-1, 3]$, the integral equals the exact total geometric area under the curve.

1. **Area under the first branch (Triangle $T_1$ on $[-1, 1]$):**
   - The region under $y = x + 1$ between $x = -1$ and $x = 1$ is a right triangle with vertices $(-1, 0)$, $(1, 0)$, and $(1, 2)$.
   - Base: $b_1 = 1 - (-1) = 2$
   - Height: $h_1 = 2 - 0 = 2$
   - Area:
     $$
     \text{Area}(T_1) = \frac{1}{2} \cdot b_1 \cdot h_1 = \frac{1}{2}(2)(2) = 2
     $$
   This matches $I_1 = 2$.

2. **Area under the second branch (Rectangle $R_2$ on $[1, 3]$):**
   - The region under $y = 2$ between $x = 1$ and $x = 3$ is a rectangle with vertices $(1, 0)$, $(3, 0)$, $(3, 2)$, and $(1, 2)$.
   - Width: $w_2 = 3 - 1 = 2$
   - Height: $h_2 = 2$
   - Area:
     $$
     \text{Area}(R_2) = w_2 \cdot h_2 = 2 \cdot 2 = 4
     $$
   This matches $I_2 = 4$.

3. **Total Area:**
   $$
   \text{Total Area} = \text{Area}(T_1) + \text{Area}(R_2) = 2 + 4 = 6
   $$

The geometric area of $6$ verifies the analytical result.

---

## 4. Verification and Consistency Checks

1. **Trapezoidal Sub-Check on $[-1, 1]$:**
   Split $[-1, 1]$ into a triangle on $[-1, 0]$ and a trapezoid on $[0, 1]$:
   - Triangle on $[-1, 0]$: Base $= 1$, Height $= 1 \implies \text{Area} = 0.5$.
   - Trapezoid on $[0, 1]$: Base $= 1$, Left height $= 1$, Right height $= 2 \implies \text{Area} = \frac{1 + 2}{2} \times 1 = 1.5$.
   - Sum on $[-1, 1]$: $0.5 + 1.5 = 2.0$.
   This confirms $I_1 = 2$.

2. **Average Value of the Function:**
   $$
   \bar{f} = \frac{1}{3 - (-1)} \int_{-1}^3 f(x) \, dx = \frac{1}{4} \times 6 = 1.5
   $$
   Because the function rises from $0$ to $2$ and then stays at $2$ across equal interval widths of $2$, the mean value is:
   $$
   \bar{f} = \frac{\bar{f}_{[ -1, 1]} + \bar{f}_{[1, 3]}}{2} = \frac{1.0 + 2.0}{2} = 1.5
   $$
   This confirms the integral calculation.
