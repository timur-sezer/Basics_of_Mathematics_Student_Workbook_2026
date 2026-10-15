# Solution to Problem 15: Recovering a Function from Its Derivative and a Condition

## 1. Problem Statement

A function $F(x)$ satisfies the initial value problem (differential equation with an initial condition):
$$
F'(x) = 2x e^{x^2} \qquad \text{and} \qquad F(0) = 3
$$

1. Identify and explain the integration method required to find the antiderivative of $F'(x)$.
2. Compute the complete one-parameter family of antiderivatives (the general solution).
3. Apply the initial condition $F(0) = 3$ to uniquely determine the numerical value of the constant of integration $C$.
4. State the unique particular solution $F(x)$.
5. Verify the final result by differentiating $F(x)$ and evaluating it at $x = 0$.

---

## 2. Theoretical Background and Concepts

1. **The Initial Value Problem (IVP):**
   In mathematics and physical sciences, laws of nature frequently specify the rate of change of a quantity:
   $$
   \frac{dF}{dx} = f(x)
   $$
   Integration yields a family of infinitely many curves parameterized by an arbitrary constant $C$:
   $$
   F(x) = F_0(x) + C
   $$
   An **initial condition** $F(x_0) = y_0$ selects the single, unique trajectory from this family that passes through the prescribed coordinate $(x_0, y_0)$.

2. **Recognition of the Substitution Rule:**
   An integral of the form:
   $$
   \int g'(x) e^{g(x)} \, dx
   $$
   is evaluated by the substitution $u = g(x)$, with differential $du = g'(x) \, dx$, reducing the problem to the standard exponential integral $\int e^u \, du = e^u + C$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Recognize the Integration Method

We need to evaluate the indefinite integral:
$$
F(x) = \int F'(x) \, dx = \int 2x e^{x^2} \, dx
$$

**Structural Analysis:**
- The integrand consists of a composite exponential term $e^{x^2}$ multiplied by an algebraic term $2x$.
- The exponent is an inner function $g(x) = x^2$.
- Differentiating the exponent gives $\frac{d}{dx}[x^2] = 2x$.
- This derivative factor $2x$ appears explicitly and completely as a multiplier of $dx$.
- Therefore, the appropriate method is **$u$-substitution (reversing the chain rule)**.

---

### Step 2: Determine the Entire Family of Antiderivatives

1. **Set Up the Substitution:**
   $$
   u = x^2
   $$
2. **Compute the Differential:**
   $$
   du = 2x \, dx
   $$
3. **Transform the Integral:**
   $$
   \int 2x e^{x^2} \, dx = \int e^{x^2} \cdot (2x \, dx) = \int e^u \, du
   $$
4. **Evaluate the Integral:**
   $$
   \int e^u \, du = e^u + C
   $$
5. **Back-Substitute $u = x^2$:**
   $$
   F(x) = e^{x^2} + C, \qquad C \in \mathbb{R}
   $$

This represents the complete family of all possible antiderivatives of $2x e^{x^2}$.

---

### Step 3: Determine the Constant $C$ Using the Condition $F(0) = 3$

We are given the initial condition:
$$
F(0) = 3
$$

1. Substitute $x = 0$ into our general family $F(x) = e^{x^2} + C$:
   $$
   F(0) = e^{0^2} + C = e^0 + C
   $$
   Since $e^0 = 1$:
   $$
   F(0) = 1 + C
   $$

2. Equate this to the prescribed initial value:
   $$
   1 + C = 3
   $$

3. Solve for $C$:
   $$
   C = 3 - 1 = 2
   $$

The unique constant of integration satisfying the condition is:
$$
C = 2
$$

---

### Step 4: Write the Final Particular Solution

Substituting $C = 2$ into the general family yields the unique function:
$$
\mathbf{F(x) = e^{x^2} + 2}
$$

---

### Step 5: Verification of the Solution

We verify that $F(x) = e^{x^2} + 2$ satisfies both requirements of the problem:

1. **Verification of the Derivative Condition:**
   Differentiate $F(x) = e^{x^2} + 2$ with respect to $x$ using the chain rule:
   $$
   F'(x) = \frac{d}{dx}\left[e^{x^2} + 2\right] = \frac{d}{dx}\left[e^{x^2}\right] + \frac{d}{dx}[2]
   $$
   Using $\frac{d}{dx}[e^{u(x)}] = e^{u(x)} u'(x)$:
   $$
   F'(x) = e^{x^2} \cdot \frac{d}{dx}[x^2] + 0 = e^{x^2} \cdot (2x) = 2x e^{x^2}
   $$
   This matches the given differential equation $F'(x) = 2x e^{x^2}$ identically.

2. **Verification of the Initial Value Condition:**
   Substitute $x = 0$ into $F(x)$:
   $$
   F(0) = e^{0^2} + 2 = e^0 + 2 = 1 + 2 = 3
   $$
   This matches the given condition $F(0) = 3$ identically.

Both conditions are verified.

---

## 4. Verification and Consistency Checks

1. **Definite Integral Form via Fundamental Theorem of Calculus:**
   By the Fundamental Theorem of Calculus, any initial value problem $F'(t) = f(t)$ with $F(x_0) = y_0$ can be represented directly as:
   $$
   F(x) = y_0 + \int_{x_0}^x F'(t) \, dt
   $$
   Substituting $x_0 = 0$, $y_0 = 3$, and $F'(t) = 2t e^{t^2}$:
   $$
   F(x) = 3 + \int_0^x 2t e^{t^2} \, dt
   $$
   Evaluate the integral with substitution $u = t^2$, where $t = 0 \implies u = 0$ and $t = x \implies u = x^2$:
   $$
   \int_0^x 2t e^{t^2} \, dt = \int_0^{x^2} e^u \, du = \Big[e^u\Big]_0^{x^2} = e^{x^2} - e^0 = e^{x^2} - 1
   $$
   Substitute back:
   $$
   F(x) = 3 + (e^{x^2} - 1) = e^{x^2} + 2
   $$
   This confirms the algebraic result.

2. **Geometric Behavior of the Solution Curve:**
   - Because $x^2 \ge 0$ for all $x \in \mathbb{R}$, $e^{x^2} \ge 1$ everywhere.
   - Therefore, $F(x) = e^{x^2} + 2 \ge 1 + 2 = 3$ for all $x \in \mathbb{R}$.
   - The point $(0, 3)$ is the **global minimum** of the curve $y = F(x)$.
   - At $x = 0$, the slope is $F'(0) = 2(0)e^0 = 0$, so the tangent line at the initial condition point $(0, 3)$ is horizontal: $y = 3$.
   - The curve is symmetric about the $y$-axis (even function: $F(-x) = F(x)$), opening upward with rapid exponential growth as $|x| \to \infty$.
