# Solution to Exercise 3: Swapping Two Rows

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 3 & 1 \\ 2 & 1 & 1 \end{pmatrix}
$$

1. Compute $\det A$.
2. Form matrix $B$ by interchanging the first and second rows of $A$.
3. Predict $\det B$ using the theoretical properties of determinants.
4. Verify your prediction by direct calculation of $\det B$.

---

## 2. Theoretical Background and Concepts

1. **Antisymmetry Property of Determinants (Row Swap):**
   The determinant is an alternating multilinear form. If any two rows (or any two columns) of a square matrix are interchanged, the sign of the determinant is reversed while its absolute value is preserved:
   $$
   \det(B) = -\det(A)
   $$
   where $B$ is obtained from $A$ via a single transposition $R_i \leftrightarrow R_j$ ($i \ne j$).

2. **Permutation Matrices:**
   Interchanging row 1 and row 2 corresponds to pre-multiplying $A$ by the elementary permutation matrix:
   $$
   P = \begin{pmatrix} 0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 1 \end{pmatrix}
   $$
   Since $\det(P) = -1$, the multiplicative property of determinants implies:
   $$
   \det(B) = \det(PA) = \det(P)\det(A) = (-1)\det(A) = -\det(A)
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $\det A$

We compute $\det A$ using Laplace expansion along the **first column**:
$$
A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 3 & 1 \\ 2 & 1 & 1 \end{pmatrix}
$$

Expanding along Column 1:
$$
\det A = 1 \cdot (-1)^{1+1} \det\begin{pmatrix} 3 & 1 \\ 1 & 1 \end{pmatrix} - 0 + 2 \cdot (-1)^{3+1} \det\begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix}
$$

Compute the $2 \times 2$ minors:
- Minor for $a_{11}$:
  $$
  \det\begin{pmatrix} 3 & 1 \\ 1 & 1 \end{pmatrix} = (3)(1) - (1)(1) = 3 - 1 = 2
  $$
- Minor for $a_{31}$:
  $$
  \det\begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix} = (2)(1) - (0)(3) = 2 - 0 = 2
  $$

Substitute back:
$$
\det A = 1 \cdot (2) + 2 \cdot (2) = 2 + 4 = 6
$$

---

### Step 2: Form Matrix $B$ and Predict $\det B$

Interchange the first and second rows of $A$:
- Row 1 of $B$ is Row 2 of $A$: $\begin{pmatrix} 0 & 3 & 1 \end{pmatrix}$.
- Row 2 of $B$ is Row 1 of $A$: $\begin{pmatrix} 1 & 2 & 0 \end{pmatrix}$.
- Row 3 of $B$ is Row 3 of $A$: $\begin{pmatrix} 2 & 1 & 1 \end{pmatrix}$.

Thus:
$$
B = \begin{pmatrix} 0 & 3 & 1 \\ 1 & 2 & 0 \\ 2 & 1 & 1 \end{pmatrix}
$$

**Prediction:**
By the antisymmetry property of determinants, a single row swap multiplies the determinant by $-1$:
$$
\det B = -\det A = -6
$$

---

### Step 3: Verify Prediction by Computing $\det B$

Compute $\det B$ by expanding along its **first row**:
$$
B = \begin{pmatrix} 0 & 3 & 1 \\ 1 & 2 & 0 \\ 2 & 1 & 1 \end{pmatrix}
$$

Expanding along Row 1 using cofactor expansion:
$$
\det B = 0 \cdot C_{11} + 3 \cdot (-1)^{1+2} \det\begin{pmatrix} 1 & 0 \\ 2 & 1 \end{pmatrix} + 1 \cdot (-1)^{1+3} \det\begin{pmatrix} 1 & 2 \\ 2 & 1 \end{pmatrix} = -3(1) + 1(-3) = -6
$$

Detailed calculation of the $2 \times 2$ minors:
- Minor for $b_{12}$:
  $$
  \det\begin{pmatrix} 1 & 0 \\ 2 & 1 \end{pmatrix} = (1)(1) - (0)(2) = 1
  $$
- Minor for $b_{13}$:
  $$
  \det\begin{pmatrix} 1 & 2 \\ 2 & 1 \end{pmatrix} = (1)(1) - (2)(2) = 1 - 4 = -3
  $$

Substituting the minors into the cofactor expansion:
$$
\det B = 0 - 3(1) + 1(-3) = -3 - 3 = -6
$$

The direct calculation yields **$-6$**, confirming the prediction precisely.

---

## 4. Verification and Consistency Checks

1. **Sarrus' Rule Check on Matrix $B$:**
   $$
   \begin{array}{ccc|cc}
   0 & 3 & 1 & 0 & 3 \\
   1 & 2 & 0 & 1 & 2 \\
   2 & 1 & 1 & 2 & 1
   \end{array}
   $$
   - Downward diagonals:
     $(0 \cdot 2 \cdot 1) + (3 \cdot 0 \cdot 2) + (1 \cdot 1 \cdot 1) = 0 + 0 + 1 = 1$.
   - Upward diagonals:
     $(2 \cdot 2 \cdot 1) + (1 \cdot 0 \cdot 0) + (1 \cdot 1 \cdot 3) = 4 + 0 + 3 = 7$.
   - Difference:
     $$
     \det B = 1 - 7 = -6 \quad \checkmark
     $$

2. **Orientation Check:**
   In three-dimensional space, swapping two basis vectors transforms a right-handed coordinate system into a left-handed coordinate system, reversing the sign of the oriented volume from $+6$ to $-6$.

