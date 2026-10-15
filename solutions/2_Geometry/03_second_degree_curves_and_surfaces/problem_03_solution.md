# Solution to Exercise 3: Ellipse

## 1. Problem Statement

Given the canonical equation of the ellipse in $\mathbb{R}^2$:
$$
\frac{x^2}{25} + \frac{y^2}{9} = 1
$$

1. Determine the lengths of the semiaxes and the full axes.
2. Find the coordinates of the intercepts with the coordinate axes (the four vertices).
3. Determine along which coordinate axis the ellipse is more stretched, and explain how this property is directly visible from the algebraic structure of the equation.

---

## 2. Theoretical Background and Concepts

1. **Canonical Form of an Origin-Centered Ellipse:**
   An ellipse centered at $(0, 0)$ with axes aligned with the coordinate axes has the equation:
   $$
   \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1
   $$
   where $a > 0$ is the semiaxis along the $x$-direction and $b > 0$ is the semiaxis along the $y$-direction.

2. **Axis Lengths and Intercepts:**
   - Setting $y = 0$ yields the $x$-intercepts: $x = \pm a$, giving primary vertices $(\pm a, 0)$. The full horizontal axis length is $2a$.
   - Setting $x = 0$ yields the $y$-intercepts: $y = \pm b$, giving secondary vertices $(0, \pm b)$. The full vertical axis length is $2b$.

3. **Geometric Scaling Principle:**
   The equation $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$ states that the sum of the normalized squares equals $1$.
   If $a > b$, a point on the curve can reach a maximum coordinate of $|x| = a$, which is larger than the maximum coordinate $|y| = b$. Thus, the larger denominator indicates the axis of greater elongation.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify Semiaxis Lengths

Comparing $\frac{x^2}{25} + \frac{y^2}{9} = 1$ with $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$:
- $a^2 = 25 \implies a = \sqrt{25} = 5$
- $b^2 = 9 \implies b = \sqrt{9} = 3$

**Summary of Dimensions:**
- **Major semiaxis (horizontal):** $a = 5$ (full major axis length $2a = 10$)
- **Minor semiaxis (vertical):** $b = 3$ (full minor axis length $2b = 6$)

---

### Step 2: Compute Intercepts with Coordinate Axes

1. **$x$-Intercepts (let $y = 0$):**
   $$
   \frac{x^2}{25} + \frac{0^2}{9} = 1 \implies \frac{x^2}{25} = 1 \implies x^2 = 25 \implies x = \pm 5
   $$
   The vertices on the $x$-axis are:
   $$
   A_1 = (-5, 0), \qquad A_2 = (5, 0)
   $$

2. **$y$-Intercepts (let $x = 0$):**
   $$
   \frac{0^2}{25} + \frac{y^2}{9} = 1 \implies \frac{y^2}{9} = 1 \implies y^2 = 9 \implies y = \pm 3
   $$
   The co-vertices on the $y$-axis are:
   $$
   B_1 = (0, -3), \qquad B_2 = (0, 3)
   $$

---

### Step 3: Axis of Greater Elongation and Algebraic Explanation

1. **Which axis is more stretched:**
   The ellipse is **more stretched along the $x$-axis** (horizontal elongation). The total width of the ellipse is $2a = 10$, whereas its total height is only $2b = 6$.

2. **Why this is visible in the equation:**
   - In the equation $\frac{x^2}{25} + \frac{y^2}{9} = 1$, the denominator under $x^2$ is $25$, which is substantially larger than the denominator under $y^2$ ($9$).
   - The value of each term $\frac{x^2}{a^2}$ and $\frac{y^2}{b^2}$ must remain in the range $[0, 1]$ since their sum is $1$.
   - Because $x^2$ is divided by $25$, $x$ must grow to $5$ before the term $\frac{x^2}{25}$ reaches $1$.
   - In contrast, $y$ only needs to reach $3$ for $\frac{y^2}{9}$ to reach $1$.
   - A larger denominator "dilutes" the growth of the variable, allowing it to take on larger numerical values before reaching the upper bound of the unit sum. Therefore, the variable with the larger denominator always corresponds to the longer axis.

---

## 4. Verification and Consistency Checks

1. **Focal Distance and Foci Coordinates:**
   Calculate the linear eccentricity $c$:
   $$
   c = \sqrt{a^2 - b^2} = \sqrt{25 - 9} = \sqrt{16} = 4
   $$
   The foci are located along the major axis at:
   $$
   F_1 = (-4, 0), \qquad F_2 = (4, 0)
   $$

2. **Focal Sum Property Check:**
   By definition of an ellipse, the sum of distances from any point on the ellipse to both foci must equal the major axis length $2a = 10$:
   - For co-vertex $B_2(0, 3)$:
     $$
     d(B_2, F_1) = \sqrt{(-4 - 0)^2 + (0 - 3)^2} = \sqrt{16 + 9} = \sqrt{25} = 5
     $$
     $$
     d(B_2, F_2) = \sqrt{(4 - 0)^2 + (0 - 3)^2} = \sqrt{16 + 9} = \sqrt{25} = 5
     $$
     $$
     d(B_2, F_1) + d(B_2, F_2) = 5 + 5 = 10 = 2a \quad (\checkmark)
     $$

3. **Arbitrary Point Substitution Check:**
   Let $x = 2.5 = \frac{5}{2}$:
   $$
   \frac{(5/2)^2}{25} + \frac{y^2}{9} = 1 \implies \frac{25/4}{25} + \frac{y^2}{9} = 1 \implies \frac{1}{4} + \frac{y^2}{9} = 1 \implies \frac{y^2}{9} = \frac{3}{4} \implies y = \pm \frac{3\sqrt{3}}{2} \approx \pm 2.598
   $$
   Check equation: $\frac{25/4}{25} + \frac{27/4}{9} = \frac{1}{4} + \frac{3}{4} = 1 \quad (\checkmark)$.
