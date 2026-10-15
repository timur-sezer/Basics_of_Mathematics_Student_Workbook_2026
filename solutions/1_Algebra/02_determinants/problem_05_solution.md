# Solution to Exercise 5: Row Operations

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 1 & 0 \\ -1 & 4 & 2 \end{pmatrix}
$$

Find $\det A$ by reducing the matrix to upper-triangular form using elementary row operations. At each step, explicitly indicate whether and how the determinant changes.

---

## 2. Theoretical Background and Concepts

The three elementary row operations affect the determinant of a matrix as follows:
1. **Type I (Row Swap):** Interchanging two rows changes the sign of the determinant:
   $$
   R_i \leftrightarrow R_j \implies \det(A_{\text{new}}) = -\det(A_{\text{old}})
   $$
2. **Type II (Row Scaling):** Multiplying a row by a scalar $c \ne 0$ scales the determinant by $c$:
   $$
   R_i \leftarrow c R_i \implies \det(A_{\text{new}}) = c \cdot \det(A_{\text{old}})
   $$
3. **Type III (Row Addition):** Adding a scalar multiple of one row to another row **leaves the determinant completely unchanged**:
   $$
   R_i \leftarrow R_i + c R_j \quad (i \ne j) \implies \det(A_{\text{new}}) = \det(A_{\text{old}})
   $$

By systematically applying Type III operations to eliminate sub-diagonal entries, we can reduce any square matrix to upper-triangular form without altering the determinant's value.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Eliminate the $(2, 1)$ entry

Perform the operation:
$$
R_2 \leftarrow R_2 - 2R_1
$$
- **Effect on Determinant:** This is a Type III row operation (adding a multiple of row 1 to row 2). **The determinant does not change:** $\det A_1 = \det A$.

Computing the new second row:
$$
R_2 - 2R_1 = \begin{pmatrix} 2 & 1 & 0 \end{pmatrix} - 2\begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} 2 - 2 & 1 - 4 & 0 - 6 \end{pmatrix} = \begin{pmatrix} 0 & -3 & -6 \end{pmatrix}
$$

The matrix becomes:
$$
A_1 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ -1 & 4 & 2 \end{pmatrix}
$$

---

### Step 2: Eliminate the $(3, 1)$ entry

Perform the operation:
$$
R_3 \leftarrow R_3 + R_1
$$
- **Effect on Determinant:** This is a Type III row operation. **The determinant does not change:** $\det A_2 = \det A_1 = \det A$.

Computing the new third row:
$$
R_3 + R_1 = \begin{pmatrix} -1 & 4 & 2 \end{pmatrix} + \begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} -1 + 1 & 4 + 2 & 2 + 3 \end{pmatrix} = \begin{pmatrix} 0 & 6 & 5 \end{pmatrix}
$$

The matrix becomes:
$$
A_2 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ 0 & 6 & 5 \end{pmatrix}
$$

---

### Step 3: Eliminate the $(3, 2)$ entry

To eliminate the entry $6$ in position $(3, 2)$ using the pivot $-3$ in row 2, add $2 R_2$ to $R_3$:
$$
R_3 \leftarrow R_3 + 2R_2
$$
- **Effect on Determinant:** This is a Type III row operation. **The determinant does not change:** $\det A_3 = \det A_2 = \det A$.

Computing the new third row:
$$
R_3 + 2R_2 = \begin{pmatrix} 0 & 6 & 5 \end{pmatrix} + 2\begin{pmatrix} 0 & -3 & -6 \end{pmatrix} = \begin{pmatrix} 0 & 6 - 6 & 5 - 12 \end{pmatrix} = \begin{pmatrix} 0 & 0 & -7 \end{pmatrix}
$$

The matrix is now in upper-triangular form:
$$
A_3 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ 0 & 0 & -7 \end{pmatrix}
$$

---

### Step 4: Evaluate the Determinant

Matrix $A_3$ is upper triangular, so its determinant is simply the product of its diagonal elements:
$$
\det A_3 = (1) \cdot (-3) \cdot (-7) = 21
$$

Since every row operation performed was of Type III, none of them altered the determinant:
$$
\det A = \det A_1 = \det A_2 = \det A_3 = 21
$$

---

## 4. Verification and Consistency Checks

1. **Independent Calculation via Sarrus' Rule:**
   $$
   \begin{array}{ccc|cc}
   1 & 2 & 3 & 1 & 2 \\
   2 & 1 & 0 & 2 & 1 \\
   -1 & 4 & 2 & -1 & 4
   \end{array}
   $$
   - Downward diagonal products:
     $$
     (1)(1)(2) + (2)(0)(-1) + (3)(2)(4) = 2 + 0 + 24 = 26
     $$
   - Upward diagonal products:
     $$
     (-1)(1)(3) + (4)(0)(1) + (2)(2)(2) = -3 + 0 + 8 = 5
     $$
   - Value:
     $$
     \det A = 26 - 5 = 21 \quad \checkmark
     $$

2. **Cofactor Expansion Along Row 2 (having a zero):**
   $$
   \det A = -2 \det\begin{pmatrix} 2 & 3 \\ 4 & 2 \end{pmatrix} + 1 \det\begin{pmatrix} 1 & 3 \\ -1 & 2 \end{pmatrix} - 0
   $$
   $$
   \det\begin{pmatrix} 2 & 3 \\ 4 & 2 \end{pmatrix} = 4 - 12 = -8
   $$
   $$
   \det\begin{pmatrix} 1 & 3 \\ -1 & 2 \end{pmatrix} = 2 - (-3) = 5
   $$
   $$
   \det A = -2(-8) + 1(5) = 16 + 5 = 21 \quad \checkmark
   $$
