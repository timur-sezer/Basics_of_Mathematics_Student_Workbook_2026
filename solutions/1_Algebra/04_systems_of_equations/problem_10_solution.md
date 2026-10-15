# Solution to Exercise 10: A Polynomial Through Three Points

## 1. Problem Statement

Find a quadratic polynomial
$$
p(x) = ax^2 + bx + c
$$
whose graph passes through the three points $(0, 1)$, $(1, 3)$, and $(2, 9)$.

1. Reduce the polynomial interpolation problem to a system of linear equations in the unknowns $a, b, c$.
2. Solve the linear system using Gaussian elimination.
3. Verify the final polynomial by evaluating it at all three given points.

---

## 2. Theoretical Background and Concepts

1. **Polynomial Interpolation as a Linear System:**
   For a polynomial $p(x) = \sum_{k=0}^n c_k x^k$, each interpolation condition $p(x_i) = y_i$ is strictly linear with respect to the unknown coefficients $c_0, c_1, \dots, c_n$, because the powers $x_i^k$ are known constants.

2. **The Vandermonde Matrix:**
   Given $n+1$ distinct interpolation nodes $x_0, x_1, \dots, x_n$, the resulting linear system has the form:
   $$
   V \begin{pmatrix} c \\ b \\ a \end{pmatrix} = \begin{pmatrix} y_0 \\ y_1 \\ y_2 \end{pmatrix}, \quad \text{where } V = \begin{pmatrix} 1 & x_0 & x_0^2 \\ 1 & x_1 & x_1^2 \\ 1 & x_2 & x_2^2 \end{pmatrix}
   $$
   The determinant of a Vandermonde matrix is given by $\det(V) = \prod_{0 \le i < j \le n} (x_j - x_i)$. Since the $x$-coordinates are pairwise distinct ($0 \ne 1 \ne 2$), $\det(V) \ne 0$. Therefore, the interpolating polynomial of degree at most $2$ is mathematically guaranteed to exist and be unique.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up the System of Linear Equations

Substitute each given point $(x, y)$ into $p(x) = ax^2 + bx + c$:

1. **Point $(0, 1)$:**
   $$
   p(0) = a(0)^2 + b(0) + c = 1 \implies c = 1
   $$
2. **Point $(1, 3)$:**
   $$
   p(1) = a(1)^2 + b(1) + c = 3 \implies a + b + c = 3
   $$
3. **Point $(2, 9)$:**
   $$
   p(2) = a(2)^2 + b(2) + c = 9 \implies 4a + 2b + c = 9
   $$

Writing in standard order for unknowns $(a, b, c)$:
$$
\begin{cases}
c = 1, \\
a + b + c = 3, \\
4a + 2b + c = 9.
\end{cases}
$$

---

### Step 2: Matrix Representation and Elimination

Write the augmented matrix with columns corresponding to $a, b, c$:
$$
[A \mid y] = \left(\begin{array}{ccc|c}
0 & 0 & 1 & 1 \\
1 & 1 & 1 & 3 \\
4 & 2 & 1 & 9
\end{array}\right)
$$

1. **Permute rows to bring a non-zero pivot to the top ($R_1 \leftrightarrow R_2$):**
   $$
   \left(\begin{array}{ccc|c}
   1 & 1 & 1 & 3 \\
   0 & 0 & 1 & 1 \\
   4 & 2 & 1 & 9
   \end{array}\right)
   $$

2. **Interchange Row 2 and Row 3 ($R_2 \leftrightarrow R_3$) to establish triangular order:**
   $$
   \left(\begin{array}{ccc|c}
   1 & 1 & 1 & 3 \\
   4 & 2 & 1 & 9 \\
   0 & 0 & 1 & 1
   \end{array}\right)
   $$

3. **Eliminate the entry in the first column of Row 2 ($R_2 \leftarrow R_2 - 4R_1$):**
   - Left side: $\begin{pmatrix} 4 & 2 & 1 \end{pmatrix} - 4\begin{pmatrix} 1 & 1 & 1 \end{pmatrix} = \begin{pmatrix} 0 & -2 & -3 \end{pmatrix}$
   - Right side: $9 - 4(3) = 9 - 12 = -3$

   The augmented matrix in row echelon form is:
   $$
   \left(\begin{array}{ccc|c}
   1 & 1 & 1 & 3 \\
   0 & -2 & -3 & -3 \\
   0 & 0 & 1 & 1
   \end{array}\right)
   $$

---

### Step 3: Back-Substitution

1. **From Row 3:**
   $$
   c = 1
   $$

2. **Substitute $c = 1$ into Row 2:**
   $$
   -2b - 3(1) = -3 \implies -2b - 3 = -3 \implies -2b = 0 \implies b = 0
   $$

3. **Substitute $b = 0$ and $c = 1$ into Row 1:**
   $$
   a + 0 + 1 = 3 \implies a = 2
   $$

Thus, the coefficients are:
$$
a = 2, \quad b = 0, \quad c = 1
$$

The required polynomial is:
$$
p(x) = 2x^2 + 1
$$

---

## 4. Verification and Consistency Checks

Substitute each given node into $p(x) = 2x^2 + 1$:

1. **Node 1 $(x = 0)$:**
   $$
   p(0) = 2(0)^2 + 1 = 0 + 1 = 1 \quad (\checkmark \text{passes through } (0, 1))
   $$

2. **Node 2 $(x = 1)$:**
   $$
   p(1) = 2(1)^2 + 1 = 2(1) + 1 = 3 \quad (\checkmark \text{passes through } (1, 3))
   $$

3. **Node 3 $(x = 2)$:**
   $$
   p(2) = 2(2)^2 + 1 = 2(4) + 1 = 8 + 1 = 9 \quad (\checkmark \text{passes through } (2, 9))
   $$

4. **Vandermonde Determinant Check:**
   With nodes $x_0 = 0, x_1 = 1, x_2 = 2$:
   $$
   \det(V) = (x_1 - x_0)(x_2 - x_0)(x_2 - x_1) = (1 - 0)(2 - 0)(2 - 1) = 1 \times 2 \times 1 = 2 \ne 0
   $$
   Because $\det(V) \ne 0$, the solution $(a, b, c) = (2, 0, 1)$ is rigorously unique.
