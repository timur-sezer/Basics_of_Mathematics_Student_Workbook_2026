# Solution to Exercise 2: Determinant of a 3×3 Matrix

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 4 \\ 2 & 1 & 5 \end{pmatrix}
$$

1. Compute $\det A$ using Sarrus' rule.
2. Perform a check of the result using a chosen property of the determinant (e.g., Laplace expansion along a row or column).

---

## 2. Theoretical Background and Concepts

1. **Sarrus' Rule for $3 \times 3$ Determinants:**
   Sarrus' rule is a mnemonic device applicable exclusively to $3 \times 3$ matrices:
   $$
   \det \begin{pmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{pmatrix}
   $$
   By repeating the first two columns to the right, the determinant is computed by summing the products along the three main downward diagonals and subtracting the products along the three upward anti-diagonals:
   $$
   \det A = (a_{11}a_{22}a_{33} + a_{12}a_{23}a_{31} + a_{13}a_{21}a_{32}) - (a_{13}a_{22}a_{31} + a_{11}a_{23}a_{32} + a_{12}a_{21}a_{33})
   $$

2. **Laplace Expansion (Cofactor Expansion):**
   The determinant can also be computed by expanding along any row $i$ or column $j$:
   $$
   \det A = \sum_{k=1}^3 (-1)^{i+k} a_{ik} M_{ik}
   $$
   where $M_{ik}$ is the $(2 \times 2)$ minor determinant formed by deleting row $i$ and column $k$. Choosing a row or column with zero entries significantly simplifies the calculation.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $\det A$ Using Sarrus' Rule

Write matrix $A$ and append its first two columns:
$$
\begin{array}{ccc|cc}
1 & 2 & -1 & 1 & 2 \\
0 & 3 & 4 & 0 & 3 \\
2 & 1 & 5 & 2 & 1
\end{array}
$$

1. **Downward Diagonals (positive terms):**
   - First diagonal: $(1) \cdot (3) \cdot (5) = 15$
   - Second diagonal: $(2) \cdot (4) \cdot (2) = 16$
   - Third diagonal: $(-1) \cdot (0) \cdot (1) = 0$
   $$
   \text{Sum of downward products} = 15 + 16 + 0 = 31
   $$

2. **Upward Diagonals (negative terms):**
   - First anti-diagonal: $(2) \cdot (3) \cdot (-1) = -6$
   - Second anti-diagonal: $(1) \cdot (4) \cdot (1) = 4$
   - Third anti-diagonal: $(5) \cdot (0) \cdot (2) = 0$
   $$
   \text{Sum of upward products} = -6 + 4 + 0 = -2
   $$

3. **Subtract the Upward Sum from the Downward Sum:**
   $$
   \det A = 31 - (-2) = 31 + 2 = 33
   $$

---

### Step 2: Verification Check via Laplace Expansion

To verify the result using a determinant property, we perform cofactor expansion along the **first column** of $A$, as it contains a convenient zero entry ($a_{21} = 0$):
$$
A = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 4 \\ 2 & 1 & 5 \end{pmatrix}
$$

Expanding along Column 1:
$$
\det A = 1 \cdot (-1)^{1+1} \det\begin{pmatrix} 3 & 4 \\ 1 & 5 \end{pmatrix} + 0 \cdot (-1)^{2+1} \det\begin{pmatrix} 2 & -1 \\ 1 & 5 \end{pmatrix} + 2 \cdot (-1)^{3+1} \det\begin{pmatrix} 2 & -1 \\ 3 & 4 \end{pmatrix}
$$

Evaluate each $2 \times 2$ minor:
- Minor for entry $a_{11}$:
  $$
  \det\begin{pmatrix} 3 & 4 \\ 1 & 5 \end{pmatrix} = (3)(5) - (4)(1) = 15 - 4 = 11
  $$
- Minor for entry $a_{31}$:
  $$
  \det\begin{pmatrix} 2 & -1 \\ 3 & 4 \end{pmatrix} = (2)(4) - (-1)(3) = 8 - (-3) = 11
  $$

Substitute the minor values back into the expansion:
$$
\det A = 1 \cdot (11) - 0 + 2 \cdot (11) = 11 + 22 = 33
$$

Both methods yield exactly **$33$**.

---

## 4. Verification and Consistency Checks

1. **Row Operation Verification (Gaussian Elimination):**
   Subtract $2 R_1$ from $R_3$ (which preserves the determinant):
   $$
   R_3 \leftarrow R_3 - 2R_1 = \begin{pmatrix} 2 & 1 & 5 \end{pmatrix} - 2\begin{pmatrix} 1 & 2 & -1 \end{pmatrix} = \begin{pmatrix} 0 & -3 & 7 \end{pmatrix}
   $$
   The resulting matrix is:
   $$
   A' = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 4 \\ 0 & -3 & 7 \end{pmatrix}
   $$
   Add Row 2 to Row 3 ($R_3 \leftarrow R_3 + R_2$, preserving the determinant):
   $$
   A'' = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 4 \\ 0 & 0 & 11 \end{pmatrix}
   $$
   Since $A''$ is upper-triangular, its determinant is the product of diagonal elements:
   $$
   \det A = \det A'' = 1 \cdot 3 \cdot 11 = 33 \quad \checkmark
   $$

2. **Invertibility Conclusion:**
   Since $\det A = 33 \ne 0$, matrix $A$ is non-singular and invertible.

