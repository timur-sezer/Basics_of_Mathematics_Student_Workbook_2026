# Solution to Problem 6: Product Rule and Trigonometry

## 1. Problem Statement

Given the function:
$$
f(x) = x \sin x + \cos x
$$

1. Compute the derivative $f'(x)$ using the product rule and standard trigonometric differentiation rules.
2. Simplify the resulting expression algebraically.
3. Compute the value of the derivative at $x = 0$: $f'(0)$.
4. Interpret the geometric direction of the tangent line to the graph of $f(x)$ at $x = 0$, including the nature of this point.

---

## 2. Theoretical Background and Concepts

1. **Trigonometric Derivative Rules:**
   - $\frac{d}{dx}[\sin x] = \cos x$
   - $\frac{d}{dx}[\cos x] = -\sin x$

2. **The Product Rule:**
   For a product of two differentiable functions $u(x)$ and $v(x)$:
   $$
   \frac{d}{dx}[u(x) v(x)] = u'(x) v(x) + u(x) v'(x)
   $$

3. **Horizontal Tangents and Extrema:**
   A point $x_0$ where $f'(x_0) = 0$ is a stationary (critical) point.
   - The tangent line has slope $m = 0$ and is therefore horizontal, given by the constant equation $y = f(x_0)$.
   - By the First Derivative Test:
     - If $f'(x)$ transitions from negative to positive across $x_0$, the curve reaches a local minimum at $(x_0, f(x_0))$.
     - If $f'(x)$ transitions from positive to negative, the curve reaches a local maximum.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Differentiate Term-by-Term

The function is composed of a sum of two terms:
$$
f(x) = \underbrace{x \sin x}_{\text{Term 1}} + \underbrace{\cos x}_{\text{Term 2}}
$$

Applying the sum rule:
$$
f'(x) = \frac{d}{dx}[x \sin x] + \frac{d}{dx}[\cos x]
$$

### Step 2: Apply the Product Rule to $x \sin x$

Let:
- $u(x) = x \implies u'(x) = 1$
- $v(x) = \sin x \implies v'(x) = \cos x$

Applying $(u v)' = u' v + u v'$:
$$
\frac{d}{dx}[x \sin x] = (1)(\sin x) + (x)(\cos x) = \sin x + x \cos x
$$

### Step 3: Differentiate $\cos x$

Using the fundamental trigonometric derivative rule:
$$
\frac{d}{dx}[\cos x] = -\sin x
$$

### Step 4: Combine and Simplify

Substitute the two terms back into $f'(x)$:
$$
f'(x) = (\sin x + x \cos x) + (-\sin x)
$$

Notice the exact cancellation between $\sin x$ and $-\sin x$:
$$
f'(x) = \sin x - \sin x + x \cos x = x \cos x
$$

Thus, the simplified derivative is:
$$
f'(x) = x \cos x
$$

---

### Step 5: Evaluate at $x = 0$ and Geometric Interpretation

1. **Evaluate $f'(0)$:**
   Substitute $x = 0$:
   $$
   f'(0) = 0 \cdot \cos(0) = 0 \cdot 1 = 0
   $$

2. **Evaluate the Point of Tangency:**
   Substitute $x = 0$ into the original function $f(x)$:
   $$
   f(0) = 0 \cdot \sin(0) + \cos(0) = 0 + 1 = 1
   $$
   The point of tangency on the graph is $(0, 1)$.

3. **Geometric Direction of the Tangent Line:**
   - The slope of the tangent line is $m = f'(0) = 0$.
   - A line with slope $0$ is **strictly horizontal** (parallel to the $x$-axis).
   - The equation of this tangent line is:
     $$
     y - 1 = 0 \cdot (x - 0) \implies y = 1
     $$

4. **Local Behavior Around $x = 0$:**
   Examine the sign of $f'(x) = x \cos x$ in an open neighborhood around $x = 0$, for example $x \in (-\pi/2, \pi/2)$ where $\cos x > 0$:
   - For $x \in (-\pi/2, 0)$: $x < 0$ and $\cos x > 0 \implies f'(x) < 0$ (the function is strictly decreasing).
   - At $x = 0$: $f'(0) = 0$ (horizontal tangent).
   - For $x \in (0, \pi/2)$: $x > 0$ and $\cos x > 0 \implies f'(x) > 0$ (the function is strictly increasing).

   Because $f'(x)$ changes sign from negative to positive at $x = 0$, the point $(0, 1)$ is a **strict local minimum** of $f(x)$.

---

## 4. Verification and Consistency Checks

1. **Taylor Series Expansion Verification:**
   Recall the Maclaurin series for $\sin x$ and $\cos x$:
   $$
   \sin x = x - \frac{x^3}{6} + \mathcal{O}(x^5)
   $$
   $$
   \cos x = 1 - \frac{x^2}{2} + \frac{x^4}{24} - \mathcal{O}(x^6)
   $$
   Substituting these into $f(x)$:
   $$
   f(x) = x\left(x - \frac{x^3}{6} + \dots\right) + \left(1 - \frac{x^2}{2} + \frac{x^4}{24} - \dots\right)
   $$
   $$
   f(x) = \left(x^2 - \frac{x^4}{6} + \dots\right) + \left(1 - \frac{x^2}{2} + \frac{x^4}{24} - \dots\right)
   $$
   Grouping like powers:
   $$
   f(x) = 1 + \left(1 - \frac{1}{2}\right)x^2 + \left(-\frac{1}{6} + \frac{1}{24}\right)x^4 + \dots = 1 + \frac{1}{2}x^2 - \frac{1}{8}x^4 + \dots
   $$
   Differentiating term-by-term:
   $$
   f'(x) = \frac{d}{dx}\left[1 + \frac{1}{2}x^2 - \frac{1}{8}x^4 + \dots\right] = x - \frac{1}{2}x^3 + \dots
   $$
   Now expand our derivative formula $f'(x) = x \cos x$:
   $$
   x \cos x = x\left(1 - \frac{x^2}{2} + \dots\right) = x - \frac{1}{2}x^3 + \dots
   $$
   The series match term-for-term, verifying the derivative.

2. **Numerical Difference Quotient at $x = 0$:**
   For $h = 0.001$:
   $$
   f(0.001) = 0.001 \sin(0.001) + \cos(0.001) \approx 0.001(0.001) + (1 - 0.5(10^{-6})) = 1 + 0.5 \times 10^{-6}
   $$
   $$
   \frac{f(0.001) - f(0)}{0.001} \approx \frac{0.5 \times 10^{-6}}{10^{-3}} = 0.0005 \approx 0
   $$
   This independently confirms $f'(0) = 0$.
