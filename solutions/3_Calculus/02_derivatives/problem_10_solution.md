# Solution to Problem 10: The Tangent Line as an Application of the Derivative

## 1. Problem Statement

Given the quadratic function:
$$
f(x) = x^2 - 3x + 1
$$

1. Find the coordinates of the point of tangency $P(x_0, y_0)$ at $x_0 = 2$.
2. Compute the derivative value $f'(2)$, representing the slope $m$ of the tangent line.
3. Determine the equation of the tangent line in both slope-intercept and general forms.
4. Verify that the point of tangency satisfies the derived tangent line equation, and verify the geometric tangency property (multiplicity of intersection).

---

## 2. Theoretical Background and Concepts

1. **Point-Slope Equation of the Tangent Line:**
   For a function $f(x)$ differentiable at $x_0$, the tangent line to the graph of $y = f(x)$ at the point $(x_0, f(x_0))$ has slope:
   $$
   m = f'(x_0)
   $$
   Its point-slope equation is:
   $$
   y - f(x_0) = f'(x_0)(x - x_0)
   $$
   In slope-intercept form ($y = mx + b$):
   $$
   y = f'(x_0)x + \left[f(x_0) - x_0 f'(x_0)\right]
   $$

2. **Algebraic Meaning of Tangency:**
   For a curve $y = f(x)$ and a line $y = L(x)$, the line is tangent to the curve at $x = x_0$ if and only if:
   - $f(x_0) = L(x_0)$ (the line touches the curve at the point of tangency).
   - $f'(x_0) = L'(x_0)$ (they share the same slope at that point).
   For polynomial curves, this implies that the difference polynomial $D(x) = f(x) - L(x)$ has a root of multiplicity at least $2$ at $x = x_0$, meaning that $(x - x_0)^2$ factors out of $D(x)$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Find the Coordinates of the Point of Tangency

The given $x$-coordinate is $x_0 = 2$.
Substitute $x = 2$ into the original function $f(x)$:
$$
y_0 = f(2) = (2)^2 - 3(2) + 1 = 4 - 6 + 1 = -1
$$

Thus, the point of tangency is:
$$
P(x_0, y_0) = (2, -1)
$$

---

### Step 2: Compute the Derivative and the Tangent Slope

1. Differentiate $f(x) = x^2 - 3x + 1$ using the power rule:
   $$
   f'(x) = \frac{d}{dx}[x^2] - 3\frac{d}{dx}[x] + \frac{d}{dx}[1] = 2x - 3 + 0 = 2x - 3
   $$
2. Evaluate the derivative at $x_0 = 2$:
   $$
   m = f'(2) = 2(2) - 3 = 4 - 3 = 1
   $$

The slope of the tangent line is $m = 1$.

---

### Step 3: Formulate the Equation of the Tangent Line

Substitute $x_0 = 2$, $y_0 = -1$, and $m = 1$ into the point-slope form:
$$
y - y_0 = m(x - x_0) \implies y - (-1) = 1(x - 2)
$$
Simplify:
$$
y + 1 = x - 2 \implies y = x - 3
$$

- **Slope-Intercept Form:**
  $$
  y = x - 3
  $$
- **General Form ($Ax + By + C = 0$):**
  $$
  x - y - 3 = 0
  $$

---

### Step 4: Verification of Tangency

1. **Verify that the Point of Tangency Lies on the Line:**
   Substitute the coordinates $(x, y) = (2, -1)$ into the tangent equation $y = x - 3$:
   $$
   \text{LHS} = -1, \qquad \text{RHS} = 2 - 3 = -1
   $$
   $\text{LHS} = \text{RHS} = -1$. The point $P(2, -1)$ lies on the line.

2. **Algebraic Double-Root Verification:**
   Subtract the tangent line $y = x - 3$ from the parabola $y = f(x)$:
   $$
   D(x) = f(x) - (x - 3) = (x^2 - 3x + 1) - (x - 3) = x^2 - 4x + 4
   $$
   Factoring the quadratic:
   $$
   D(x) = (x - 2)^2
   $$
   - The root at $x = 2$ has **multiplicity 2**, algebraically confirming that the line is tangent to the parabola at $x = 2$.
   - Furthermore, because $(x - 2)^2 \ge 0$ for all $x \in \mathbb{R}$:
     $$
     f(x) \ge x - 3 \quad \forall x \in \mathbb{R}
     $$
     The parabola lies entirely above its tangent line for all $x \neq 2$, touching it only at the single point $(2, -1)$.

---

## 4. Verification and Consistency Checks

1. **Secant-to-Tangent Limit Check:**
   Take a point $Q(2 + h, f(2 + h))$ on the parabola for $h \neq 0$:
   $$
   f(2 + h) = (2 + h)^2 - 3(2 + h) + 1 = (4 + 4h + h^2) - (6 + 3h) + 1 = -1 + h + h^2
   $$
   The slope of the secant line through $P(2, -1)$ and $Q(2+h, f(2+h))$ is:
   $$
   m_{\text{sec}} = \frac{f(2 + h) - f(2)}{h} = \frac{(-1 + h + h^2) - (-1)}{h} = \frac{h + h^2}{h} = 1 + h
   $$
   Taking the limit as $h \to 0$:
   $$
   m = \lim_{h \to 0} m_{\text{sec}} = \lim_{h \to 0} (1 + h) = 1
   $$
   This matches $m = 1$.

2. **Intercept Checks:**
   - Tangent line $x$-intercept: set $y = 0 \implies x - 3 = 0 \implies (3, 0)$.
   - Tangent line $y$-intercept: set $x = 0 \implies y = -3 \implies (0, -3)$.
   - Both intercepts are consistent with a line of slope $1$ passing through $(2, -1)$.
