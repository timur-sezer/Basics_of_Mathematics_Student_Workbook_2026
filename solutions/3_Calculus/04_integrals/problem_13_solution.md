# Solution to Problem 13: An Integral Depending on the Upper Limit

## 1. Problem Statement

Given the accumulation function defined by a definite integral with a variable upper limit:
$$
F(x) = \int_0^x (t^2 + 1) \, dt
$$

1. Determine the explicit algebraic formula for $F(x)$ by performing the definite integration with respect to the dummy variable $t$.
2. Compute the derivative $F'(x)$ with respect to $x$.
3. Compare the resulting derivative $F'(x)$ with the original integrand function $f(t) = t^2 + 1$.
4. Explain in intuitive, conceptual, and geometric terms why the instantaneous rate of increase of accumulated area equals the instantaneous height of the boundary curve.

---

## 2. Theoretical Background and Concepts

1. **The Fundamental Theorem of Calculus (Part 1 - Differentiation of an Integral):**
   Let $f$ be a continuous function on an open interval containing $a$. Define the accumulation function:
   $$
   F(x) = \int_a^x f(t) \, dt
   $$
   Then $F(x)$ is differentiable on that interval, and its derivative is given by:
   $$
   F'(x) = \frac{d}{dx}\left[\int_a^x f(t) \, dt\right] = f(x)
   $$
   This theorem establishes that **integration and differentiation are exact inverse operations**.

2. **Dummy Variables vs. Independent Variables:**
   - In $\int_0^x f(t) \, dt$, $t$ is a **dummy variable of integration** (an internal counter indexing points across the interval $[0, x]$).
   - $x$ is the **independent variable** representing the position of the moving upper boundary.
   - The resulting function $F(x)$ depends strictly on $x$, not on $t$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Explicit Formula for $F(x)$

Integrate the polynomial $t^2 + 1$ with respect to $t$:
$$
\int (t^2 + 1) \, dt = \frac{t^3}{3} + t
$$

Apply the Fundamental Theorem of Calculus with lower limit $0$ and upper limit $x$:
$$
F(x) = \left[\frac{t^3}{3} + t\right]_0^x
$$

Evaluate at the upper limit $t = x$ and lower limit $t = 0$:
$$
F(x) = \left(\frac{x^3}{3} + x\right) - \left(\frac{0^3}{3} + 0\right) = \frac{x^3}{3} + x - 0
$$

Thus, the explicit formula for the accumulation function is:
$$
F(x) = \frac{x^3}{3} + x
$$

---

### Step 2: Compute $F'(x)$

Differentiate the resulting polynomial $F(x) = \frac{x^3}{3} + x$ with respect to $x$:
$$
F'(x) = \frac{d}{dx}\left[\frac{x^3}{3} + x\right] = \frac{1}{3} \frac{d}{dx}[x^3] + \frac{d}{dx}[x]
$$
$$
F'(x) = \frac{1}{3}(3x^2) + 1 = x^2 + 1
$$

---

### Step 3: Comparison with the Integrand

- The original integrand was:
  $$
  f(t) = t^2 + 1
  $$
- The derivative of the area accumulation function is:
  $$
  F'(x) = x^2 + 1
  $$
- Comparing the two:
  $$
  F'(x) = f(x)
  $$
  The derivative of the accumulation function with respect to its upper limit $x$ is **identically equal to the integrand evaluated at $x$**.

---

### Step 4: Geometric and Conceptual Explanation: Why Height Governs Area Rate

```text
       y
       ^                             |<- dx ->|
   f(x)| - - - - - - - - - - - - - - +--------+
       |                             |  dF    |
       |                             | (strip)|
       |         Accumulated         |        |
       |          Area F(x)          |        |
-------+-----------------------------+--------+---------> t
       0                             x      x + dx
```

1. **The Infinitesimal Area Slice:**
   Imagine moving the right boundary from $x$ to $x + \Delta x$.
   The added region under the curve is a thin vertical slice of width $\Delta x$.
   The change in accumulated area is:
   $$
   \Delta F = F(x + \Delta x) - F(x) = \int_x^{x + \Delta x} f(t) \, dt
   $$

2. **The Rectangular Approximation:**
   For a very small step $\Delta x$, the curve $y = f(t)$ across the narrow window $[x, x + \Delta x]$ is nearly horizontal at height $f(x)$ (by continuity).
   The thin slice is geometrically an elementary rectangle:
   $$
   \text{Area of slice } \Delta F \approx \text{Height} \times \text{Width} = f(x) \cdot \Delta x
   $$

3. **Taking the Instantaneous Limit:**
   Dividing the area increment by the width increment gives the average rate of area accumulation:
   $$
   \frac{\Delta F}{\Delta x} \approx f(x)
   $$
   In the limit as $\Delta x \to 0$, the approximation becomes exact:
   $$
   F'(x) = \lim_{\Delta x \to 0} \frac{F(x + \Delta x) - F(x)}{\Delta x} = f(x)
   $$

4. **Intuitive Physical Analogies:**
   - **The Snowplow Analogy:** Imagine driving a snowplow across a snowy field. The rate at which snow volume is cleared per meter traveled ($\frac{dV}{dx}$) depends directly on the **depth of the snow at that spot** ($h(x)$). If the snow is 1 meter deep, each meter forward clears $1 \times \text{width}$. If the snow is 5 meters deep, area accumulates 5 times faster.
   - **The Paintbrush Analogy:** When painting a wall with a brush whose bristles expand and contract vertically according to $f(x)$, pushing the brush horizontally by distance $dx$ paints an area $dA = f(x) \, dx$. The vertical span of the brush ($f(x)$) dictates the rate at which painted area grows.

---

## 4. Verification and Consistency Checks

1. **Evaluation at Specific Test Point ($x = 2$):**
   - Area accumulated up to $x = 2$:
     $$
     F(2) = \frac{2^3}{3} + 2 = \frac{8}{3} + 2 = \frac{14}{3} \approx 4.667
     $$
   - Rate of area accumulation at $x = 2$:
     $$
     F'(2) = 2^2 + 1 = 5
     $$
   - Check with a finite difference with $h = 0.001$:
     $$
     F(2.001) = \frac{2.001^3}{3} + 2.001 = \frac{8.012006}{3} + 2.001 = 2.670669 + 2.001 = 4.671669
     $$
     $$
     \frac{F(2.001) - F(2)}{0.001} = \frac{4.671669 - 4.666667}{0.001} = \frac{0.005002}{0.001} \approx 5.002 \approx 5.0
     $$
   The difference quotient confirms that area increases at an instantaneous speed of $5$ area units per unit length at $x = 2$, which is exactly the height $f(2) = 5$.

2. **Boundary Condition Check at $x = 0$:**
   $$
   F(0) = \int_0^0 (t^2 + 1) \, dt = 0
   $$
   From our formula:
   $$
   F(0) = \frac{0^3}{3} + 0 = 0
   $$
   An integral over an interval of length zero has zero area, confirming the constant of integration is zero.
