# Solution to Problem 2: A Parabola from the Perspective of the Derivative

## 1. Problem Statement

Given the quadratic function:
$$
f(x) = x^2 - 4x + 1
$$

1. Find the local and absolute minimum of the function using differential calculus (the first and second derivatives).
2. Determine the vertex of the parabola algebraically by completing the square (vertex form).
3. Compare the results of the two methods.
4. Explain fundamentally why both algebraic optimization (completing the square) and analytical optimization (setting the derivative to zero) inevitably lead to the exact same point.

---

## 2. Theoretical Background and Concepts

1. **Calculus Approach to Optimization:**
   For a differentiable function $f(x)$, extreme values on an open interval can only occur at critical points where:
   $$
   f'(x) = 0
   $$
   By the Second Derivative Test:
   - If $f''(x) > 0$, the function is strictly convex (concave upward) and the critical point is a strict minimum.

2. **Algebraic Approach via Completing the Square:**
   Any quadratic function $f(x) = ax^2 + bx + c$ with $a \neq 0$ can be written in the **vertex form**:
   $$
   f(x) = a(x - h)^2 + k
   $$
   where $V(h, k)$ is the vertex of the parabola.
   - Because $(x - h)^2 \ge 0$ for all $x \in \mathbb{R}$, with minimum value $0$ attained uniquely at $x = h$:
     - If $a > 0$, the parabola opens upward, and $f(x) \ge k$ for all $x$, reaching its global minimum $k$ at $x = h$.
     - If $a < 0$, the parabola opens downward, reaching its global maximum $k$ at $x = h$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: The Calculus Approach

1. **Compute the First Derivative:**
   $$
   f'(x) = \frac{d}{dx}[x^2 - 4x + 1] = 2x - 4
   $$

2. **Find the Critical Point:**
   Set $f'(x) = 0$:
   $$
   2x - 4 = 0 \implies 2x = 4 \implies x_0 = 2
   $$

3. **Verify Extremum Character via the Second Derivative:**
   $$
   f''(x) = \frac{d}{dx}[2x - 4] = 2
   $$
   Since $f''(x) = 2 > 0$ for all $x \in \mathbb{R}$, the curve is everywhere concave upward ($\cup$). By the Second Derivative Test, $x_0 = 2$ is a **strict global minimum**.

4. **Compute the Minimum Value:**
   Substitute $x = 2$ into $f(x)$:
   $$
   f(2) = (2)^2 - 4(2) + 1 = 4 - 8 + 1 = -3
   $$

The minimum point obtained via calculus is:
$$
\mathbf{V(2, -3)}
$$

---

### Step 2: The Algebraic Approach (Vertex Form)

1. **Complete the Square:**
   Group the quadratic and linear terms:
   $$
   f(x) = (x^2 - 4x) + 1
   $$
   Take half of the linear coefficient ($-4/2 = -2$), square it ($(-2)^2 = 4$), and add and subtract it inside the expression:
   $$
   f(x) = (x^2 - 4x + 4) - 4 + 1
   $$
   Factor the perfect square trinomial:
   $$
   f(x) = (x - 2)^2 - 3
   $$

2. **Read the Vertex and Minimum:**
   The vertex form is $f(x) = a(x - h)^2 + k$, where:
   - $a = 1 > 0$ (parabola opens upward)
   - $h = 2$
   - $k = -3$
   Since $(x - 2)^2 \ge 0$ for all real $x$, the smallest possible value of $(x - 2)^2$ is $0$, which occurs when $x = 2$.
   Therefore:
   $$
   f(x) = (x - 2)^2 - 3 \ge 0 - 3 = -3
   $$
   with equality if and only if $x = 2$.

The minimum point obtained algebraically is:
$$
\mathbf{V(2, -3)}
$$

---

### Step 3: Comparison and Epistemological Synthesis

Both methods identify the exact same point on the Cartesian plane:
$$
(x_{\min}, y_{\min}) = (2, -3)
$$

### Why Both Approaches Must Lead to the Same Point

1. **Analytical Connection:**
   Consider a general quadratic in vertex form:
   $$
   f(x) = a(x - h)^2 + k
   $$
   Differentiating this expression with respect to $x$ via the chain rule:
   $$
   f'(x) = 2a(x - h)
   $$
   Setting the derivative to zero to locate the stationary point:
   $$
   2a(x - h) = 0
   $$
   Since $a \neq 0$, dividing by $2a$ gives:
   $$
   x - h = 0 \iff x = h
   $$
   The condition that minimizes the algebraic squared distance $(x - h)^2$ (namely $x - h = 0$) is **identical** to the condition that makes the derivative vanish ($2a(x - h) = 0$).

2. **Geometric Connection (Horizontal Tangent at Symmetry Axis):**
   A parabola is axially symmetric with respect to its vertical line of symmetry $x = h$.
   - Any secant line connecting two symmetric points $(h - d, f(h - d))$ and $(h + d, f(h + d))$ has slope:
     $$
     m_{\text{sec}} = \frac{f(h + d) - f(h - d)}{2d} = \frac{[a d^2 + k] - [a d^2 + k]}{2d} = 0
     $$
   - As $d \to 0$, these secant lines remain strictly horizontal. Therefore, the tangent line at the vertex is necessarily horizontal ($f'(h) = 0$).
   - The algebraic vertex is the geometric turning point of the curve, which calculus detects as the point of zero instantaneous rate of change.

---

## 4. Verification and Consistency Checks

1. **Quadratic Formula for Vertex ($x = -b / 2a$):**
   For $f(x) = ax^2 + bx + c$ with $a = 1, b = -4, c = 1$:
   $$
   h = -\frac{b}{2a} = -\frac{-4}{2(1)} = \frac{4}{2} = 2
   $$
   $$
   k = f(2) = 2^2 - 4(2) + 1 = -3
   $$
   This third independent formula confirms $V(2, -3)$.

2. **Monotonicity Check:**
   - For $x < 2$: $f'(x) = 2x - 4 < 0 \implies f$ is strictly decreasing on $(-\infty, 2]$.
   - For $x > 2$: $f'(x) = 2x - 4 > 0 \implies f$ is strictly increasing on $[2, \infty)$.
   This confirms that $x = 2$ is an absolute minimum on the entire real line.
