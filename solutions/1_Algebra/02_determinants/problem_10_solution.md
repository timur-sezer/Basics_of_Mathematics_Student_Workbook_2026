# Solution to Exercise 10: Detecting Dependence

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 5 \end{pmatrix}
$$

1. Without carrying out a full determinant calculation, explain why $\det A = 0$.
2. Identify the specific linear dependence relationship between the rows.
3. Connect this linear dependence with the non-invertibility of the matrix.

---

## 2. Theoretical Background and Concepts

1. **Linear Dependence of Rows:**
   A set of row vectors $\{\mathbf{r}_1, \mathbf{r}_2, \dots, \mathbf{r}_n\}$ is **linearly dependent** if there exist scalars $c_1, c_2, \dots, c_n$, not all zero, such that:
   $$
   c_1 \mathbf{r}_1 + c_2 \mathbf{r}_2 + \dots + c_n \mathbf{r}_n = \mathbf{0}
   $$

2. **Determinants and Linear Dependence:**
   A square matrix has a determinant of zero if and only if its rows (or columns) are linearly dependent:
   $$
   \det(A) = 0 \iff \text{rows of } A \text{ are linearly dependent}
   $$
   If two rows are proportional ($R_j = c R_i$), subtracting $c R_i$ from $R_j$ creates a row entirely consisting of zeros without changing the determinant. Expanding along an all-zero row immediately evaluates to zero.

3. **Rank and Invertibility:**
   For an $n \times n$ matrix $A$:
   $$
   A \text{ is invertible} \iff \operatorname{rank}(A) = n \iff \det(A) \ne 0
   $$
   If the rows are linearly dependent, $\operatorname{rank}(A) < n$. The matrix is singular, its kernel is non-trivial ($\ker A \ne \{\mathbf{0}\}$), and no inverse matrix $A^{-1}$ exists.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Linear Dependence Between the Rows

Let the row vectors of matrix $A$ be:
$$
\mathbf{r}_1 = \begin{pmatrix} 1 & 2 & 3 \end{pmatrix}
$$
$$
\mathbf{r}_2 = \begin{pmatrix} 2 & 4 & 6 \end{pmatrix}
$$
$$
\mathbf{r}_3 = \begin{pmatrix} 0 & 1 & 5 \end{pmatrix}
$$

Comparing Row 1 and Row 2:
$$
\mathbf{r}_2 = 2 \cdot \mathbf{r}_1 = \begin{pmatrix} 2(1) & 2(2) & 2(3) \end{pmatrix} = \begin{pmatrix} 2 & 4 & 6 \end{pmatrix}
$$

Thus, Row 2 is an exact scalar multiple (double) of Row 1.
The explicit non-trivial linear dependence relation is:
$$
2 \mathbf{r}_1 - \mathbf{r}_2 + 0 \mathbf{r}_3 = \mathbf{0}
$$
where the coefficients $(2, -1, 0)$ are not all zero.

---

### Step 2: Conclude Why $\det A = 0$ Without Full Expansion

1. By the property of determinants, adding a multiple of one row to another row leaves the determinant unchanged.
2. Applying the elementary row operation $R_2 \leftarrow R_2 - 2R_1$:
   $$
   \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 5 \end{pmatrix} \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & 0 \\ 0 & 1 & 5 \end{pmatrix}
   $$
3. The resulting matrix has an entire row of zeros. Expanding the determinant along the second row:
   $$
   \det A = 0 \cdot C_{21} + 0 \cdot C_{22} + 0 \cdot C_{23} = 0
   $$
Therefore, $\det A = 0$ directly from structural observation.

---

### Step 3: Connection with Non-Invertibility

1. **Rank Deficency:**
   Because row 2 provides no new dimensional direction beyond row 1, the row space of $A$ is spanned by only two independent vectors ($\mathbf{r}_1$ and $\mathbf{r}_3$). Therefore:
   $$
   \operatorname{rank}(A) \le 2 < 3
   $$
   An $n \times n$ matrix must have full rank $n$ (here $3$) to be invertible.

2. **Non-Trivial Kernel (Lack of Injectivity):**
   Since the rows are linearly dependent, the columns are also linearly dependent. There exists a non-zero vector $x \ne 0$ such that $Ax = 0$.
   For instance, solving $Ax = 0$ yields non-zero solutions (e.g., $x = \begin{pmatrix} 7 \\ -5 \\ 1 \end{pmatrix}$).
   Because distinct vectors map to the same image, $A$ is not one-to-one and cannot be inverted.

3. **Invertible Matrix Theorem Equivalence:**
   Since $\det A = 0$, the inverse formula $A^{-1} = \frac{1}{\det A} \operatorname{adj}(A)$ requires dividing by zero, which is undefined. Hence, $A$ is not invertible.

---

## 4. Verification and Consistency Checks

1. **Direct Sarrus' Rule Check:**
   $$
   \begin{array}{ccc|cc}
   1 & 2 & 3 & 1 & 2 \\
   2 & 4 & 6 & 2 & 4 \\
   0 & 1 & 5 & 0 & 1
   \end{array}
   $$
   - Downward diagonals:
     $(1)(4)(5) + (2)(6)(0) + (3)(2)(1) = 20 + 0 + 6 = 26$.
   - Upward diagonals:
     $(0)(4)(3) + (1)(6)(1) + (5)(2)(2) = 0 + 6 + 20 = 26$.
   - Difference:
     $$
     \det A = 26 - 26 = 0 \quad \checkmark
     $$

2. **Nullspace Vector Check:**
   Multiply $A$ by $x = \begin{pmatrix} 7 \\ -5 \\ 1 \end{pmatrix}$:
   $$
   \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 5 \end{pmatrix} \begin{pmatrix} 7 \\ -5 \\ 1 \end{pmatrix} = \begin{pmatrix} 1(7) + 2(-5) + 3(1) \\ 2(7) + 4(-5) + 6(1) \\ 0(7) + 1(-5) + 5(1) \end{pmatrix} = \begin{pmatrix} 7 - 10 + 3 \\ 14 - 20 + 6 \\ 0 - 5 + 5 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix} \quad \checkmark
   $$
   This explicitly confirms that $A$ is singular and non-invertible.

