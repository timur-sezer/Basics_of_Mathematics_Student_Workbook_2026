# Solution to Exercise 4: Triangular Matrix

## 1. Problem Statement

Given the matrix:
$$
T = \begin{pmatrix} 2 & 4 & 1 \\ 0 & -3 & 5 \\ 0 & 0 & 7 \end{pmatrix}
$$

1. Without expanding the determinant by general brute-force formulas, compute $\det T$.
2. State the general rule for the determinant of an arbitrary triangular matrix.
3. Explain why the rule holds using this specific example.

---

## 2. Theoretical Background and Concepts

1. **Triangular Matrices:**
   - An $n \times n$ matrix $U = (u_{ij})$ is **upper triangular** if all entries strictly below the main diagonal are zero ($u_{ij} = 0$ for all $i > j$).
   - An $n \times n$ matrix $L = (l_{ij})$ is **lower triangular** if all entries strictly above the main diagonal are zero ($l_{ij} = 0$ for all $i < j$).
   - A matrix that is both upper and lower triangular is **diagonal**.

2. **General Determinant Rule for Triangular Matrices:**
   For any triangular (or diagonal) matrix of size $n \times n$, its determinant equals the product of its diagonal entries:
   $$
   \det T = t_{11} \cdot t_{22} \cdots t_{nn} = \prod_{i=1}^n t_{ii}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $\det T$ Using the Triangular Matrix Rule

The matrix:
$$
T = \begin{pmatrix} 2 & 4 & 1 \\ 0 & -3 & 5 \\ 0 & 0 & 7 \end{pmatrix}
$$
has all zero entries below the main diagonal ($t_{21} = 0$, $t_{31} = 0$, $t_{32} = 0$). Hence, $T$ is an upper-triangular matrix.

Its diagonal entries are:
$$
t_{11} = 2, \qquad t_{22} = -3, \qquad t_{33} = 7
$$

Applying the rule directly:
$$
\det T = t_{11} \cdot t_{22} \cdot t_{33} = 2 \cdot (-3) \cdot 7 = -6 \cdot 7 = -42
$$

---

### Step 2: Explanation Using Successive Laplace Expansions

To understand *why* the rule works for this example:

1. **First expansion along Column 1:**
   Column 1 contains only one non-zero element, which is the first diagonal entry $t_{11} = 2$:
   $$
   \det T = 2 \cdot (-1)^{1+1} \det\begin{pmatrix} -3 & 5 \\ 0 & 7 \end{pmatrix} + 0 + 0 = 2 \det\begin{pmatrix} -3 & 5 \\ 0 & 7 \end{pmatrix}
   $$

2. **Second expansion along Column 1 of the $2 \times 2$ submatrix:**
   The remaining $2 \times 2$ submatrix $\begin{pmatrix} -3 & 5 \\ 0 & 7 \end{pmatrix}$ is itself upper triangular. Expanding along its first column:
   $$
   \det\begin{pmatrix} -3 & 5 \\ 0 & 7 \end{pmatrix} = -3 \cdot (-1)^{1+1} \det(7) + 0 = (-3) \cdot 7 = -21
   $$

3. **Combining the steps:**
   $$
   \det T = 2 \cdot [(-3) \cdot 7] = 2 \cdot (-3) \cdot 7 = -42
   $$

Because all sub-diagonal elements are zero, every expansion step along the first column isolates exactly one diagonal entry multiplied by the determinant of a smaller triangular matrix, culminating in the product of all diagonal entries.

---

## 4. Verification and Consistency Checks

1. **Direct Sarrus' Rule Verification:**
   $$
   \begin{array}{ccc|cc}
   2 & 4 & 1 & 2 & 4 \\
   0 & -3 & 5 & 0 & -3 \\
   0 & 0 & 7 & 0 & 0
   \end{array}
   $$
   - Downward terms:
     $$
     (2)(-3)(7) + (4)(5)(0) + (1)(0)(0) = -42 + 0 + 0 = -42
     $$
   - Upward terms:
     $$
     (0)(-3)(1) + (0)(5)(2) + (7)(0)(4) = 0 + 0 + 0 = 0
     $$
   - Difference:
     $$
     \det T = -42 - 0 = -42 \quad \checkmark
     $$
   Notice that all products other than the main diagonal contain at least one zero factor, confirming why only the main diagonal contributes.

2. **Eigenvalues Connection:**
   For any triangular matrix, its eigenvalues are precisely its diagonal entries: $\lambda_1 = 2$, $\lambda_2 = -3$, $\lambda_3 = 7$.
   Since the determinant is the product of all eigenvalues:
   $$
   \det T = \lambda_1 \lambda_2 \lambda_3 = 2 \cdot (-3) \cdot 7 = -42 \quad \checkmark
   $$
