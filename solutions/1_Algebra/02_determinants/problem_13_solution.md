# Solution to Exercise 13: Determinant by Elimination

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 5 & 7 \\ 1 & 0 & 2 \end{pmatrix}
$$

Compute $\det A$ using Gaussian elimination to reduce the matrix to upper-triangular form. Explicitly record the effect of every row operation used on the value of the determinant.

---

## 2. Theoretical Background and Concepts

1. **Gaussian Elimination and Determinants:**
   Gaussian elimination transforms a matrix into upper-triangular form using elementary row operations. Because the determinant of an upper-triangular matrix is simply the product of its diagonal entries, tracking how each row operation affects the determinant allows efficient computation:
   - **Row Addition ($R_i \leftarrow R_i + c R_j$):** Does not change the determinant ($\times 1$).
   - **Row Interchange ($R_i \leftrightarrow R_j$):** Multiplies the determinant by $-1$.
   - **Row Scaling ($R_i \leftarrow c R_i$):** Multiplies the determinant by $c$.

2. **Triangular Determinant Rule:**
   For any matrix in upper-triangular form $U = (u_{ij})$:
   $$
   \det U = u_{11} \cdot u_{22} \cdots u_{nn}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Eliminate the $(2, 1)$ Entry

Starting with:
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 5 & 7 \\ 1 & 0 & 2 \end{pmatrix}
$$

Subtract $2R_1$ from $R_2$:
$$
R_2 \leftarrow R_2 - 2R_1
$$
- **Effect on Determinant:** Adding a scalar multiple of Row 1 to Row 2 is a Type III row operation. **The determinant is unchanged:** $\det A_1 = \det A$.
- **Calculation:**
  $$
  R_2 - 2R_1 = \begin{pmatrix} 2 & 5 & 7 \end{pmatrix} - 2\begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} 2 - 2 & 5 - 4 & 7 - 6 \end{pmatrix} = \begin{pmatrix} 0 & 1 & 1 \end{pmatrix}
  $$

The matrix becomes:
$$
A_1 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 1 & 0 & 2 \end{pmatrix}
$$

---

### Step 2: Eliminate the $(3, 1)$ Entry

Subtract $R_1$ from $R_3$:
$$
R_3 \leftarrow R_3 - R_1
$$
- **Effect on Determinant:** Type III row operation. **The determinant is unchanged:** $\det A_2 = \det A_1 = \det A$.
- **Calculation:**
  $$
  R_3 - R_1 = \begin{pmatrix} 1 & 0 & 2 \end{pmatrix} - \begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} 1 - 1 & 0 - 2 & 2 - 3 \end{pmatrix} = \begin{pmatrix} 0 & -2 & -1 \end{pmatrix}
  $$

The matrix becomes:
$$
A_2 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & -2 & -1 \end{pmatrix}
$$

---

### Step 3: Eliminate the $(3, 2)$ Entry

Add $2R_2$ to $R_3$ using the pivot $1$ in Row 2:
$$
R_3 \leftarrow R_3 + 2R_2
$$
- **Effect on Determinant:** Type III row operation. **The determinant is unchanged:** $\det A_3 = \det A_2 = \det A$.
- **Calculation:**
  $$
  R_3 + 2R_2 = \begin{pmatrix} 0 & -2 & -1 \end{pmatrix} + 2\begin{pmatrix} 0 & 1 & 1 \end{pmatrix} = \begin{pmatrix} 0 & -2 + 2 & -1 + 2 \end{pmatrix} = \begin{pmatrix} 0 & 0 & 1 \end{pmatrix}
  $$

The matrix is now in upper-triangular form:
$$
A_3 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 0 & 1 \end{pmatrix}
$$

---

### Step 4: Evaluate the Determinant

Matrix $A_3$ is upper triangular. Its determinant is the product of its diagonal elements:
$$
\det A_3 = (1) \cdot (1) \cdot (1) = 1
$$

Since all row operations performed throughout the elimination process were Type III (row additions), the determinant was preserved at each step:
$$
\det A = \det A_1 = \det A_2 = \det A_3 = 1
$$

---

## 4. Verification and Consistency Checks

1. **Direct Calculation via Sarrus' Rule:**
   $$
   \begin{array}{ccc|cc}
   1 & 2 & 3 & 1 & 2 \\
   2 & 5 & 7 & 2 & 5 \\
   1 & 0 & 2 & 1 & 0
   \end{array}
   $$
   - Downward diagonal products:
     $$
     (1)(5)(2) + (2)(7)(1) + (3)(2)(0) = 10 + 14 + 0 = 24
     $$
   - Upward diagonal products:
     $$
     (1)(5)(3) + (0)(7)(1) + (2)(2)(2) = 15 + 0 + 8 = 23
     $$
   - Difference:
     $$
     \det A = 24 - 23 = 1 \quad \checkmark
     $$

2. **Cofactor Expansion Along Row 3:**
   Expanding along row 3 (which contains a zero entry):
   $$
   \det A = 1 \cdot \det\begin{pmatrix} 2 & 3 \\ 5 & 7 \end{pmatrix} - 0 + 2 \cdot \det\begin{pmatrix} 1 & 2 \\ 2 & 5 \end{pmatrix}
   $$
   - Minor 1: $(2)(7) - (3)(5) = 14 - 15 = -1$
   - Minor 2: $(1)(5) - (2)(2) = 5 - 4 = 1$
   - Value:
     $$
     \det A = 1(-1) + 2(1) = -1 + 2 = 1 \quad \checkmark
     $$
