# Solution to Exercise 3: When Does the Inverse Not Exist?

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 2 & 4 \\ 1 & 2 \end{pmatrix}
$$

Explain in two distinct ways why the inverse matrix $A^{-1}$ does not exist:
1. Using the determinant of the matrix.
2. Using the linear dependence between the rows of the matrix.

---

## 2. Theoretical Background and Concepts

1. **Determinant Criterion for Invertibility:**
   For any square matrix $M$, $M$ is invertible if and only if $\det M \ne 0$. If an inverse matrix $M^{-1}$ were to exist, applying the multiplicative property of determinants would yield:
   $$
   M M^{-1} = I \implies \det(M) \det(M^{-1}) = \det(I) = 1
   $$
   If $\det M = 0$, this would force $0 \cdot \det(M^{-1}) = 1$, which is impossible in any field.

2. **Row Rank and Linear Independence:**
   An $n \times n$ matrix is invertible if and only if its rows form a linearly independent set spanning $\mathbb{R}^n$ (full row rank $\operatorname{rank}(A) = n$).
   If the rows are linearly dependent, the transformation collapses dimensions: by the Rank-Nullity Theorem, $\dim(\ker A) = n - \operatorname{rank}(A) > 0$. The mapping is therefore not one-to-one (not injective), preventing the existence of any two-sided inverse.

---

## 3. Detailed Step-by-Step Solution

### Method 1: Using the Determinant

Compute the determinant of matrix $A$:
$$
\det A = \det\begin{pmatrix} 2 & 4 \\ 1 & 2 \end{pmatrix} = (2)(2) - (4)(1) = 4 - 4 = 0
$$

- **Why $A^{-1}$ does not exist:**
  1. The explicit formula for the inverse of a $2 \times 2$ matrix requires division by the determinant:
     $$
     A^{-1} = \frac{1}{\det A} \begin{pmatrix} 2 & -4 \\ -1 & 2 \end{pmatrix}
     $$
     Because $\det A = 0$, evaluating this expression would require division by zero, which is mathematically undefined.
  2. Moreover, if an inverse matrix $B$ existed such that $AB = I$, taking the determinant on both sides would give:
     $$
     \det(AB) = \det(A) \cdot \det(B) = 0 \cdot \det(B) = 0
     $$
     However, $\det(I) = 1$, leading to the contradiction $0 = 1$.
  3. Therefore, no matrix $A^{-1}$ can exist.

---

### Method 2: Using Linear Dependence Between the Rows

Let the row vectors of matrix $A$ be:
$$
\mathbf{r}_1 = \begin{pmatrix} 2 & 4 \end{pmatrix}, \qquad \mathbf{r}_2 = \begin{pmatrix} 1 & 2 \end{pmatrix}
$$

1. **Identify the Linear Dependence:**
   Notice that Row 1 is exactly twice Row 2:
   $$
   \mathbf{r}_1 = 2 \mathbf{r}_2 \iff \mathbf{r}_1 - 2 \mathbf{r}_2 = \mathbf{0}
   $$
   Because a non-trivial linear combination of the rows equals the zero vector (with coefficients $1$ and $-2$), the rows are **linearly dependent**.

2. **Why Row Dependence Precludes an Inverse:**
   - Because the two rows lie on the same 1-dimensional subspace in $\mathbb{R}^2$, the row space has dimension $\operatorname{rank}(A) = 1 < 2$.
   - By the Rank-Nullity Theorem, the dimension of the nullspace (kernel) is:
     $$
     \dim(\ker A) = 2 - \operatorname{rank}(A) = 2 - 1 = 1
     $$
   - Since the nullspace is non-trivial, there exist non-zero vectors that $A$ maps directly to the zero vector. For example:
     $$
     A \begin{pmatrix} -2 \\ 1 \end{pmatrix} = \begin{pmatrix} 2 & 4 \\ 1 & 2 \end{pmatrix} \begin{pmatrix} -2 \\ 1 \end{pmatrix} = \begin{pmatrix} 2(-2) + 4(1) \\ 1(-2) + 2(1) \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix}
     $$
   - Since both $\begin{pmatrix} 0 \\ 0 \end{pmatrix}$ and $\begin{pmatrix} -2 \\ 1 \end{pmatrix}$ map to $\begin{pmatrix} 0 \\ 0 \end{pmatrix}$, the linear mapping is not injective (it collapses the entire 2D plane onto a 1D line).
   - A non-injective function cannot have an inverse, because the origin cannot be mapped back to a single unique pre-image.

---

## 4. Verification and Consistency Checks

1. **System Consistency Check:**
   Attempt to solve $Ax = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$:
   $$
   \begin{cases}
   2x_1 + 4x_2 = 1 \\
   1x_1 + 2x_2 = 0
   \end{cases}
   $$
   Multiplying the second equation by $2$ gives $2x_1 + 4x_2 = 0$, contradicting the first equation ($1 = 0$).
   Since the vector $\begin{pmatrix} 1 \\ 0 \end{pmatrix}$ has no solution, $A$ is not surjective (onto), confirming non-invertibility.

2. **Column Dependence Check:**
   The column vectors are $\mathbf{c}_1 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}$ and $\mathbf{c}_2 = \begin{pmatrix} 4 \\ 2 \end{pmatrix}$.
   Notice $\mathbf{c}_2 = 2 \mathbf{c}_1$, confirming that column dependence and row dependence occur simultaneously, as guaranteed for all square matrices.
