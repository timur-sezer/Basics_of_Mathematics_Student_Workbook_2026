# Solution to Problem 14: Continuity and Differentiability of a Piecewise Function

## 1. Problem Statement

Investigate the behavior at the junction point $x = 0$ of the piecewise-defined function:
$$
f(x) = \begin{cases} x^2, & x \ge 0 \\ ax, & x < 0 \end{cases}
$$
where $a \in \mathbb{R}$ is a real parameter.

1. Determine the values of $a$ for which the function is continuous at $x = 0$.
2. Compute the right-hand and left-hand derivatives at $x = 0$, and determine for which values of $a$ they exist and agree.
3. Determine for which value(s) of $a$ the function is differentiable at $x = 0$.
4. Provide a thorough mathematical and geometric explanation of why continuity alone is necessary but not sufficient for differentiability.

---

## 2. Theoretical Background and Concepts

1. **Definition of Continuity at a Point:**
   A function $f$ is continuous at $x = c$ if and only if:
   $$
   \lim_{x \to c^-} f(x) = \lim_{x \to c^+} f(x) = f(c)
   $$

2. **Definition of One-Sided Derivatives:**
   - **Right-Hand Derivative:**
     $$
     f'_+(c) = \lim_{h \to 0^+} \frac{f(c + h) - f(c)}{h}
     $$
   - **Left-Hand Derivative:**
     $$
     f'_-(c) = \lim_{h \to 0^-} \frac{f(c + h) - f(c)}{h}
     $$

3. **Criterion for Differentiability:**
   A function $f$ is differentiable at $x = c$ if and only if:
   - $f$ is continuous at $c$.
   - Both one-sided derivatives $f'_+(c)$ and $f'_-(c)$ exist as finite real numbers.
   - The one-sided derivatives are strictly equal:
     $$
     f'_+(c) = f'_-(c)
     $$
   When this holds, the common value is the two-sided derivative $f'(c)$.

4. **Continuity vs. Differentiability ($C^1 \subset C^0$):**
   Differentiability implies continuity ($f \in D \implies f \in C$), but the converse is false ($C \not\implies D$). Continuity prevents *jumps* and *tears* in the graph; differentiability prevents *sharp corners*, *kinks*, and *vertical tangents*.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Investigation of Continuity at $x = 0$

1. **Function Value at $x = 0$:**
   Since $x = 0$ falls under the branch $x \ge 0$:
   $$
   f(0) = 0^2 = 0
   $$

2. **Right-Hand Limit ($x \to 0^+$):**
   For $x > 0$, $f(x) = x^2$:
   $$
   \lim_{x \to 0^+} f(x) = \lim_{x \to 0^+} (x^2) = 0^2 = 0
   $$

3. **Left-Hand Limit ($x \to 0^-$):**
   For $x < 0$, $f(x) = ax$:
   $$
   \lim_{x \to 0^-} f(x) = \lim_{x \to 0^-} (ax) = a \cdot 0 = 0
   $$

4. **Conclusion on Continuity:**
   For **any** real number $a \in \mathbb{R}$:
   $$
   \lim_{x \to 0^-} f(x) = \lim_{x \to 0^+} f(x) = f(0) = 0
   $$
   The left-hand limit, right-hand limit, and function value are identically zero regardless of the value of $a$.
   Therefore, $f(x)$ is **continuous at $x = 0$ for all $a \in \mathbb{R}$**.

---

### Step 2: Investigation of One-Sided Derivatives at $x = 0$

We must evaluate the one-sided limits of the difference quotient $\frac{f(h) - f(0)}{h} = \frac{f(h) - 0}{h} = \frac{f(h)}{h}$.

1. **Right-Hand Derivative $f'_+(0)$:**
   For $h > 0$, $f(h) = h^2$:
   $$
   f'_+(0) = \lim_{h \to 0^+} \frac{h^2 - 0}{h} = \lim_{h \to 0^+} h = 0
   $$
   The right-hand derivative exists and equals $0$ for every $a \in \mathbb{R}$.

2. **Left-Hand Derivative $f'_-(0)$:**
   For $h < 0$, $f(h) = ah$:
   $$
   f'_-(0) = \lim_{h \to 0^-} \frac{ah - 0}{h} = \lim_{h \to 0^-} a = a
   $$
   The left-hand derivative exists and equals $a$ for every $a \in \mathbb{R}$.

3. **Agreement of One-Sided Derivatives:**
   For the one-sided derivatives to agree:
   $$
   f'_+(0) = f'_-(0) \iff 0 = a \iff a = 0
   $$
   The one-sided derivatives exist for all $a \in \mathbb{R}$, but they agree **if and only if $a = 0$**.

---

### Step 3: Differentiability at $x = 0$

Combining the continuity and one-sided derivative results:
- For $a = 0$: $f$ is continuous, and $f'_+(0) = f'_-(0) = 0$. Thus, $f(x)$ is **differentiable at $x = 0$**, with:
  $$
  f'(0) = 0
  $$
  In this case, the function is $f(x) = \begin{cases} x^2, & x \ge 0 \\ 0, & x < 0 \end{cases}$, which smoothly transitions from a flat horizontal line to an upward-opening parabola with horizontal tangent $y = 0$.
- For $a \neq 0$: $f'_+(0) = 0 \neq a = f'_-(0)$. Thus, the two-sided limit of the difference quotient does not exist, and $f(x)$ is **not differentiable at $x = 0$**.

---

### Step 4: Why Continuity Alone Is Not Sufficient

1. **Geometric Distinction (Connection vs. Smoothness):**
   - **Continuity** is a topological property asserting that the curve has no breaks: one can draw the graph without lifting the pencil from the paper.
   - **Differentiability** is a geometric property of *smoothness*: it requires that the curve has a unique, non-vertical tangent line with a well-defined slope at that point.
   - When $a \neq 0$ (e.g., $a = 1$), the graph connects at the origin $(0, 0)$, so it is unbroken (continuous). However, approaching from the left, the curve is a line of constant slope $m_1 = a = 1$ ($45^\circ$ angle), while approaching from the right, the curve is a parabola arriving horizontally with slope $m_2 = 0$ ($0^\circ$ angle).
   - At the origin $(0, 0)$, the tangent slope abruptly jumps from $1$ to $0$. The graph forms a sharp corner (kink / angular point). There is no single tangent line that can approximate the curve from both sides.

2. **Analytical Distinction (Order of Closeness):**
   - Continuity at $c$ means $f(x) = f(c) + o(1)$ as $x \to c$ (the values get close).
   - Differentiability at $c$ means $f(x) = f(c) + L(x - c) + o(x - c)$ as $x \to c$ (the function can be locally approximated by a linear function with error decaying strictly faster than $|x - c|$).
   - This higher order of approximation requires directional agreement, which continuity does not provide.

---

## 4. Verification and Consistency Checks

1. **Visual/Slope Verification for $a = 1$:**
   Consider $f(x) = \begin{cases} x^2, & x \ge 0 \\ x, & x < 0 \end{cases}$:
   - Take secant slopes from left: with $h = -0.01$, $\frac{f(-0.01) - f(0)}{-0.01} = \frac{-0.01}{-0.01} = 1$.
   - Take secant slopes from right: with $h = +0.01$, $\frac{f(0.01) - f(0)}{0.01} = \frac{0.0001}{0.01} = 0.01$.
   - As $h \to 0$, the slopes approach $1$ from the left and $0$ from the right. The two-sided limit:
     $$
     \lim_{h \to 0} \frac{f(h) - f(0)}{h} \quad \text{does not exist}.
     $$
   This proves non-differentiability for $a = 1$.

2. **Derivative Function for $a = 0$:**
   For $a = 0$, the function is:
   $$
   f(x) = \begin{cases} x^2, & x \ge 0 \\ 0, & x < 0 \end{cases}
   $$
   Differentiating each open branch:
   $$
   f'(x) = \begin{cases} 2x, & x > 0 \\ 0, & x < 0 \end{cases}
   $$
   At the boundary $x = 0$:
   $$
   \lim_{x \to 0^+} f'(x) = \lim_{x \to 0^+} (2x) = 0, \qquad \lim_{x \to 0^-} f'(x) = \lim_{x \to 0^-} (0) = 0
   $$
   Both limits exist and equal $f'(0) = 0$. Thus, for $a = 0$, $f'(x)$ is not only well-defined at $0$, but is itself continuous on all of $\mathbb{R}$ ($f \in C^1(\mathbb{R})$).
