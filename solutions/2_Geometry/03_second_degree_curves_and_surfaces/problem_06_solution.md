# Solution to Exercise 6: Shifted Ellipse

## 1. Problem Statement

Given the second-degree equation in $\mathbb{R}^2$:
$$
4x^2 + 9y^2 - 16x + 18y - 11 = 0
$$

1. Reduce the equation to canonical form by completing the square for both variables.
2. Determine the center $S = (x_0, y_0)$ and the lengths of the major and minor semiaxes.
3. Verify the algebraic consistency by evaluating the left-hand side of the original equation at the center coordinates $(x_0, y_0)$ and comparing with the completed-square form.

---

## 2. Theoretical Background and Concepts

1. **Canonical Form of a Translated Ellipse:**
   An ellipse with center $S(x_0, y_0)$ whose axes of symmetry are parallel to the Cartesian coordinate axes is described by:
   $$
   \frac{(x - x_0)^2}{a^2} + \frac{(y - y_0)^2}{b^2} = 1
   $$
   where $a > 0$ and $b > 0$ denote the horizontal and vertical semiaxes, respectively.

2. **Completing the Square with Non-Unit Leading Coefficients:**
   To complete the square for terms of the form $A x^2 + B x$:
   $$
   A x^2 + B x = A \left( x^2 + \frac{B}{A} x \right) = A \left[ \left(x + \frac{B}{2A}\right)^2 - \left(\frac{B}{2A}\right)^2 \right]
   $$
   The center coordinates $(x_0, y_0)$ correspond to the unique point where both squared binomials vanish simultaneously:
   $$
   x - x_0 = 0 \implies x_0 = -\frac{B}{2A}, \qquad y - y_0 = 0 \implies y_0 = -\frac{D}{2C}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Group Terms by Variable

Rearrange the terms:
$$
(4x^2 - 16x) + (9y^2 + 18y) - 11 = 0
$$
Factor out the leading coefficients of the quadratic terms:
$$
4(x^2 - 4x) + 9(y^2 + 2y) - 11 = 0
$$

---

### Step 2: Complete the Squares Inside Parentheses

1. **For the $x$-terms:**
   $$
   x^2 - 4x = (x - 2)^2 - 2^2 = (x - 2)^2 - 4
   $$
2. **For the $y$-terms:**
   $$
   y^2 + 2y = (y + 1)^2 - 1^2 = (y + 1)^2 - 1
   $$

---

### Step 3: Substitute Back and Simplify

Substitute the completed squares into the grouped equation:
$$
4\left[(x - 2)^2 - 4\right] + 9\left[(y + 1)^2 - 1\right] - 11 = 0
$$
Distribute the factors $4$ and $9$:
$$
4(x - 2)^2 - 16 + 9(y + 1)^2 - 9 - 11 = 0
$$
Combine the constant terms:
$$
-(16 + 9 + 11) = -36
$$
The equation becomes:
$$
4(x - 2)^2 + 9(y + 1)^2 - 36 = 0 \implies 4(x - 2)^2 + 9(y + 1)^2 = 36
$$

---

### Step 4: Divide by the Right-Hand Side to Obtain Canonical Form

Divide both sides by $36$:
$$
\frac{4(x - 2)^2}{36} + \frac{9(y + 1)^2}{36} = 1
$$
Simplify each fraction:
$$
\frac{(x - 2)^2}{9} + \frac{(y + 1)^2}{4} = 1
$$

Writing denominators as squares:
$$
\frac{(x - 2)^2}{3^2} + \frac{(y + 1)^2}{2^2} = 1
$$

---

### Step 5: Read Off Center and Semiaxis Lengths

Comparing with the standard shifted ellipse formula $\frac{(x - x_0)^2}{a^2} + \frac{(y - y_0)^2}{b^2} = 1$:
- **Center:**
  $$
  S = (x_0, y_0) = (2, -1)
  $$
- **Major Semiaxis (horizontal, along $x$):**
  $$
  a = \sqrt{9} = 3 \quad (\text{Major axis length } 2a = 6)
  $$
- **Minor Semiaxis (vertical, along $y$):**
  $$
  b = \sqrt{4} = 2 \quad (\text{Minor axis length } 2b = 4)
  $$

---

### Step 6: Consistency Check via Substitution of the Center

Evaluate the left-hand side of the general equation $f(x, y) = 4x^2 + 9y^2 - 16x + 18y - 11$ at the center $(x_0, y_0) = (2, -1)$:
$$
f(2, -1) = 4(2)^2 + 9(-1)^2 - 16(2) + 18(-1) - 11
$$
$$
f(2, -1) = 4(4) + 9(1) - 32 - 18 - 11 = 16 + 9 - 32 - 18 - 11 = 25 - 61 = -36
$$

Now examine the completed-square form:
$$
f(x, y) = 4(x - 2)^2 + 9(y + 1)^2 - 36
$$
At the center $(x, y) = (2, -1)$, both squared terms are identically zero:
$$
4(2 - 2)^2 + 9(-1 + 1)^2 - 36 = 0 + 0 - 36 = -36
$$

The direct coordinate evaluation ($25 - 61 = -36$) matches the constant $-36$ from the completed-square form. This confirms that shifting the coordinate origin to $(2, -1)$ eliminates the linear terms.

---

## 4. Verification and Consistency Checks

1. **Expansion Check:**
   Expand the canonical form $4(x - 2)^2 + 9(y + 1)^2 = 36$:
   $$
   4(x^2 - 4x + 4) + 9(y^2 + 2y + 1) = 36
   $$
   $$
   4x^2 - 16x + 16 + 9y^2 + 18y + 9 - 36 = 0
   $$
   $$
   4x^2 + 9y^2 - 16x + 18y + (16 + 9 - 36) = 0 \implies 4x^2 + 9y^2 - 16x + 18y - 11 = 0 \quad (\checkmark)
   $$
   The expansion confirms algebraic equivalence.

2. **Vertex Verification:**
   - Vertices on major axis: $(x_0 \pm a, y_0) = (2 \pm 3, -1) \implies V_1(-1, -1)$ and $V_2(5, -1)$.
     Substitute $V_2(5, -1)$ into the original equation:
     $$
     4(25) + 9(1) - 16(5) + 18(-1) - 11 = 100 + 9 - 80 - 18 - 11 = 109 - 109 = 0 \quad (\checkmark)
     $$
   - Vertices on minor axis: $(x_0, y_0 \pm b) = (2, -1 \pm 2) \implies W_1(2, -3)$ and $W_2(2, 1)$.
     Substitute $W_2(2, 1)$ into the original equation:
     $$
     4(4) + 9(1) - 16(2) + 18(1) - 11 = 16 + 9 - 32 + 18 - 11 = 43 - 43 = 0 \quad (\checkmark)
     $$
