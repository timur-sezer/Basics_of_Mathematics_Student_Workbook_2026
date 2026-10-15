# Solution to Problem 1: Antiderivative and Verification

## 1. Problem Statement

Given the polynomial function:
$$
f(x) = 3x^2 - 4x + 5
$$

1. Find one specific antiderivative $F_0(x)$ of $f(x)$.
2. Express the entire family of antiderivatives (the indefinite integral) of $f(x)$.
3. Verify the result by differentiating the family of antiderivatives to recover the original integrand.
4. Explain the mathematical, geometric, and physical meaning of the arbitrary constant of integration $C$.

---

## 2. Theoretical Background and Concepts

1. **Definition of an Antiderivative:**
   A function $F(x)$ is called an **antiderivative** (or primitive function) of a function $f(x)$ on an open interval $I$ if:
   $$
   F'(x) = f(x) \quad \forall x \in I
   $$

2. **The Indefinite Integral and Family of Antiderivatives:**
   If $F_0(x)$ is one antiderivative of $f(x)$, then every antiderivative of $f(x)$ on $I$ is of the form:
   $$
   \int f(x) \, dx = F_0(x) + C, \qquad C \in \mathbb{R}
   $$
   This follows from the Mean Value Theorem: if two differentiable functions have identical derivatives on an interval ($F_1'(x) = F_2'(x)$), their difference is constant: $\frac{d}{dx}[F_1(x) - F_2(x)] = 0 \implies F_1(x) - F_2(x) = C$.

3. **Reversing the Power Rule for Integration:**
   For any real constant $n \neq -1$:
   $$
   \int x^n \, dx = \frac{x^{n+1}}{n + 1} + C
   $$

4. **Linearity of the Indefinite Integral:**
   For constants $c_1, c_2 \in \mathbb{R}$:
   $$
   \int [c_1 u(x) \pm c_2 v(x)] \, dx = c_1 \int u(x) \, dx \pm c_2 \int v(x) \, dx
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Find One Specific Antiderivative $F_0(x)$

Integrate $f(x) = 3x^2 - 4x + 5$ term-by-term:
$$
\int (3x^2 - 4x + 5) \, dx = 3 \int x^2 \, dx - 4 \int x^1 \, dx + 5 \int x^0 \, dx
$$

Apply the power rule to each power of $x$:
- Term 1:
  $$
  3 \int x^2 \, dx = 3 \left(\frac{x^{2+1}}{2 + 1}\right) = 3 \left(\frac{x^3}{3}\right) = x^3
  $$
- Term 2:
  $$
  -4 \int x^1 \, dx = -4 \left(\frac{x^{1+1}}{1 + 1}\right) = -4 \left(\frac{x^2}{2}\right) = -2x^2
  $$
- Term 3:
  $$
  5 \int 1 \, dx = 5 \left(\frac{x^{0+1}}{0 + 1}\right) = 5x
  $$

Choosing $C = 0$ gives one specific antiderivative:
$$
F_0(x) = x^3 - 2x^2 + 5x
$$

---

### Step 2: Write the Entire Family of Antiderivatives

The general antiderivative (indefinite integral) consists of all functions that differ from $F_0(x)$ by a real constant:
$$
F(x) = x^3 - 2x^2 + 5x + C, \qquad C \in \mathbb{R}
$$

In integral notation:
$$
\int (3x^2 - 4x + 5) \, dx = x^3 - 2x^2 + 5x + C
$$

---

### Step 3: Verification by Differentiation

To verify that $F(x)$ is an antiderivative, differentiate $F(x) = x^3 - 2x^2 + 5x + C$ with respect to $x$:
$$
F'(x) = \frac{d}{dx}[x^3 - 2x^2 + 5x + C] = \frac{d}{dx}[x^3] - 2\frac{d}{dx}[x^2] + 5\frac{d}{dx}[x] + \frac{d}{dx}[C]
$$
Computing the derivatives:
- $\frac{d}{dx}[x^3] = 3x^2$
- $-2\frac{d}{dx}[x^2] = -2(2x) = -4x$
- $5\frac{d}{dx}[x] = 5(1) = 5$
- $\frac{d}{dx}[C] = 0$ (the derivative of any constant is zero)

Combining these terms:
$$
F'(x) = 3x^2 - 4x + 5 + 0 = 3x^2 - 4x + 5 = f(x)
$$
The derivative of $F(x)$ recovers $f(x)$ identically for any value of $C$.

---

### Step 4: Mathematical, Geometric, and Physical Meaning of the Constant $C$

1. **Algebraic / Analytical Meaning:**
   Differentiation is a "many-to-one" operation: infinitely many functions with different vertical offsets share the identical derivative because the derivative of a constant is zero ($\frac{d}{dx}[C] = 0$). Integration is the inverse operation, so reversing differentiation necessarily recovers this one-parameter degree of freedom.

2. **Geometric Meaning (Family of Parallel Curves):**
   The equation $y = F_0(x) + C$ defines a family of curves that are **vertical translations** of one another.
   For any chosen $x = x_0$, the slope of the tangent line to every curve in the family is:
   $$
   m = F'(x_0) = f(x_0)
   $$
   Every curve in the family has the exact same tangent slope at the same vertical line $x = x_0$. Shifting a curve upward or downward does not alter the slope of its tangent lines.

3. **Physical / Kinematic Meaning (Initial Conditions):**
   In physics, if $f(t)$ represents the instantaneous velocity $v(t)$ of a particle along a line, the antiderivative $F(t)$ represents its position $s(t)$.
   Knowing how fast an object travels ($v(t) = 3t^2 - 4t + 5$) tells you how its position *changes*, but it cannot tell you *where the object started*.
   The constant $C = F(0)$ represents the **initial position** (reference datum) of the system:
   $$
   s(t) = t^3 - 2t^2 + 5t + s_0
   $$
   To fix $C$, an external boundary or initial condition (such as $s(0) = s_0$) must be supplied.

---

## 4. Verification and Consistency Checks

1. **Definite Integral Verification via Fundamental Theorem of Calculus:**
   Evaluate the definite integral between $x = 0$ and $x = 1$:
   $$
   \int_0^1 (3x^2 - 4x + 5) \, dx = \left[x^3 - 2x^2 + 5x + C\right]_0^1
   $$
   $$
   = \Big(1^3 - 2(1^2) + 5(1) + C\Big) - \Big(0^3 - 2(0^2) + 5(0) + C\Big) = (1 - 2 + 5 + C) - (0 + C) = 4 + C - C = 4
   $$
   Notice how the arbitrary constant $C$ cancels out completely in definite integration, leaving the net accumulation invariant.

2. **Riemann Sum Approximation Check on $[0, 1]$:**
   Evaluate midpoint Riemann sum for $n = 2$ intervals with $\Delta x = 0.5$:
   - Midpoints: $m_1 = 0.25$, $m_2 = 0.75$.
   - $f(0.25) = 3(0.0625) - 4(0.25) + 5 = 0.1875 - 1 + 5 = 4.1875$.
   - $f(0.75) = 3(0.5625) - 4(0.75) + 5 = 1.6875 - 3 + 5 = 3.6875$.
   - Approximate area:
     $$
     (4.1875 + 3.6875) \times 0.5 = 7.875 \times 0.5 = 3.9375 \approx 4.0
     $$
   This reinforces that the antiderivative $F(x)$ correctly computes accumulated area.
