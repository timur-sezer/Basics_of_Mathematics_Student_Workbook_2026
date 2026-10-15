# Solution to Problem 8: The Second Derivative

## 1. Problem Statement

Perform a complete curvature and monotonicity analysis of the quartic polynomial:
$$
f(x) = x^4 - 4x^2
$$

1. Determine the domain, symmetry (parity), and $x$- and $y$-intercepts.
2. Compute the first derivative $f'(x)$ and determine all critical points, intervals of monotonicity, and local/global extrema.
3. Compute the second derivative $f''(x)$, determine the intervals of convexity and concavity, and find the exact coordinates of all inflection points.
4. Provide an ASCII sketch of the graph clearly marking the local extrema, inflection points, and zeros.

---

## 2. Theoretical Background and Concepts

1. **Parity and Quartic Polynomials:**
   If a polynomial contains only even powers of $x$, it is an **even function** ($f(-x) = f(x)$), exhibiting reflective symmetry across the $y$-axis.

2. **The Second Derivative as Geometric Curvature:**
   While the first derivative $f'(x)$ gives the slope of the tangent line, the second derivative $f''(x)$ measures how that slope changes:
   - **$f''(x) > 0$:** The slope is increasing. The curve lies above its tangent lines and holds water: **concave upward (convex)** ($\cup$).
   - **$f''(x) < 0$:** The slope is decreasing. The curve lies below its tangent lines: **concave downward (concave)** ($\cap$).

3. **Inflection Points:**
   An inflection point is a point on the curve where the concavity strictly changes sign (from upward to downward or vice versa). For twice continuously differentiable functions, candidates satisfy:
   $$
   f''(x) = 0
   $$
   with an actual sign change of $f''(x)$ across the point.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain, Parity, and Intercepts

1. **Domain:**
   $$
   \mathcal{D}_f = \mathbb{R}
   $$

2. **Parity (Symmetry):**
   $$
   f(-x) = (-x)^4 - 4(-x)^2 = x^4 - 4x^2 = f(x)
   $$
   The function is **strictly even**, symmetric with respect to the $y$-axis.

3. **Intercepts (Zeros):**
   Set $f(x) = 0$:
   $$
   x^4 - 4x^2 = 0 \iff x^2(x^2 - 4) = 0 \iff x^2(x - 2)(x + 2) = 0
   $$
   - $x = 0$ is a root of **multiplicity 2** (the graph touches the $x$-axis without crossing).
   - $x = -2$ and $x = +2$ are simple roots (the graph crosses the $x$-axis).
   The three intercepts are $(-2, 0)$, $(0, 0)$, and $(2, 0)$.

---

### Step 2: First Derivative, Monotonicity, and Local Extrema

1. **Compute $f'(x)$:**
   $$
   f'(x) = 4x^3 - 8x = 4x(x^2 - 2) = 4x(x - \sqrt{2})(x + \sqrt{2})
   $$

2. **Critical Points:**
   Set $f'(x) = 0$:
   $$
   x_1 = -\sqrt{2} \approx -1.414, \qquad x_2 = 0, \qquad x_3 = +\sqrt{2} \approx +1.414
   $$

3. **Sign Chart of $f'(x)$:**
   - **$(-\infty, -\sqrt{2})$:** $f'(-2) = 4(-2)(4 - 2) = -16 < 0 \implies \mathbf{f}$ is strictly decreasing.
   - **$(-\sqrt{2}, 0)$:** $f'(-1) = 4(-1)(1 - 2) = +4 > 0 \implies \mathbf{f}$ is strictly increasing.
   - **$(0, \sqrt{2})$:** $f'(1) = 4(1)(1 - 2) = -4 < 0 \implies \mathbf{f}$ is strictly decreasing.
   - **$(\sqrt{2}, \infty)$:** $f'(2) = 4(2)(4 - 2) = +16 > 0 \implies \mathbf{f}$ is strictly increasing.

4. **Coordinates and Character of Extrema:**
   - **At $x = -\sqrt{2}$:** Transition from $-$ to $+$ $\implies$ **strict global minimum**:
     $$
     f(-\sqrt{2}) = (-\sqrt{2})^4 - 4(-\sqrt{2})^2 = 4 - 8 = -4 \implies \mathbf{m_1(-\sqrt{2}, -4)}
     $$
   - **At $x = 0$:** Transition from $+$ to $-$ $\implies$ **strict local maximum**:
     $$
     f(0) = 0^4 - 4(0)^2 = 0 \implies \mathbf{M(0, 0)}
     $$
   - **At $x = +\sqrt{2}$:** Transition from $-$ to $+$ $\implies$ **strict global minimum**:
     $$
     f(\sqrt{2}) = (\sqrt{2})^4 - 4(\sqrt{2})^2 = 4 - 8 = -4 \implies \mathbf{m_2(\sqrt{2}, -4)}
     $$

---

### Step 3: Second Derivative, Convexity, and Inflection Points

1. **Compute $f''(x)$:**
   $$
   f''(x) = \frac{d}{dx}[4x^3 - 8x] = 12x^2 - 8 = 12\left(x^2 - \frac{2}{3}\right)
   $$

2. **Zeros of $f''(x)$:**
   $$
   12x^2 - 8 = 0 \iff x^2 = \frac{8}{12} = \frac{2}{3} \implies x = \pm\sqrt{\frac{2}{3}} = \pm\frac{\sqrt{6}}{3} \approx \pm 0.8165
   $$

3. **Intervals of Convexity and Concavity:**
   - **$\left(-\infty, -\sqrt{\frac{2}{3}}\right)$:** $x^2 > \frac{2}{3} \implies f''(x) > 0 \implies$ **concave upward** ($\cup$).
   - **$\left(-\sqrt{\frac{2}{3}}, \sqrt{\frac{2}{3}}\right)$:** $x^2 < \frac{2}{3} \implies f''(x) < 0 \implies$ **concave downward** ($\cap$).
   - **$\left(\sqrt{\frac{2}{3}}, \infty\right)$:** $x^2 > \frac{2}{3} \implies f''(x) > 0 \implies$ **concave upward** ($\cup$).

4. **Coordinates of Inflection Points:**
   Evaluate $f(x)$ at $x = \pm\sqrt{2/3}$:
   $$
   y_{\text{inf}} = \left(\sqrt{\frac{2}{3}}\right)^4 - 4\left(\sqrt{\frac{2}{3}}\right)^2 = \left(\frac{2}{3}\right)^2 - 4\left(\frac{2}{3}\right) = \frac{4}{9} - \frac{8}{3} = \frac{4 - 24}{9} = -\frac{20}{9} \approx -2.222
   $$
   The two symmetric inflection points are:
   $$
   \mathbf{I_1\left(-\sqrt{\frac{2}{3}}, -\frac{20}{9}\right)}, \qquad \mathbf{I_2\left(\sqrt{\frac{2}{3}}, -\frac{20}{9}\right)}
   $$

---

### Step 4: Graphical Sketch of the "W-Curve"

```text
            y
            ^
        2   |   *                               *
        1   |    *                             *
   -----+----+----+-------------*-------------+----+----> x
       -2   |      *         (0, 0) M        *     2
            |       *       *       *       *
       -1   |        *     *         *     *
       -2 --+---------*---*-----------*---*---- y = -20/9 (Inflection line)
            |       I1 * *             * * I2
       -3   |           *               *
       -4 --+------------*-------------*------- y = -4 (Global Minimum)
            |      m1(-√2, -4)     m2(√2, -4)
```

The curve exhibits the characteristic "W" profile of a double-well potential:
- Starts at $+\infty$ for $x \to -\infty$, passes through $(-2, 0)$.
- Reaches first global minimum at $(-\sqrt{2}, -4)$.
- Reverses curvature at inflection point $I_1(-\sqrt{2/3}, -20/9)$.
- Peaks at local maximum $(0, 0)$ where it touches the $x$-axis.
- Reverses curvature at inflection point $I_2(\sqrt{2/3}, -20/9)$.
- Reaches second global minimum at $(\sqrt{2}, -4)$.
- Passes through $(2, 0)$ and climbs to $+\infty$ as $x \to +\infty$.

---

## 4. Verification and Consistency Checks

1. **Second Derivative Test on Critical Points:**
   - At $x = -\sqrt{2}$: $f''(-\sqrt{2}) = 12(2) - 8 = +16 > 0 \implies$ strict local minimum ($\checkmark$).
   - At $x = 0$: $f''(0) = 12(0) - 8 = -8 < 0 \implies$ strict local maximum ($\checkmark$).
   - At $x = +\sqrt{2}$: $f''(\sqrt{2}) = 12(2) - 8 = +16 > 0 \implies$ strict local minimum ($\checkmark$).

2. **Algebraic Absolute Minimum Check:**
   Complete the square in terms of $u = x^2 \ge 0$:
   $$
   f(x) = (x^2)^2 - 4(x^2) = (x^2 - 2)^2 - 4
   $$
   Since $(x^2 - 2)^2 \ge 0$ for all real $x$, with minimum value $0$ attained precisely when $x^2 = 2 \iff x = \pm\sqrt{2}$:
   $$
   f(x) \ge -4 \quad \forall x \in \mathbb{R}
   $$
   This proves beyond doubt that $-4$ is the true global minimum.
