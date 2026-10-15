# Solution to Exercise 8: Sphere

## 1. Problem Statement

Given the second-degree equation in $\mathbb{R}^3$:
$$
x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0
$$

1. Reduce the equation to canonical center-radius form by completing the square for all three variables.
2. Determine the coordinates of the center $S = (x_0, y_0, z_0)$ and the radius $R$ of the sphere.
3. Identify two simple points lying on the surface of the sphere and verify their coordinates in both the canonical and general forms of the equation.

---

## 2. Theoretical Background and Concepts

1. **Canonical Form of a Sphere:**
   In three-dimensional Euclidean space $\mathbb{R}^3$, a sphere with center $S(x_0, y_0, z_0)$ and radius $R > 0$ is defined as the locus of all points $P(x, y, z)$ whose Euclidean distance to $S$ is constant and equal to $R$:
   $$
   \|\overrightarrow{SP}\| = R \iff (x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2 = R^2
   $$

2. **Completing the Square in Three Dimensions:**
   The general equation of a sphere with unit quadratic coefficients:
   $$
   x^2 + y^2 + z^2 + D x + E y + F z + G = 0
   $$
   is reduced by completing the square independently on each variable coordinate:
   $$
   \left(x + \frac{D}{2}\right)^2 + \left(y + \frac{E}{2}\right)^2 + \left(z + \frac{F}{2}\right)^2 = \left(\frac{D}{2}\right)^2 + \left(\frac{E}{2}\right)^2 + \left(\frac{F}{2}\right)^2 - G
   $$
   A real sphere exists if and only if the right-hand side is strictly positive ($R^2 > 0$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Group the Terms by Variable

Rearrange the given equation:
$$
(x^2 - 4x) + (y^2 + 2y) + (z^2 - 6z) - 2 = 0
$$

---

### Step 2: Complete the Squares

1. **For the $x$-terms:**
   $$
   x^2 - 4x = (x - 2)^2 - 2^2 = (x - 2)^2 - 4
   $$
2. **For the $y$-terms:**
   $$
   y^2 + 2y = (y + 1)^2 - 1^2 = (y + 1)^2 - 1
   $$
3. **For the $z$-terms:**
   $$
   z^2 - 6z = (z - 3)^2 - 3^2 = (z - 3)^2 - 9
   $$

---

### Step 3: Substitute and Simplify to Canonical Form

Substitute the completed squares into the grouped equation:
$$
\left[(x - 2)^2 - 4\right] + \left[(y + 1)^2 - 1\right] + \left[(z - 3)^2 - 9\right] - 2 = 0
$$
Combine the constant numerical terms:
$$
(x - 2)^2 + (y + 1)^2 + (z - 3)^2 - (4 + 1 + 9 + 2) = 0
$$
$$
(x - 2)^2 + (y + 1)^2 + (z - 3)^2 - 16 = 0
$$
Move the constant to the right-hand side:
$$
(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16
$$

Writing the right-hand side as a square:
$$
(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 4^2
$$

---

### Step 4: Identify Center and Radius

Comparing with $(x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2 = R^2$:
- **Center:**
  $$
  S = (x_0, y_0, z_0) = (2, -1, 3)
  $$
- **Radius:**
  $$
  R = \sqrt{16} = 4
  $$

---

### Step 5: Choose and Verify Two Points on the Sphere

To select simple points, displace from the center by $R = 4$ along the standard basis directions:

1. **Point $P_1$ (displacement along the positive $x$-direction):**
   - Coordinates: $(x_0 + R, y_0, z_0) = (2 + 4, -1, 3) = (6, -1, 3)$

   *Check in Canonical Form:*
   $$
   (6 - 2)^2 + (-1 + 1)^2 + (3 - 3)^2 = 4^2 + 0^2 + 0^2 = 16 = 16 \quad (\checkmark)
   $$
   *Check in General Form:*
   $$
   6^2 + (-1)^2 + 3^2 - 4(6) + 2(-1) - 6(3) - 2
   $$
   $$
   = 36 + 1 + 9 - 24 - 2 - 18 - 2 = 46 - 46 = 0 \quad (\checkmark)
   $$

2. **Point $P_2$ (displacement along the positive $z$-direction):**
   - Coordinates: $(x_0, y_0, z_0 + R) = (2, -1, 3 + 4) = (2, -1, 7)$

   *Check in Canonical Form:*
   $$
   (2 - 2)^2 + (-1 + 1)^2 + (7 - 3)^2 = 0^2 + 0^2 + 4^2 = 16 = 16 \quad (\checkmark)
   $$
   *Check in General Form:*
   $$
   2^2 + (-1)^2 + 7^2 - 4(2) + 2(-1) - 6(7) - 2
   $$
   $$
   = 4 + 1 + 49 - 8 - 2 - 42 - 2 = 54 - 54 = 0 \quad (\checkmark)
   $$

Both points satisfy both representations of the sphere.

---

## 4. Verification and Consistency Checks

1. **Algebraic Expansion Check:**
   Expand $(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16$:
   $$
   (x^2 - 4x + 4) + (y^2 + 2y + 1) + (z^2 - 6z + 9) = 16
   $$
   $$
   x^2 + y^2 + z^2 - 4x + 2y - 6z + (4 + 1 + 9) - 16 = 0
   $$
   $$
   x^2 + y^2 + z^2 - 4x + 2y - 6z + 14 - 16 = 0 \implies x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0 \quad (\checkmark)
   $$
   The expanded equation matches the original expression identically.

2. **Equidistance Verification:**
   Compute the distance from $P_1(6, -1, 3)$ and $P_2(2, -1, 7)$ to center $S(2, -1, 3)$:
   - $d(P_1, S) = \sqrt{(6 - 2)^2 + (-1 - (-1))^2 + (3 - 3)^2} = \sqrt{4^2 + 0 + 0} = 4 = R \quad (\checkmark)$
   - $d(P_2, S) = \sqrt{(2 - 2)^2 + (-1 - (-1))^2 + (7 - 3)^2} = \sqrt{0 + 0 + 4^2} = 4 = R \quad (\checkmark)$
