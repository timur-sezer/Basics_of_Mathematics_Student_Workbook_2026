# Solution to Exercise 10: Inverse of a Diagonal Matrix

## 1. Problem Statement

Given the diagonal matrices:
$$
D = \begin{pmatrix} 2 & 0 & 0 \\ 0 & -3 & 0 \\ 0 & 0 & 5 \end{pmatrix}, \qquad E = \begin{pmatrix} 2 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 5 \end{pmatrix}
$$

1. Without using Gauss–Jordan elimination, determine which matrix is invertible.
2. For the invertible matrix, write its inverse directly from its diagonal structure.
3. Check the calculated inverse by matrix multiplication.

---

## 2. Theoretical Background and Concepts

1. **Determinant and Invertibility of Diagonal Matrices:**
   A diagonal matrix $M = \operatorname{diag}(d_1, d_2, \dots, d_n)$ has non-zero entries only on its main diagonal. Its determinant is simply the product of all diagonal entries:
   $$
   \det(M) = d_1 \cdot d_2 \cdots d_n
   $$
   Consequently, a diagonal matrix is invertible if and only if **all its diagonal entries are non-zero**:
   $$
   M \text{ is invertible} \iff \det(M) \ne 0 \iff d_i \ne 0 \quad \text{for all } i = 1, 2, \dots, n
   $$

2. **Inverse of a Diagonal Matrix:**
   Because diagonal matrices multiply entry-by-entry along the diagonal:
   $$
   \operatorname{diag}(d_1, \dots, d_n) \cdot \operatorname{diag}(c_1, \dots, c_n) = \operatorname{diag}(d_1 c_1, \dots, d_n c_n)
   $$
   Setting the product equal to $I = \operatorname{diag}(1, \dots, 1)$ requires $d_i c_i = 1 \implies c_i = \frac{1}{d_i}$.
   Hence, the inverse is formed simply by replacing each diagonal entry with its reciprocal:
   $$
   M^{-1} = \operatorname{diag}\left(\frac{1}{d_1}, \frac{1}{d_2}, \dots, \frac{1}{d_n}\right)
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Decide Invertibility of $D$ and $E$

1. **Matrix $D$:**
   $$
   D = \operatorname{diag}(2, -3, 5)
   $$
   - The diagonal entries are $d_1 = 2$, $d_2 = -3$, and $d_3 = 5$.
   - None of the diagonal entries is zero ($2 \ne 0$, $-3 \ne 0$, $5 \ne 0$).
   - Determinant: $\det D = (2)(-3)(5) = -30 \ne 0$.
   - **Conclusion:** **Matrix $D$ is invertible.**

2. **Matrix $E$:**
   $$
   E = \operatorname{diag}(2, 0, 5)
   $$
   - The diagonal entry $e_{22} = 0$.
   - Row 2 (and Column 2) consists entirely of zeros: $\begin{pmatrix} 0 & 0 & 0 \end{pmatrix}$.
   - Determinant: $\det E = (2)(0)(5) = 0$.
   - **Conclusion:** **Matrix $E$ is not invertible (singular).**

---

### Step 2: Write Down the Inverse $D^{-1}$

Inverting each non-zero diagonal entry of $D$:
- $(D^{-1})_{11} = \frac{1}{2}$
- $(D^{-1})_{22} = \frac{1}{-3} = -\frac{1}{3}$
- $(D^{-1})_{33} = \frac{1}{5}$

All off-diagonal entries remain zero:
$$
D^{-1} = \begin{pmatrix}
\frac{1}{2} & 0 & 0 \\
0 & -\frac{1}{3} & 0 \\
0 & 0 & \frac{1}{5}
\end{pmatrix}
$$

---

### Step 3: Check by Matrix Multiplication

Multiply $D$ by $D^{-1}$:
$$
D D^{-1} = \begin{pmatrix} 2 & 0 & 0 \\ 0 & -3 & 0 \\ 0 & 0 & 5 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 & 0 \\ 0 & -\frac{1}{3} & 0 \\ 0 & 0 & \frac{1}{5} \end{pmatrix}
$$

Computing the product:
- Row 1: $\begin{pmatrix} 2\left(\frac{1}{2}\right) & 0 & 0 \end{pmatrix} = \begin{pmatrix} 1 & 0 & 0 \end{pmatrix}$
- Row 2: $\begin{pmatrix} 0 & (-3)\left(-\frac{1}{3}\right) & 0 \end{pmatrix} = \begin{pmatrix} 0 & 1 & 0 \end{pmatrix}$
- Row 3: $\begin{pmatrix} 0 & 0 & 5\left(\frac{1}{5}\right) \end{pmatrix} = \begin{pmatrix} 0 & 0 & 1 \end{pmatrix}$

Thus:
$$
D D^{-1} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} = I_3
$$

Similarly:
$$
D^{-1} D = \begin{pmatrix} \frac{1}{2} \cdot 2 & 0 & 0 \\ 0 & \left(-\frac{1}{3}\right) \cdot (-3) & 0 \\ 0 & 0 & \frac{1}{5} \cdot 5 \end{pmatrix} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} = I_3
$$
This verifies that $D^{-1}$ is the exact inverse.

---

## 4. Verification and Consistency Checks

1. **Non-Invertibility of $E$ via Kernel:**
   Consider the standard basis vector $\mathbf{e}_2 = \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}$:
   $$
   E \mathbf{e}_2 = \begin{pmatrix} 2 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 5 \end{pmatrix} \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}
   $$
   Because a non-zero vector is mapped to the zero vector, $\ker E \ne \{\mathbf{0}\}$, proving that $E$ is non-injective and therefore cannot have an inverse.

2. **Determinant of $D^{-1}$:**
   $$
   \det(D^{-1}) = \left(\frac{1}{2}\right)\left(-\frac{1}{3}\right)\left(\frac{1}{5}\right) = -\frac{1}{30} = \frac{1}{\det D} \quad \checkmark
   $$
