# Solution to Problem 4: A Function with Two Vertical Asymptotes

## 1. Problem Statement

Perform a complete analysis of the rational function:
$$
f(x) = \frac{1}{x^2 - 1}
$$

1. Determine the domain $\mathcal{D}_f$ and identify the parity (symmetry) of the function.
2. Determine all vertical and horizontal asymptotes using one-sided and infinite limits.
3. Determine the sign of $f(x)$ across the real axis.
4. Compute the derivative $f'(x)$, find all critical points, and determine the monotonicity on each interval of the domain.
5. Explain why each interval of the domain must be analyzed strictly separately and why monotonicity cannot be stated on unions of disjoint intervals.

---

## 2. Theoretical Background and Concepts

1. **Disconnected Domains:**
   When the denominator of a rational function has multiple zeros, the real line is partitioned into disjoint intervals:
   $$
   \mathcal{D}_f = I_1 \cup I_2 \cup \dots \cup I_k
   $$
   The **Mean Value Theorem** and the **Monotonicity Theorem** ($f' > 0 \implies f \text{ is increasing}$) apply strictly to **connected intervals**. They do not hold across unions of disconnected intervals.

2. **Parity (Even Function):**
   A function is even if $f(-x) = f(x)$ for all $x \in \mathcal{D}_f$. Its graph is symmetric with respect to the $y$-axis, and its derivative is an odd function: $f'(-x) = -f'(x)$.

3. **Behavior Near Vertical Asymptotes:**
   At a pole $x = c$, the sign of the one-sided limit $\lim_{x \to c^\pm} f(x) = \pm\infty$ depends on whether the denominator approaches zero through positive or negative values.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and Symmetry

1. **Domain:**
   Set the denominator to zero:
   $$
   x^2 - 1 = 0 \iff (x - 1)(x + 1) = 0 \iff x = -1 \quad \text{or} \quad x = 1
   $$
   Excluding these two singular points:
   $$
   \mathcal{D}_f = \mathbb{R} \setminus \{-1, 1\} = (-\infty, -1) \cup (-1, 1) \cup (1, \infty)
   $$

2. **Parity:**
   $$
   f(-x) = \frac{1}{(-x)^2 - 1} = \frac{1}{x^2 - 1} = f(x)
   $$
   The function is **strictly even**. The graph is symmetric with respect to the vertical line $x = 0$ ($y$-axis).

---

### Step 2: Asymptotes

1. **Vertical Asymptotes ($x = -1$ and $x = 1$):**
   - **Near $x = -1$:**
     - As $x \to -1^-$ ($x < -1$): $x^2 > 1 \implies x^2 - 1 \to 0^+$.
       $$
       \lim_{x \to -1^-} f(x) = \frac{1}{0^+} = +\infty
       $$
     - As $x \to -1^+$ ($-1 < x < 0$): $x^2 < 1 \implies x^2 - 1 \to 0^-$.
       $$
       \lim_{x \to -1^+} f(x) = \frac{1}{0^-} = -\infty
       $$
   - **Near $x = 1$ (by even symmetry):**
     - As $x \to 1^-$ ($0 < x < 1$): $x^2 < 1 \implies x^2 - 1 \to 0^-$.
       $$
       \lim_{x \to 1^-} f(x) = \frac{1}{0^-} = -\infty
       $$
     - As $x \to 1^+$ ($x > 1$): $x^2 > 1 \implies x^2 - 1 \to 0^+$.
       $$
       \lim_{x \to 1^+} f(x) = \frac{1}{0^+} = +\infty
       $$
   The lines **$x = -1$** and **$x = 1$** are two vertical asymptotes.

2. **Horizontal Asymptote:**
   As $x \to \pm\infty$:
   $$
   \lim_{x \to \pm\infty} \frac{1}{x^2 - 1} = 0
   $$
   The horizontal line **$y = 0$** (the $x$-axis) is a horizontal asymptote as $x \to \pm\infty$.

---

### Step 3: Sign of the Function and Intercepts

- **Zeros:** The numerator is constant $1 \neq 0$, so $f(x)$ has **no zeros** (the graph never touches or crosses the $x$-axis).
- **$y$-intercept:** Setting $x = 0$:
  $$
  f(0) = \frac{1}{0^2 - 1} = -1 \implies (0, -1)
  $$
- **Sign on the Three Disjoint Intervals:**
  - On $(-\infty, -1)$: $x^2 - 1 > 0 \implies \mathbf{f(x) > 0}$ (positive branch above the $x$-axis).
  - On $(-1, 1)$: $x^2 - 1 < 0 \implies \mathbf{f(x) < 0}$ (negative branch below the $x$-axis).
  - On $(1, \infty)$: $x^2 - 1 > 0 \implies \mathbf{f(x) > 0}$ (positive branch above the $x$-axis).

---

### Step 4: Derivative, Monotonicity, and Local Extrema

1. **Compute $f'(x)$:**
   Using the chain rule on $f(x) = (x^2 - 1)^{-1}$:
   $$
   f'(x) = -1(x^2 - 1)^{-2} \cdot \frac{d}{dx}[x^2 - 1] = -\frac{2x}{(x^2 - 1)^2}
   $$

2. **Critical Points:**
   Set $f'(x) = 0$:
   $$
   -\frac{2x}{(x^2 - 1)^2} = 0 \implies -2x = 0 \implies x = 0
   $$
   $x = 0 \in \mathcal{D}_f$ is the only critical point.

3. **Sign of $f'(x)$ and Monotonicity on Each Interval:**
   The denominator $(x^2 - 1)^2 > 0$ for all $x \in \mathcal{D}_f$. Therefore, the sign of $f'(x)$ is determined solely by $-2x$:

   | Interval | Sign of $-2x$ | Sign of $f'(x)$ | Monotonicity of $f(x)$ |
   |:---|:---:|:---:|:---|
   | **$(-\infty, -1)$** | $+$ | $+$ | **Strictly increasing** |
   | **$(-1, 0)$** | $+$ | $+$ | **Strictly increasing** |
   | **$x = 0$** | $0$ | $0$ | **Strict Local Maximum: $(0, -1)$** |
   | **$(0, 1)$** | $-$ | $-$ | **Strictly decreasing** |
   | **$(1, \infty)$** | $-$ | $-$ | **Strictly decreasing** |

4. **Characterization of Extrema:**
   - At $x = 0$, $f'(x)$ changes sign from positive to negative, confirming that $(0, -1)$ is a **strict local maximum**.
   - On the middle branch $(-1, 1)$, $f(x) \le -1$ everywhere.
   - On the outer branches, $f(x) > 0$, so $(0, -1)$ is a local maximum, but not an absolute maximum.

---

### Step 5: Why Each Interval Must Be Analyzed Separately

1. **The Fallacy of Unionizing Monotonicity:**
   Notice that $f'(x) > 0$ on both $(-\infty, -1)$ and $(-1, 0)$.
   A common student blunder is to assert: *"The function is increasing on $(-\infty, -1) \cup (-1, 0)$."*
   This statement is **mathematically false**.
   - Consider $x_1 = -2 \in (-\infty, -1)$ and $x_2 = -0.5 \in (-1, 0)$.
   - Here $x_1 < x_2$, yet:
     $$
     f(x_1) = f(-2) = \frac{1}{(-2)^2 - 1} = \frac{1}{3} > 0
     $$
     $$
     f(x_2) = f(-0.5) = \frac{1}{(-0.5)^2 - 1} = -\frac{4}{3} < 0
     $$
   - We have $x_1 < x_2$ but $f(x_1) > f(x_2)$! The function has violently dropped from $+1/3$ to $-4/3$.

2. **Mathematical Cause:**
   The Monotonicity Theorem states:
   $$
   f'(x) \ge 0 \quad \forall x \in I \implies f \text{ is non-decreasing on } I
   $$
   The theorem relies directly on the **Mean Value Theorem**: $f(b) - f(a) = f'(\xi)(b - a)$, which requires $f$ to be continuous on the entire closed interval $[a, b]$.
   Because $x = -1 \notin \mathcal{D}_f$, any interval containing both $x_1$ and $x_2$ crosses the discontinuity at $-1$, breaking the hypothesis of the Mean Value Theorem.
   Therefore, monotonicity statements must be strictly confined to individual, connected intervals of definition.

---

## 4. Verification and Consistency Checks

1. **Second Derivative and Convexity:**
   $$
   f''(x) = \frac{d}{dx}\left[\frac{-2x}{(x^2 - 1)^2}\right] = \frac{-2(x^2 - 1)^2 - (-2x) \cdot 2(x^2 - 1)(2x)}{(x^2 - 1)^4}
   $$
   Divide numerator and denominator by $(x^2 - 1)$:
   $$
   f''(x) = \frac{-2(x^2 - 1) + 8x^2}{(x^2 - 1)^3} = \frac{6x^2 + 2}{(x^2 - 1)^3} = \frac{2(3x^2 + 1)}{(x^2 - 1)^3}
   $$
   - Since $2(3x^2 + 1) > 0$ for all $x$, the sign of $f''(x)$ is determined entirely by $(x^2 - 1)^3$:
     - On $(-\infty, -1)$: $x^2 - 1 > 0 \implies f''(x) > 0$ (concave upward $\cup$).
     - On $(-1, 1)$: $x^2 - 1 < 0 \implies f''(x) < 0$ (concave downward $\cap$).
     - On $(1, \infty)$: $x^2 - 1 > 0 \implies f''(x) > 0$ (concave upward $\cup$).
   - At $x = 0$: $f''(0) = \frac{2(1)}{(-1)^3} = -2 < 0$, independently confirming that $(0, -1)$ is a strict local maximum.

2. **ASCII Visual Profile:**
```text
                 :             y             :
      x = -1     :             ^             :     x = 1
   (Asymptote)   :             |             :  (Asymptote)
        |        :             |             :       |
        |        :             |             :       |
         \       :             |             :      /
          \      :             |             :     /
           ------:             |             :-----    (Outer branches > 0, y -> 0+)
   --------------:-------------+-------------:-----------------> x (Horizontal Asymptote y = 0)
                 :             | (0, 0)      :
                 :             |             :
                 :          (0, -1)          :
                 :             * [Local Max] :
                 :           / | \           :
                 :          /  |  \          :
                 :         |   |   |         :
                 :         v   |   v         : (Middle branch: plunges to -inf)
```
*Labels:* Vertical asymptote $x = -1$ strictly to the left of the $y$-axis; vertical asymptote $x = 1$ strictly to the right of the $y$-axis; both outer branches ($x < -1$ and $x > 1$) stay strictly positive ($y > 0$) and never touch or cross the $x$-axis; middle branch ($-1 < x < 1$) stays strictly at or below $-1$ ($y \le -1$), peaking at the strict local maximum $(0, -1)$ on the $y$-axis and plunging toward $-\infty$ at both asymptotes.
