# Solution to Exercise 1: From a System to a Matrix

## 1. Problem Statement

Given the linear system of equations:
$$
\begin{cases}
2x - y + z = 4, \\
x + 3y - 2z = 1, \\
3x + y + z = 7.
\end{cases}
$$

1. Write the system in matrix-vector form:
   $$
   Ax = b
   $$
2. Identify the coefficient matrix $A$, the vector of unknowns $x$, and the right-hand side vector $b$.
3. Explain how each row of the coefficient matrix corresponds to one equation in the system.

---

## 2. Theoretical Background and Concepts

1. **Matrix Form of a Linear System ($Ax = b$):**
   A system of $m$ linear equations in $n$ variables:
   $$
   \begin{cases}
   a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = b_1 \\
   a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n = b_2 \\
   \quad \vdots \\
   a_{m1}x_1 + a_{m2}x_2 + \cdots + a_{mn}x_n = b_m
   \end{cases}
   $$
   can be compactly encoded as the matrix equation $Ax = b$, where:
   - $A \in \mathbb{R}^{m \times n}$ is the **coefficient matrix**, whose entry $a_{ij}$ is the scalar multiplying variable $x_j$ in equation $i$.
   - $x \in \mathbb{R}^{n \times 1}$ is the **column vector of unknowns**.
   - $b \in \mathbb{R}^{m \times 1}$ is the **right-hand side column vector** of constants.

2. **Row Correspondence via Dot Product:**
   By the definition of matrix-vector multiplication, the $i$-th entry of the product $Ax$ is the dot product of the $i$-th row of $A$, denoted $\mathbf{r}_i(A)$, with the vector of unknowns $x$:
   $$
   (Ax)_i = \mathbf{r}_i(A) \cdot x = a_{i1}x_1 + a_{i2}x_2 + \cdots + a_{in}x_n
   $$
   Setting $(Ax)_i = b_i$ exactly reproduces the $i$-th scalar equation.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Align the Variables

Write the equations with all variables $x, y, z$ in identical order, explicitly writing implied coefficients of $\pm 1$:
$$
\begin{cases}
(2)x + (-1)y + (1)z = 4 \\
(1)x + (3)y + (-2)z = 1 \\
(3)x + (1)y + (1)z = 7
\end{cases}
$$

---

### Step 2: Identify the Matrix and Vectors

1. **Coefficient Matrix $A$ ($3 \times 3$):**
   Extract the coefficients of $x, y, z$ row-by-row:
   $$
   A = \begin{pmatrix}
   2 & -1 & 1 \\
   1 & 3 & -2 \\
   3 & 1 & 1
   \end{pmatrix}
   $$

2. **Vector of Unknowns $x$ ($3 \times 1$):**
   $$
   x = \begin{pmatrix} x \\ y \\ z \end{pmatrix}
   $$

3. **Right-Hand Side Vector $b$ ($3 \times 1$):**
   Extract the constants from the right-hand sides:
   $$
   b = \begin{pmatrix} 4 \\ 1 \\ 7 \end{pmatrix}
   $$

---

### Step 3: Write in $Ax = b$ Form

Combining these into matrix-vector form:
$$
\begin{pmatrix}
2 & -1 & 1 \\
1 & 3 & -2 \\
3 & 1 & 1
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}
=
\begin{pmatrix}
4 \\
1 \\
7
\end{pmatrix}
$$

---

### Step 4: Explanation of the Row Correspondence

Each row of matrix $A$ encapsulates the linear weights of the corresponding equation:
- **Row 1:** $\begin{pmatrix} 2 & -1 & 1 \end{pmatrix} \cdot \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 2x - y + z$.
  Equating this to the first entry of $b$ gives $2x - y + z = 4$ (Equation 1).
- **Row 2:** $\begin{pmatrix} 1 & 3 & -2 \end{pmatrix} \cdot \begin{pmatrix} x \\ y \\ z \end{pmatrix} = x + 3y - 2z$.
  Equating this to the second entry of $b$ gives $x + 3y - 2z = 1$ (Equation 2).
- **Row 3:** $\begin{pmatrix} 3 & 1 & 1 \end{pmatrix} \cdot \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 3x + y + z$.
  Equating this to the third entry of $b$ gives $3x + y + z = 7$ (Equation 3).

Thus, each horizontal row of $A$ together with the corresponding entry of $b$ represents a hyperplane in $\mathbb{R}^3$, and the system seeks the intersection of these three hyperplanes.

---

## 4. Verification and Consistency Checks

1. **Dimensional Consistency:**
   - $\text{size}(A) = 3 \times 3$
   - $\text{size}(x) = 3 \times 1$
   - $\text{size}(Ax) = (3 \times 3) \times (3 \times 1) = 3 \times 1$
   - $\text{size}(b) = 3 \times 1$
   The dimensions match on both sides of $Ax = b$.

2. **Expansion Verification:**
   Performing standard matrix multiplication:
   $$
   Ax = \begin{pmatrix} 2(x) + (-1)(y) + 1(z) \\ 1(x) + 3(y) + (-2)(z) \\ 3(x) + 1(y) + 1(z) \end{pmatrix} = \begin{pmatrix} 2x - y + z \\ x + 3y - 2z \\ 3x + y + z \end{pmatrix}
   $$
   Setting $Ax = b$ precisely recovers the original three equations.
