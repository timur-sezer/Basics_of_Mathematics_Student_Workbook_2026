# Solution to Exercise 6: Parameter and Invertibility

## 1. Problem Statement

Given the parameter-dependent family of matrices:
$$
A(t) = \begin{pmatrix} t & 1 \\ 2 & t \end{pmatrix}
$$

1. Find all real values of $t$ for which the matrix $A(t)$ is not invertible.
2. Explain how this condition is directly related to the determinant being zero.

---

## 2. Theoretical Background and Concepts

1. **The Invertible Matrix Theorem:**
   For any square matrix $M \in M_n(\mathbb{R})$, the following statements are mathematically equivalent:
   - $M$ is invertible (there exists $M^{-1}$ such that $M M^{-1} = I$).
   - $\det(M) \ne 0$.
   - The columns (and rows) of $M$ are linearly independent.
   - The linear mapping $x \mapsto Mx$ is bijective (one-to-one and onto).

2. **Singular Matrices:**
   A matrix that is not invertible is termed **singular**. By the equivalence above, a matrix is singular if and only if its determinant is zero:
   $$
   M \text{ is not invertible} \iff \det(M) = 0
   $$

3. **Determinant of a $2 \times 2$ Matrix:**
   For $M = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$, $\det(M) = ad - bc$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $\det A(t)$

Calculate the determinant of $A(t)$ as a function of the parameter $t$:
$$
\det A(t) = \det\begin{pmatrix} t & 1 \\ 2 & t \end{pmatrix} = (t)(t) - (1)(2) = t^2 - 2
$$

---

### Step 2: Set the Determinant to Zero

A square matrix is not invertible if and only if its determinant vanishes:
$$
\det A(t) = 0 \iff t^2 - 2 = 0
$$

Solving for $t$:
$$
t^2 = 2 \implies t = \pm\sqrt{2}
$$

Therefore, the matrix $A(t)$ is not invertible for:
$$
t = \sqrt{2} \quad \text{and} \quad t = -\sqrt{2}
$$

---

### Step 3: Explanation of the Connection Between Zero Determinant and Invertibility

1. **Algebraic Perspective (Inverse Matrix Formula):**
   The explicit formula for the inverse of a $2 \times 2$ matrix is:
   $$
   A(t)^{-1} = \frac{1}{\det A(t)} \begin{pmatrix} t & -1 \\ -2 & t \end{pmatrix} = \frac{1}{t^2 - 2} \begin{pmatrix} t & -1 \\ -2 & t \end{pmatrix}
   $$
   When $t = \pm\sqrt{2}$, the denominator becomes $\det A(t) = 0$. Division by zero is undefined, which algebraically demonstrates that no inverse matrix can exist.

2. **Geometric Perspective (Dimensional Collapse):**
   The determinant represents the signed area scaling factor of the transformation.
   - When $\det A(t) = 0$, the $2$-dimensional plane is crushed into a $1$-dimensional line.
   - Because infinitely many different input vectors are squashed onto the exact same output point, the mapping is not injective (information is irreversibly lost), making it impossible to uniquely reverse the transformation.

3. **Linear Dependence of Columns:**
   - At $t = \sqrt{2}$:
     $$
     A(\sqrt{2}) = \begin{pmatrix} \sqrt{2} & 1 \\ 2 & \sqrt{2} \end{pmatrix}
     $$
     Notice that the first column $\begin{pmatrix} \sqrt{2} \\ 2 \end{pmatrix}$ is exactly $\sqrt{2}$ times the second column $\begin{pmatrix} 1 \\ \sqrt{2} \end{pmatrix}$.
   - At $t = -\sqrt{2}$:
     $$
     A(-\sqrt{2}) = \begin{pmatrix} -\sqrt{2} & 1 \\ 2 & -\sqrt{2} \end{pmatrix}
     $$
     Notice that the first column is $-\sqrt{2}$ times the second column.
   In both cases, the columns are collinear (linearly dependent), preventing the matrix from having full rank.

---

## 4. Verification and Consistency Checks

1. **Kernel / Nullspace Check:**
   If $A(\sqrt{2})$ is not invertible, there must exist a non-zero vector $v \ne 0$ such that $A(\sqrt{2}) v = 0$:
   $$
   \begin{pmatrix} \sqrt{2} & 1 \\ 2 & \sqrt{2} \end{pmatrix} \begin{pmatrix} 1 \\ -\sqrt{2} \end{pmatrix} = \begin{pmatrix} \sqrt{2}(1) + 1(-\sqrt{2}) \\ 2(1) + \sqrt{2}(-\sqrt{2}) \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix}
   $$
   Since a non-trivial null vector exists, $\ker(A(\sqrt{2})) \ne \{0\}$, confirming non-invertibility.

2. **Test of an Invertible Case:**
   For $t = 0$:
   $$
   \det A(0) = 0^2 - 2 = -2 \ne 0 \implies A(0) \text{ is invertible, with } A(0)^{-1} = -\frac{1}{2}\begin{pmatrix} 0 & -1 \\ -2 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 1/2 \\ 1 & 0 \end{pmatrix} \quad \checkmark
   $$

