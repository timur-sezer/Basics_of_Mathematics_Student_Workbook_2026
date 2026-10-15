# Solution to Exercise 7: Classifying a Second-Degree Equation

## 1. Problem Statement

Determine the geometric type of object described by each of the following second-degree equations in $\mathbb{R}^2$:

1. $4x^2 + 9y^2 = 36$
2. $x^2 - y^2 = 1$
3. $x^2 - 4y = 0$
4. $x^2 + y^2 + 1 = 0$

For the fourth equation, explain thoroughly why there are no real points satisfying the equation.

---

## 2. Theoretical Background and Concepts

1. **General Second-Degree Equation in Two Variables:**
   A quadratic equation in $x$ and $y$ with no cross-product term ($B = 0$) has the form:
   $$
   A x^2 + C y^2 + D x + E y + F = 0
   $$
   The geometric nature of the real solution locus depends on the signs and values of the quadratic coefficients $A$ and $C$:
   - **Ellipse / Circle ($A \cdot C > 0$):** Both coefficients have the same sign. If reduced to $A(x - x_0)^2 + C(y - y_0)^2 = M$ with $M > 0$, it is an ellipse (or a circle if $A = C$). If $M = 0$, it is a single point (degenerate ellipse). If $M < 0$, it is the empty set (imaginary ellipse).
   - **Hyperbola ($A \cdot C < 0$):** Coefficients have opposite signs. If reduced to a non-zero RHS, it is a hyperbola. If RHS is zero, it represents two intersecting lines.
   - **Parabola ($A \cdot C = 0$):** Exactly one of $A$ or $C$ is zero, and the corresponding variable appears to the first power.

2. **Non-Negativity of Real Squares:**
   For any real number $u \in \mathbb{R}$, $u^2 \ge 0$. The sum of squares of real numbers is strictly non-negative:
   $$
   x^2 + y^2 \ge 0 \quad \forall x, y \in \mathbb{R}
   $$

---

## 3. Detailed Step-by-Step Solution

### Equation 1: $4x^2 + 9y^2 = 36$

1. **Reduction to Canonical Form:**
   Divide both sides by $36$:
   $$
   \frac{4x^2}{36} + \frac{9y^2}{36} = 1 \implies \frac{x^2}{9} + \frac{y^2}{4} = 1
   $$
   Writing in standard form $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$:
   $$
   \frac{x^2}{3^2} + \frac{y^2}{2^2} = 1
   $$
2. **Classification:**
   This is an **ellipse** centered at the origin $(0, 0)$ with horizontal major semiaxis $a = 3$ and vertical minor semiaxis $b = 2$.

---

### Equation 2: $x^2 - y^2 = 1$

1. **Reduction to Canonical Form:**
   Rewrite as:
   $$
   \frac{x^2}{1^2} - \frac{y^2}{1^2} = 1
   $$
2. **Classification:**
   This is an **equilateral (rectangular) hyperbola** centered at the origin $(0, 0)$.
   - Real semiaxis: $a = 1$, imaginary semiaxis: $b = 1$.
   - Vertices: $(\pm 1, 0)$.
   - Asymptotes: $y = \pm \frac{b}{a} x = \pm x$. The asymptotes are mutually perpendicular ($m_1 \cdot m_2 = (1)(-1) = -1$), which characterizes an equilateral hyperbola.

---

### Equation 3: $x^2 - 4y = 0$

1. **Reduction to Canonical Form:**
   Isolate the linear variable $y$ or write in standard parabolic form:
   $$
   x^2 = 4y \iff y = \frac{1}{4}x^2
   $$
   Comparing with $x^2 = 2py$, we have $2p = 4 \implies p = 2$.
2. **Classification:**
   This is a **parabola** opening upward along the positive $y$-axis.
   - Vertex: $V = (0, 0)$.
   - Axis of symmetry: The line $x = 0$ ($y$-axis).
   - Focus: $F = \left(0, \frac{p}{2}\right) = (0, 1)$.
   - Directrix: Horizontal line $y = -\frac{p}{2} = -1$.

---

### Equation 4: $x^2 + y^2 + 1 = 0$

1. **Algebraic Manipulation:**
   Subtract $1$ from both sides:
   $$
   x^2 + y^2 = -1
   $$

2. **Classification:**
   This equation describes the **empty set** $\emptyset$ (in the real plane $\mathbb{R}^2$). There are **no real points** satisfying the equation (it represents an imaginary circle of radius $R = \sqrt{-1} = i$).

3. **Why There Are No Real Points (Formal Explanation):**
   - For every real number $x \in \mathbb{R}$, its square is non-negative: $x^2 \ge 0$.
   - Similarly, for every real number $y \in \mathbb{R}$, its square is non-negative: $y^2 \ge 0$.
   - Summing these two inequalities gives:
     $$
     x^2 + y^2 \ge 0 \quad \text{for all } (x, y) \in \mathbb{R}^2
     $$
   - Adding $1$ to both sides yields:
     $$
     x^2 + y^2 + 1 \ge 1 > 0 \quad \text{for all } (x, y) \in \mathbb{R}^2
     $$
   - The expression $x^2 + y^2 + 1$ has a strict global minimum of $1$ (achieved at $(x, y) = (0, 0)$).
   - Because $x^2 + y^2 + 1$ is strictly positive for every possible point in $\mathbb{R}^2$, it can never equal $0$.
   - Therefore, the solution set in the real plane contains zero points.

---

## 4. Verification and Consistency Checks

1. **Classification Summary Table:**

| Equation | Canonical Form | Quadratic Discriminant $AC$ | Real Geometric Object |
| :--- | :--- | :--- | :--- |
| $4x^2 + 9y^2 = 36$ | $\frac{x^2}{9} + \frac{y^2}{4} = 1$ | $4 \times 9 = 36 > 0$ | **Ellipse** ($a=3, b=2$) |
| $x^2 - y^2 = 1$ | $\frac{x^2}{1} - \frac{y^2}{1} = 1$ | $1 \times (-1) = -1 < 0$ | **Equilateral Hyperbola** ($a=b=1$) |
| $x^2 - 4y = 0$ | $x^2 = 4y$ | $1 \times 0 = 0$ | **Parabola** ($p=2$, opens $+y$) |
| $x^2 + y^2 + 1 = 0$ | $x^2 + y^2 = -1$ | $1 \times 1 = 1 > 0$, $R^2 < 0$ | **Empty Set $\emptyset$** (no real locus) |

2. **Parabola Points Check:**
   For $x^2 = 4y$:
   - At $x = 0 \implies y = 0 \implies (0, 0)$ is on the curve.
   - At $x = \pm 2 \implies y = \frac{4}{4} = 1 \implies (\pm 2, 1)$ are on the curve.
   - Distance from $(2, 1)$ to focus $(0, 1)$: $\sqrt{(2-0)^2 + (1-1)^2} = 2$.
   - Distance from $(2, 1)$ to directrix $y = -1$: $|1 - (-1)| = 2 \quad (\checkmark)$.
