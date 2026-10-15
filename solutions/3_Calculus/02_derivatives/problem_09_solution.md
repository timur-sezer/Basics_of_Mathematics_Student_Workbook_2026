# Solution to Problem 9: A Logarithm and the Chain Rule

## 1. Problem Statement

Given the natural logarithmic function:
$$
f(x) = \ln(x^2 + 1)
$$

1. Determine the domain $\mathcal{D}_f$ and compute the derivative $f'(x)$ using the chain rule.
2. Determine the algebraic sign of $f'(x)$ for each of the three regimes:
   - $x < 0$
   - $x = 0$
   - $x > 0$
3. Describe qualitatively the behavior, monotonicity, and geometric profile of the function $f(x)$ around zero.

---

## 2. Theoretical Background and Concepts

1. **Domain and Properties of the Natural Logarithm:**
   The function $\ln(u)$ is defined strictly for arguments $u > 0$.
   Since $x^2 \ge 0$ for all $x \in \mathbb{R}$, we have $x^2 + 1 \ge 1 > 0$ everywhere, so the domain is all real numbers:
   $$
   \mathcal{D}_f = \mathbb{R}
   $$

2. **The Chain Rule for Logarithms:**
   For a positive, differentiable function $u(x) > 0$:
   $$
   \frac{d}{dx}[\ln(u(x))] = \frac{1}{u(x)} \cdot u'(x) = \frac{u'(x)}{u(x)}
   $$

3. **Monotonicity and the First Derivative Test:**
   - **$f'(x) > 0$ on an interval:** $f$ is strictly increasing on that interval.
   - **$f'(x) < 0$ on an interval:** $f$ is strictly decreasing on that interval.
   - **$f'(x_0) = 0$:** $x_0$ is a stationary point. If $f'(x)$ changes from negative to positive across $x_0$, then $x_0$ is a strict local minimum.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify Layers and Compute the Derivative

1. **Inner Function:**
   $$
   u(x) = x^2 + 1 \implies u'(x) = 2x
   $$
2. **Outer Function:**
   $$
   g(u) = \ln u \implies g'(u) = \frac{1}{u}
   $$
3. **Apply the Chain Rule:**
   $$
   f'(x) = g'(u(x)) \cdot u'(x) = \frac{1}{x^2 + 1} \cdot 2x = \frac{2x}{x^2 + 1}
   $$

The derivative function is:
$$
f'(x) = \frac{2x}{x^2 + 1}
$$

---

### Step 2: Sign Analysis of $f'(x)$

Notice the crucial property of the denominator:
$$
x^2 + 1 \ge 1 > 0 \quad \forall x \in \mathbb{R}
$$
Because the denominator is strictly positive for every real number, it does not affect the sign of the quotient. The algebraic sign of $f'(x)$ is completely governed by the numerator $2x$:

1. **For $x < 0$:**
   $$
   2x < 0 \implies f'(x) = \frac{2x}{x^2 + 1} < 0
   $$
   The derivative is **strictly negative**.

2. **For $x = 0$:**
   $$
   f'(0) = \frac{2(0)}{0^2 + 1} = \frac{0}{1} = 0
   $$
   The derivative is **zero** (stationary point).

3. **For $x > 0$:**
   $$
   2x > 0 \implies f'(x) = \frac{2x}{x^2 + 1} > 0
   $$
   The derivative is **strictly positive**.

---

### Step 3: Qualitative Description of the Function Around Zero

1. **Function Value at Zero:**
   $$
   f(0) = \ln(0^2 + 1) = \ln(1) = 0
   $$
   The graph passes through the origin $(0, 0)$.

2. **Global Minimum:**
   - Because $f'(x) < 0$ for all $x \in (-\infty, 0)$, $f(x)$ is strictly decreasing on $(-\infty, 0]$.
   - Because $f'(x) > 0$ for all $x \in (0, \infty)$, $f(x)$ is strictly increasing on $[0, \infty)$.
   - By the First Derivative Test, the origin $(0, 0)$ is the unique **global (absolute) minimum** of $f(x)$ on $\mathbb{R}$.
   - For all $x \neq 0$, $x^2 + 1 > 1$, which implies $f(x) = \ln(x^2 + 1) > \ln(1) = 0$.

3. **Tangent Line at the Origin:**
   The slope of the tangent line at $(0, 0)$ is $m = f'(0) = 0$. The tangent line is the horizontal line $y = 0$, which is the $x$-axis itself.

4. **Curvature and Even Symmetry:**
   - The function is strictly even: $f(-x) = \ln((-x)^2 + 1) = \ln(x^2 + 1) = f(x)$, so the curve is symmetric with respect to the $y$-axis.
   - Using the Maclaurin expansion $\ln(1 + u) = u - \frac{u^2}{2} + \dots$ for $u = x^2$:
     $$
     f(x) = \ln(1 + x^2) = x^2 - \frac{x^4}{2} + \mathcal{O}(x^6)
     $$
   - In an immediate neighborhood of $x = 0$, the graph closely resembles the standard parabola $y = x^2$, curving upward gently from its vertex at the origin.

---

## 4. Verification and Consistency Checks

1. **Second Derivative Test at $x = 0$:**
   Differentiate $f'(x) = \frac{2x}{x^2 + 1}$ using the quotient rule:
   $$
   f''(x) = \frac{(2)(x^2 + 1) - (2x)(2x)}{(x^2 + 1)^2} = \frac{2x^2 + 2 - 4x^2}{(x^2 + 1)^2} = \frac{2(1 - x^2)}{(x^2 + 1)^2}
   $$
   Evaluating at $x = 0$:
   $$
   f''(0) = \frac{2(1 - 0)}{(0 + 1)^2} = 2 > 0
   $$
   Since $f'(0) = 0$ and $f''(0) = 2 > 0$, the Second Derivative Test independently proves that $x = 0$ is a strict local minimum.

2. **Numerical Difference Quotient Check at $x = 1$:**
   - Theoretical value:
     $$
     f'(1) = \frac{2(1)}{1^2 + 1} = \frac{2}{2} = 1
     $$
   - Numerical difference quotient with $h = 10^{-4}$:
     $$
     \frac{f(1.0001) - f(1)}{0.0001} = \frac{\ln((1.0001)^2 + 1) - \ln(2)}{0.0001} = \frac{\ln(2.00020001) - \ln(2)}{0.0001}
     $$
     Using $\ln\left(1 + \frac{0.00020001}{2}\right) \approx \frac{0.00020001}{2} = 0.000100005$:
     $$
     \frac{0.000100005}{0.0001} \approx 1.00005 \approx 1
     $$
   This confirms the derivative formula.
