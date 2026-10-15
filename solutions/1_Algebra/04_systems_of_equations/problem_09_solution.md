# Solution to Exercise 9: A System from a Sum Condition

## 1. Problem Statement

Find real numbers $x$ and $y$ satisfying the system:
$$
\begin{cases}
x + y = 10, \\
2x + 5y = 32.
\end{cases}
$$

Solve the system using Gaussian elimination and explain geometrically why the solution is unique.

---

## 2. Theoretical Background and Concepts

1. **Linear Systems and Geometry of Lines:**
   In $\mathbb{R}^2$, each linear equation $a_i x + b_i y = c_i$ (with $(a_i, b_i) \ne (0,0)$) defines a straight line.
   - The solution set of the system corresponds to the intersection of the two lines.
   - If the lines have distinct slopes ($m_1 \ne m_2$), their direction vectors (and normal vectors) are linearly independent.
   - Non-parallel lines in the Euclidean plane intersect at **exactly one point**, corresponding to a unique solution.

2. **Algebraic Invertibility Condition:**
   For a $2 \times 2$ system $Ax = b$, a unique solution exists if and only if:
   $$
   \det(A) = a_{11} a_{22} - a_{12} a_{21} \ne 0
   $$
   which is algebraically equivalent to stating that the rows (and columns) of $A$ are not scalar multiples of one another.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up the Augmented Matrix

Represent the system in augmented matrix form:
$$
[A \mid b] = \left(\begin{array}{cc|c}
1 & 1 & 10 \\
2 & 5 & 32
\end{array}\right)
$$

---

### Step 2: Gaussian Elimination

1. **Eliminate the $x$-coefficient in Row 2:**
   Apply the elementary row operation $R_2 \leftarrow R_2 - 2R_1$:
   - Left side: $\begin{pmatrix} 2 & 5 \end{pmatrix} - 2\begin{pmatrix} 1 & 1 \end{pmatrix} = \begin{pmatrix} 2 - 2 & 5 - 2 \end{pmatrix} = \begin{pmatrix} 0 & 3 \end{pmatrix}$
   - Right side: $32 - 2(10) = 32 - 20 = 12$

   The resulting row echelon form is:
   $$
   \left(\begin{array}{cc|c}
   1 & 1 & 10 \\
   0 & 3 & 12
   \end{array}\right)
   $$

2. **Normalize Row 2 ($R_2 \leftarrow \frac{1}{3}R_2$):**
   $$
   \left(\begin{array}{cc|c}
   1 & 1 & 10 \\
   0 & 1 & 4
   \end{array}\right)
   $$

---

### Step 3: Back-Substitution

1. **Solve for $y$ from Row 2:**
   $$
   y = 4
   $$

2. **Substitute $y = 4$ into Row 1:**
   $$
   x + y = 10 \implies x + 4 = 10 \implies x = 6
   $$

Thus, the unique algebraic solution is:
$$
\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 6 \\ 4 \end{pmatrix}
$$

---

### Step 4: Geometric Interpretation of Uniqueness

1. **Slope-Intercept Form of the Equations:**
   - **Line 1 ($L_1$):**
     $$
     x + y = 10 \implies y = -x + 10
     $$
     Slope: $m_1 = -1$, $y$-intercept: $(0, 10)$, $x$-intercept: $(10, 0)$.
   - **Line 2 ($L_2$):**
     $$
     2x + 5y = 32 \implies 5y = -2x + 32 \implies y = -\frac{2}{5}x + \frac{32}{5} = -0.4x + 6.4
     $$
     Slope: $m_2 = -\frac{2}{5} = -0.4$, $y$-intercept: $(0, 6.4)$, $x$-intercept: $(16, 0)$.

2. **Geometric Argument:**
   - The slopes of the two lines are strictly different:
     $$
     m_1 = -1 \ne -0.4 = m_2
     $$
   - Since $m_1 \ne m_2$, the lines are **not parallel**.
   - In two-dimensional Euclidean geometry, any two lines that are not parallel must intersect, and they intersect at **precisely one point**.
   - The normal vectors to the lines are $n_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$ and $n_2 = \begin{pmatrix} 2 \\ 5 \end{pmatrix}$. The determinant of the coefficient matrix formed by these normals is:
     $$
     \det(A) = (1)(5) - (1)(2) = 5 - 2 = 3 \ne 0
     $$
     Because $\det(A) \ne 0$, the normal vectors are linearly independent, guaranteeing that the lines cross transversely at the single point $(6, 4)$.

---

## 4. Verification and Consistency Checks

1. **Algebraic Substitution:**
   - Equation 1: $x + y = 6 + 4 = 10$ ($\checkmark$ matches RHS)
   - Equation 2: $2x + 5y = 2(6) + 5(4) = 12 + 20 = 32$ ($\checkmark$ matches RHS)

2. **Linear Combination Form Check:**
   $$
   x \begin{pmatrix} 1 \\ 2 \end{pmatrix} + y \begin{pmatrix} 1 \\ 5 \end{pmatrix} = 6 \begin{pmatrix} 1 \\ 2 \end{pmatrix} + 4 \begin{pmatrix} 1 \\ 5 \end{pmatrix} = \begin{pmatrix} 6 \\ 12 \end{pmatrix} + \begin{pmatrix} 4 \\ 20 \end{pmatrix} = \begin{pmatrix} 10 \\ 32 \end{pmatrix} \quad (\checkmark)
   $$
