# Solution to Problem 10: Complete Function Analysis

## 1. Problem Statement

Perform a comprehensive, systematic function analysis of:
$$
f(x) = \frac{x}{x^2 + 1}
$$

The complete analysis must include:
1. Maximal domain of definition $\mathcal{D}_f$.
2. Symmetry and parity (even/odd).
3. Intercepts with the coordinate axes.
4. Limits at infinity and all asymptotes.
5. First derivative $f'(x)$, critical points, intervals of monotonicity, and local/global extrema.
6. Second derivative $f''(x)$, intervals of convexity/concavity, and points of inflection.
7. Summary table of variation and an ASCII sketch based entirely on the analytical findings.

---

## 2. Theoretical Background and Concepts

1. **Complete Function Analysis Workflow:**
   A complete curve sketching protocol follows an organized sequence:
   $$\text{Domain} \to \text{Symmetry} \to \text{Intercepts} \to \text{Limits/Asymptotes} \to \text{Monotonicity/Extrema} \to \text{Curvature/Inflection} \to \text{Synthesis}$$

2. **Parity (Odd Function):**
   A function is odd if $f(-x) = -f(x)$ for all $x \in \mathcal{D}_f$. The graph has point symmetry with respect to the origin $(0, 0)$. Any extremum or inflection point at $(x_0, y_0)$ has an exact symmetric counterpart at $(-x_0, -y_0)$.

3. **Cauchy-Schwarz / AM-GM Bound for $f(x) = \frac{x}{x^2 + 1}$:**
   By the AM-GM inequality, for all $x \neq 0$:
   $$
   x^2 + 1 \ge 2\sqrt{x^2 \cdot 1} = 2|x| \implies \left|\frac{x}{x^2 + 1}\right| \le \frac{|x|}{2|x|} = \frac{1}{2}
   $$
   This proves purely algebraically that $-0.5 \le f(x) \le 0.5$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain of Definition

The denominator is $x^2 + 1$.
Since $x^2 \ge 0$ for all real numbers $x \in \mathbb{R}$:
$$
x^2 + 1 \ge 1 > 0 \quad \forall x \in \mathbb{R}
$$
The denominator never equals zero. Therefore, there are no domain restrictions:
$$
\mathcal{D}_f = \mathbb{R} = (-\infty, \infty)
$$

---

### Step 2: Symmetry (Parity)

Test $f(-x)$:
$$
f(-x) = \frac{-x}{(-x)^2 + 1} = -\frac{x}{x^2 + 1} = -f(x)
$$
Because $f(-x) = -f(x)$, the function is **strictly odd**.
Its graph is point-symmetric with respect to the origin $(0, 0)$.

---

### Step 3: Intercepts with the Coordinate Axes

1. **$x$-intercept (Zeros):**
   $$
   \frac{x}{x^2 + 1} = 0 \iff x = 0
   $$
2. **$y$-intercept:**
   $$
   f(0) = \frac{0}{0^2 + 1} = 0
   $$
The origin **$(0, 0)$** is the unique intersection point with both coordinate axes.

---

### Step 4: Limits and Asymptotes

1. **Vertical Asymptotes:**
   None, because the function is continuous on all of $\mathbb{R}$.

2. **Horizontal Asymptote:**
   Divide numerator and denominator by $x^2$:
   $$
   \lim_{x \to \pm\infty} \frac{x}{x^2 + 1} = \lim_{x \to \pm\infty} \frac{\frac{1}{x}}{1 + \frac{1}{x^2}} = \frac{0}{1 + 0} = 0
   $$
   The line **$y = 0$** (the $x$-axis) is a horizontal asymptote as both $x \to +\infty$ and $x \to -\infty$.

3. **Oblique Asymptotes:**
   None, because the horizontal asymptote governs the end-behavior.

---

### Step 5: First Derivative, Monotonicity, and Extrema

1. **Compute $f'(x)$ using the Quotient Rule:**
   $$
   f'(x) = \frac{\frac{d}{dx}[x](x^2 + 1) - x \frac{d}{dx}[x^2 + 1]}{(x^2 + 1)^2} = \frac{(1)(x^2 + 1) - x(2x)}{(x^2 + 1)^2} = \frac{x^2 + 1 - 2x^2}{(x^2 + 1)^2}
   $$
   $$
   f'(x) = \frac{1 - x^2}{(x^2 + 1)^2} = \frac{(1 - x)(1 + x)}{(x^2 + 1)^2}
   $$

2. **Critical Points:**
   Set $f'(x) = 0$:
   $$
   1 - x^2 = 0 \iff x = -1 \quad \text{or} \quad x = 1
   $$

3. **Sign Chart and Monotonicity:**
   Because $(x^2 + 1)^2 > 0$ everywhere, the sign of $f'(x)$ is given by $1 - x^2$:
   - **On $(-\infty, -1)$:** $x^2 > 1 \implies f'(x) < 0 \implies f$ is **strictly decreasing**.
   - **On $(-1, 1)$:** $x^2 < 1 \implies f'(x) > 0 \implies f$ is **strictly increasing**.
   - **On $(1, \infty)$:** $x^2 > 1 \implies f'(x) < 0 \implies f$ is **strictly decreasing**.

4. **Classification and Coordinates of Extrema:**
   - **At $x = -1$:** $f'(x)$ changes from $-$ to $+$ $\implies$ **strict global minimum**:
     $$
     y_{\min} = f(-1) = \frac{-1}{(-1)^2 + 1} = -\frac{1}{2} = -0.5 \implies \mathbf{m\left(-1, -\frac{1}{2}\right)}
     $$
   - **At $x = 1$:** $f'(x)$ changes from $+$ to $-$ $\implies$ **strict global maximum**:
     $$
     y_{\max} = f(1) = \frac{1}{1^2 + 1} = \frac{1}{2} = 0.5 \implies \mathbf{M\left(1, \frac{1}{2}\right)}
     $$
   - The range of the function is:
     $$
     \mathcal{R}_f = \left[-\frac{1}{2}, \frac{1}{2}\right]
     $$

---

### Step 6: Second Derivative, Concavity, and Inflection Points

1. **Compute $f''(x)$:**
   Differentiate $f'(x) = \frac{1 - x^2}{(x^2 + 1)^2}$ using the quotient rule:
   $$
   f''(x) = \frac{(-2x)(x^2 + 1)^2 - (1 - x^2) \cdot 2(x^2 + 1)(2x)}{(x^2 + 1)^4}
   $$
   Cancel $(x^2 + 1)$ from numerator and denominator:
   $$
   f''(x) = \frac{-2x(x^2 + 1) - 4x(1 - x^2)}{(x^2 + 1)^3} = \frac{-2x^3 - 2x - 4x + 4x^3}{(x^2 + 1)^3} = \frac{2x^3 - 6x}{(x^2 + 1)^3}
   $$
   Factor out $2x$:
   $$
   f''(x) = \frac{2x(x^2 - 3)}{(x^2 + 1)^3}
   $$

2. **Zeros of $f''(x)$:**
   $$
   2x(x^2 - 3) = 0 \implies x_1 = -\sqrt{3}, \quad x_2 = 0, \quad x_3 = +\sqrt{3}
   $$

3. **Intervals of Convexity and Concavity:**
   - On $(-\infty, -\sqrt{3})$: $x < 0$ and $x^2 - 3 > 0 \implies f''(x) < 0 \implies$ **concave downward** ($\cap$).
   - On $(-\sqrt{3}, 0)$: $x < 0$ and $x^2 - 3 < 0 \implies f''(x) > 0 \implies$ **concave upward** ($\cup$).
   - On $(0, \sqrt{3})$: $x > 0$ and $x^2 - 3 < 0 \implies f''(x) < 0 \implies$ **concave downward** ($\cap$).
   - On $(\sqrt{3}, \infty)$: $x > 0$ and $x^2 - 3 > 0 \implies f''(x) > 0 \implies$ **concave upward** ($\cup$).

4. **Coordinates of Inflection Points:**
   - At $x = -\sqrt{3}$: $f(-\sqrt{3}) = \frac{-\sqrt{3}}{(-\sqrt{3})^2 + 1} = -\frac{\sqrt{3}}{4} \approx -0.433 \implies \mathbf{I_1\left(-\sqrt{3}, -\frac{\sqrt{3}}{4}\right)}$.
   - At $x = 0$: $f(0) = 0 \implies \mathbf{I_2(0, 0)}$.
   - At $x = +\sqrt{3}$: $f(\sqrt{3}) = \frac{\sqrt{3}}{(\sqrt{3})^2 + 1} = \frac{\sqrt{3}}{4} \approx +0.433 \implies \mathbf{I_3\left(\sqrt{3}, \frac{\sqrt{3}}{4}\right)}$.

---

### Step 7: Summary Table of Variation and Graphical Sketch

| $x$ | $-\infty$ | $\dots$ | $-\sqrt{3}$ | $\dots$ | $-1$ | $\dots$ | $0$ | $\dots$ | $1$ | $\dots$ | $\sqrt{3}$ | $\dots$ | $+\infty$ |
|:---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **$f'(x)$** | $0$ | $-$ | $-$ | $-$ | $0$ | $+$ | $+$ | $+$ | $0$ | $-$ | $-$ | $-$ | $0$ |
| **$f''(x)$** | $0$ | $-$ | $0$ | $+$ | $+$ | $+$ | $0$ | $-$ | $-$ | $-$ | $0$ | $+$ | $0$ |
| **$f(x)$** | $0$ | $\searrow \cap$ | $-\frac{\sqrt{3}}{4}$ | $\searrow \cup$ | **Min $-\frac{1}{2}$** | $\nearrow \cup$ | **Inf $0$** | $\nearrow \cap$ | **Max $+\frac{1}{2}$** | $\searrow \cap$ | $+\frac{\sqrt{3}}{4}$ | $\searrow \cup$ | $0$ |

**ASCII Graph Sketch:**
```text
           y
           ^
    0.5    |                     * M(1, 0.5)
           |                   *   *
    0.25   |                 *       * I3(√3 ≈ 1.73, 0.433)
           |                *          *  *  *  *  *  *  *  * (y = 0)
   --------+---------------*-----------------------------------> x
   -4  -3  | -2   -1      0 (0, 0) I2       2     3     4
 (y = 0)   |*  *  *  *
   -0.25   |            *
           |           *   *
   -0.5    |             * m(-1, -0.5)
```

---

## 4. Verification and Consistency Checks

1. **Second Derivative Test on Critical Points:**
   - At $x = -1$: $f''(-1) = \frac{2(-1)((-1)^2 - 3)}{((-1)^2 + 1)^3} = \frac{-2(-2)}{2^3} = \frac{4}{8} = +0.5 > 0 \implies$ strict minimum ($\checkmark$).
   - At $x = 1$: $f''(1) = \frac{2(1)(1^2 - 3)}{(1^2 + 1)^3} = \frac{2(-2)}{2^3} = -\frac{4}{8} = -0.5 < 0 \implies$ strict maximum ($\checkmark$).

2. **Slope at the Origin:**
   $$
   f'(0) = \frac{1 - 0^2}{(0^2 + 1)^2} = \frac{1}{1} = 1
   $$
   At the origin $(0, 0)$, the inflection tangent is the line $y = x$ (slope $45^\circ$).
   For very small $x$, $\frac{x}{x^2 + 1} \approx x(1 - x^2) \approx x$.
   This confirms that the curve crosses the origin smoothly at slope $1$.
