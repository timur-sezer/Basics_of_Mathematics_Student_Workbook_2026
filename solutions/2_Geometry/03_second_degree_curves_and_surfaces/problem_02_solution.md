# Solution to Exercise 2: Circle by Completing the Square

## 1. Problem Statement

Given the general equation of a second-degree curve in $\mathbb{R}^2$:
$$
x^2 + y^2 - 6x + 4y - 3 = 0
$$

1. Reduce the equation to canonical form by completing the square for both variables.
2. Determine the center $S = (x_0, y_0)$ and the radius $R$ of the circle.
3. Choose two simple points lying on the circle and verify that their coordinates satisfy both the canonical form and the original general form.

---

## 2. Theoretical Background and Concepts

1. **General Equation of a Circle:**
   The general equation of a circle in $\mathbb{R}^2$ is:
   $$
   x^2 + y^2 + D x + E y + F = 0
   $$
   where the coefficients of $x^2$ and $y^2$ are equal and non-zero, and there is no cross-product term $xy$.

2. **Completing the Square Technique:**
   For any quadratic expression $u^2 + b u$, completing the square gives:
   $$
   u^2 + b u = \left(u + \frac{b}{2}\right)^2 - \left(\frac{b}{2}\right)^2
   $$
   Applying this to $x$ and $y$ transforms the general equation into canonical (center-radius) form:
   $$
   (x - x_0)^2 + (y - y_0)^2 = R^2
   $$
   where $(x_0, y_0)$ is the circle's center and $R = \sqrt{R^2} > 0$ is its radius.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Group Terms by Variable

Rearrange the terms of the equation:
$$
(x^2 - 6x) + (y^2 + 4y) - 3 = 0
$$

---

### Step 2: Complete the Squares

1. **For the $x$-terms:**
   $$
   x^2 - 6x = (x - 3)^2 - 3^2 = (x - 3)^2 - 9
   $$
2. **For the $y$-terms:**
   $$
   y^2 + 4y = (y + 2)^2 - 2^2 = (y + 2)^2 - 4
   $$

---

### Step 3: Substitute and Simplify to Canonical Form

Substitute the completed squares back into the equation:
$$
\left[(x - 3)^2 - 9\right] + \left[(y + 2)^2 - 4\right] - 3 = 0
$$
Combine the constant terms:
$$
(x - 3)^2 + (y + 2)^2 - (9 + 4 + 3) = 0
$$
$$
(x - 3)^2 + (y + 2)^2 - 16 = 0
$$
Move the constant to the right-hand side:
$$
(x - 3)^2 + (y + 2)^2 = 16
$$

Since $16 = 4^2$, the canonical equation is:
$$
(x - 3)^2 + (y + 2)^2 = 4^2
$$

---

### Step 4: Identify Center and Radius

Comparing with $(x - x_0)^2 + (y - y_0)^2 = R^2$:
- **Center:** $S = (x_0, y_0) = (3, -2)$
- **Radius:** $R = \sqrt{16} = 4$

---

### Step 5: Select and Verify Two Points on the Circle

To find simple points, displace from the center by $R = 4$ along the principal directions:

1. **Point $P_1$ (horizontal displacement $x = x_0 + R, y = y_0$):**
   - $x = 3 + 4 = 7$
   - $y = -2$
   - Coordinates: $P_1(7, -2)$

   *Verification in Canonical Form:*
   $$
   (7 - 3)^2 + (-2 + 2)^2 = 4^2 + 0^2 = 16 = 16 \quad (\checkmark)
   $$
   *Verification in General Form:*
   $$
   7^2 + (-2)^2 - 6(7) + 4(-2) - 3 = 49 + 4 - 42 - 8 - 3 = 53 - 53 = 0 \quad (\checkmark)
   $$

2. **Point $P_2$ (vertical displacement $x = x_0, y = y_0 + R$):**
   - $x = 3$
   - $y = -2 + 4 = 2$
   - Coordinates: $P_2(3, 2)$

   *Verification in Canonical Form:*
   $$
   (3 - 3)^2 + (2 + 2)^2 = 0^2 + 4^2 = 16 = 16 \quad (\checkmark)
   $$
   *Verification in General Form:*
   $$
   3^2 + 2^2 - 6(3) + 4(2) - 3 = 9 + 4 - 18 + 8 - 3 = 21 - 21 = 0 \quad (\checkmark)
   $$

Both points satisfy both forms of the equation.

---

## 4. Verification and Consistency Checks

1. **Expansion Check:**
   Expand the canonical form $(x - 3)^2 + (y + 2)^2 = 16$:
   $$
   (x^2 - 6x + 9) + (y^2 + 4y + 4) = 16
   $$
   $$
   x^2 + y^2 - 6x + 4y + 13 - 16 = 0 \implies x^2 + y^2 - 6x + 4y - 3 = 0 \quad (\checkmark)
   $$
   The expanded form recovers the original equation.

2. **General Center-Radius Formula Check:**
   For $x^2 + y^2 + D x + E y + F = 0$ with $D = -6, E = 4, F = -3$:
   - Center: $\left(-\frac{D}{2}, -\frac{E}{2}\right) = \left(-\frac{-6}{2}, -\frac{4}{2}\right) = (3, -2) \quad (\checkmark)$
   - Radius: $R = \sqrt{\left(\frac{D}{2}\right)^2 + \left(\frac{E}{2}\right)^2 - F} = \sqrt{(-3)^2 + 2^2 - (-3)} = \sqrt{9 + 4 + 3} = \sqrt{16} = 4 \quad (\checkmark)$
