# Solution to Exercise 12: A Parameter Revealed by a Row Operation

## 1. Problem Statement

Given the parameter-dependent matrix:
$$
A(t) = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & t \\ 0 & 1 & 1 \end{pmatrix}
$$

1. Perform the preliminary row operation $R_2 \leftarrow R_2 - 2R_1$ before evaluating the determinant.
2. Use the resulting structure to compute $\det A(t)$.
3. Find all values of $t$ for which $A(t)$ is not invertible.
4. Explain what special structural property occurs among the rows of the original matrix for the critical value of $t$ found.

---

## 2. Theoretical Background and Concepts

1. **Row Operation Invariance:**
   The Type III elementary row operation:
   $$
   R_2 \leftarrow R_2 - 2R_1
   $$
   does not change the value of the determinant:
   $$
   \det A(t) = \det(A_1(t))
   $$

2. **Invertibility and Determinant:**
   A square matrix is not invertible (singular) if and only if its determinant is zero:
   $$
   A(t) \text{ is not invertible} \iff \det A(t) = 0
   $$

3. **Linear Dependence of Rows:**
   A zero determinant implies that the rows of the matrix are linearly dependent. In particular, if a row operation creates an all-zero row, that row was originally a linear combination of the other rows.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Perform the Row Operation $R_2 \leftarrow R_2 - 2R_1$

Starting with:
$$
A(t) = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & t \\ 0 & 1 & 1 \end{pmatrix}
$$

Subtract $2R_1$ from $R_2$:
$$
R_2 - 2R_1 = \begin{pmatrix} 2 & 4 & t \end{pmatrix} - 2\begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} 2 - 2 & 4 - 4 & t - 6 \end{pmatrix} = \begin{pmatrix} 0 & 0 & t - 6 \end{pmatrix}
$$

The matrix becomes:
$$
A_1(t) = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & t - 6 \\ 0 & 1 & 1 \end{pmatrix}
$$

Because this is a Type III operation, $\det A(t) = \det A_1(t)$.

---

### Step 2: Compute $\det A_1(t)$ Using the Resulting Structure

The second row of $A_1(t)$, $\begin{pmatrix} 0 & 0 & t - 6 \end{pmatrix}$, has zeros in the first two positions.
We expand along **Row 2**:
$$
\det A_1(t) = 0 \cdot C_{21} + 0 \cdot C_{22} + (t - 6) \cdot (-1)^{2+3} \det\begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}
$$

Evaluate the $2 \times 2$ minor:
$$
\det\begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} = (1)(1) - (2)(0) = 1
$$

Substitute back:
$$
\det A(t) = (t - 6) \cdot (-1) \cdot (1) = -(t - 6) = 6 - t
$$

---

### Step 3: Find Values of $t$ for Non-Invertibility

Matrix $A(t)$ is not invertible if and only if $\det A(t) = 0$:
$$
6 - t = 0 \implies t = 6
$$

Thus, $A(t)$ is not invertible if and only if **$t = 6$**.

---

### Step 4: Explanation of What Happens to the Rows When $t = 6$

When $t = 6$:
1. Substitute $t = 6$ into the original matrix:
   $$
   A(6) = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 1 \end{pmatrix}
   $$
2. Inspect the relationship between Row 1 and Row 2:
   $$
   R_2 = \begin{pmatrix} 2 & 4 & 6 \end{pmatrix} = 2 \begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = 2 R_1
   $$
   **The second row is an exact scalar multiple of the first row.**
3. In the simplified matrix $A_1(6)$, setting $t = 6$ causes Row 2 to become entirely zero: $\begin{pmatrix} 0 & 0 & 0 \end{pmatrix}$.
4. Consequently, the three rows are linearly dependent ($2R_1 - R_2 = \mathbf{0}$), reducing the rank of the matrix to $2 < 3$. This linear dependence is the exact geometric and algebraic reason why the matrix loses invertibility at $t = 6$.

---

## 4. Verification and Consistency Checks

1. **Direct Sarrus' Rule Verification:**
   $$
   \begin{array}{ccc|cc}
   1 & 2 & 3 & 1 & 2 \\
   2 & 4 & t & 2 & 4 \\
   0 & 1 & 1 & 0 & 1
   \end{array}
   $$
   - Downward diagonals:
     $$
     (1)(4)(1) + (2)(t)(0) + (3)(2)(1) = 4 + 0 + 6 = 10
     $$
   - Upward diagonals:
     $$
     (0)(4)(3) + (1)(t)(1) + (1)(2)(2) = 0 + t + 4 = t + 4
     $$
   - Difference:
     $$
     \det A(t) = 10 - (t + 4) = 6 - t \quad \checkmark
     $$
   Matches the result from the row operation method.

2. **Test of Invertible Value ($t = 0$):**
   - For $t = 0$: $\det A(0) = 6 - 0 = 6 \ne 0 \implies A(0)$ is invertible.
   - For $t = 6$: $\det A(6) = 6 - 6 = 0 \implies A(6)$ is singular.
