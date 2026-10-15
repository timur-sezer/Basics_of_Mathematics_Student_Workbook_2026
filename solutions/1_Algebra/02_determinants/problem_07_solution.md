# Solution to Exercise 7: Using Properties Instead of Recomputing

## 1. Problem Statement

Suppose $A$ is a $3 \times 3$ matrix with:
$$
\det A = -4
$$

Using the theoretical properties of determinants (without needing the individual matrix entries), compute:
1. $\det(2A)$
2. $\det(A^T)$
3. $\det(A^2)$
4. $\det(-A)$

Justify each computation using the appropriate determinant property.

---

## 2. Theoretical Background and Concepts

1. **Scalar Multiplication Property:**
   For an $n \times n$ matrix $M$ and any scalar $c \in \mathbb{R}$:
   $$
   \det(cM) = c^n \det(M)
   $$
   *Reason:* The determinant is multilinear in its rows. Multiplying the matrix by scalar $c$ scales each of its $n$ individual rows by factor $c$. Factoring out $c$ from each row yields a total factor of $c^n$.

2. **Transpose Property:**
   Transposing a matrix does not change its determinant:
   $$
   \det(M^T) = \det(M)
   $$
   *Reason:* Row operations on $M$ correspond to column operations on $M^T$, preserving the algebraic permutation expansion $\sum_{\sigma} \operatorname{sgn}(\sigma) \prod m_{i, \sigma(i)}$.

3. **Multiplicative Property:**
   For any square matrices $M$ and $N$ of identical dimensions:
   $$
   \det(MN) = \det(M)\det(N)
   $$
   In particular, for matrix powers:
   $$
   \det(M^k) = (\det M)^k
   $$

---

## 3. Detailed Step-by-Step Solution

Matrix $A$ has dimension $n = 3$, and its determinant is $\det A = -4$.

### 1. Compute $\det(2A)$
- **Applicable Property:** $\det(cA) = c^n \det A$.
- Here, scalar $c = 2$ and matrix dimension $n = 3$:
  $$
  \det(2A) = 2^3 \det A = 8 \det A
  $$
- Substituting $\det A = -4$:
  $$
  \det(2A) = 8 \cdot (-4) = -32
  $$

---

### 2. Compute $\det(A^T)$
- **Applicable Property:** $\det(A^T) = \det A$.
- Transposition preserves the determinant value:
  $$
  \det(A^T) = \det A = -4
  $$

---

### 3. Compute $\det(A^2)$
- **Applicable Property:** $\det(A^2) = \det(A \cdot A) = \det A \cdot \det A = (\det A)^2$.
- Substituting $\det A = -4$:
  $$
  \det(A^2) = (-4)^2 = 16
  $$

---

### 4. Compute $\det(-A)$
- **Applicable Property:** This is scalar multiplication with $c = -1$:
  $$
  \det(-A) = \det((-1)A) = (-1)^n \det A
  $$
- Since $n = 3$ is odd, $(-1)^3 = -1$:
  $$
  \det(-A) = (-1)^3 \det A = -1 \cdot \det A
  $$
- Substituting $\det A = -4$:
  $$
  \det(-A) = -1 \cdot (-4) = 4
  $$

---

## 4. Verification and Consistency Checks

1. **Concrete Numerical Test Case:**
   Construct a simple diagonal $3 \times 3$ matrix with $\det A = -4$:
   $$
   A = \begin{pmatrix} -4 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} \implies \det A = (-4)(1)(1) = -4
   $$
   - **Check $2A$:**
     $$
     2A = \begin{pmatrix} -8 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 2 \end{pmatrix} \implies \det(2A) = (-8)(2)(2) = -32 \quad \checkmark
     $$
   - **Check $A^T$:**
     $$
     A^T = A \implies \det(A^T) = -4 \quad \checkmark
     $$
   - **Check $A^2$:**
     $$
     A^2 = \begin{pmatrix} 16 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} \implies \det(A^2) = (16)(1)(1) = 16 \quad \checkmark
     $$
   - **Check $-A$:**
     $$
     -A = \begin{pmatrix} 4 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & -1 \end{pmatrix} \implies \det(-A) = (4)(-1)(-1) = 4 \quad \checkmark
     $$
   All properties are verified.

