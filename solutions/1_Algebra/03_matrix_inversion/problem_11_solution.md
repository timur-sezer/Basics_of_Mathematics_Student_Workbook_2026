# Solution to Exercise 11: Parameter and Invertibility

## 1. Problem Statement

Given the symmetric family of matrices depending on a parameter $t \in \mathbb{R}$:
$$
A(t) = \begin{pmatrix} 1 & t \\ t & 1 \end{pmatrix}
$$

1. Find all values of $t$ for which $A(t)$ is invertible.
2. For these values, give an explicit formula for the inverse matrix $A(t)^{-1}$.
3. Explain what happens to this formula and to the matrix structure at the excluded values.

---

## 2. Theoretical Background and Concepts

1. **Determinant and Invertibility Condition:**
   A square matrix is invertible if and only if its determinant is non-zero:
   $$
   A(t) \text{ is invertible} \iff \det A(t) \ne 0
   $$

2. **Inverse of a $2 \times 2$ Matrix:**
   For $M = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$ with $\det M \ne 0$:
   $$
   M^{-1} = \frac{1}{\det M} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}
   $$

3. **Singular Limits and Linear Dependence:**
   When the parameter $t$ approaches a value where $\det A(t) = 0$, the rows of $A(t)$ become linearly dependent, and the magnitude of the entries in $A(t)^{-1}$ diverges to infinity ($\pm \infty$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $\det A(t)$

Calculate the determinant:
$$
\det A(t) = \det\begin{pmatrix} 1 & t \\ t & 1 \end{pmatrix} = (1)(1) - (t)(t) = 1 - t^2
$$

---

### Step 2: Determine Values of $t$ for Invertibility

The matrix $A(t)$ is invertible if and only if $\det A(t) \ne 0$:
$$
1 - t^2 \ne 0 \iff t^2 \ne 1 \iff t \ne 1 \quad \text{and} \quad t \ne -1
$$

**Conclusion:**
Matrix $A(t)$ is invertible for all real numbers except $t = 1$ and $t = -1$:
$$
t \in \mathbb{R} \setminus \{-1, 1\}
$$

---

### Step 3: Find the Formula for $A(t)^{-1}$

For $t \ne \pm 1$, apply the $2 \times 2$ inversion formula:
$$
A(t)^{-1} = \frac{1}{\det A(t)} \begin{pmatrix} 1 & -t \\ -t & 1 \end{pmatrix} = \frac{1}{1 - t^2} \begin{pmatrix} 1 & -t \\ -t & 1 \end{pmatrix}
$$

Writing the entries explicitly:
$$
A(t)^{-1} = \begin{pmatrix} \frac{1}{1 - t^2} & -\frac{t}{1 - t^2} \\ -\frac{t}{1 - t^2} & \frac{1}{1 - t^2} \end{pmatrix}
$$

---

### Step 4: Explanation of the Excluded Values

1. **At $t = 1$:**
   - The matrix becomes:
     $$
     A(1) = \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}
     $$
   - The rows are identical: $R_1 = R_2$. The columns are also identical.
   - The linear mapping maps (collapses) the entire 2D plane onto the line $y = x$. Note that $A(1)$ satisfies $A(1)^2 = 2A(1)$, meaning it is twice the standard orthogonal projection matrix $P_{y=x} = \frac{1}{2}\begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}$.
   - In the inverse formula, the denominator $1 - t^2 = 1 - 1 = 0$, leading to division by zero: $\frac{1}{0}$. No inverse can exist because dimension is lost (the kernel is nontrivial: $\ker(A(1)) = \operatorname{span}\{(1, -1)^T\}$).

2. **At $t = -1$:**
   - The matrix becomes:
     $$
     A(-1) = \begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}
     $$
   - The rows are linearly dependent: $R_2 = -R_1$.
   - The linear mapping maps (collapses) the entire 2D plane onto the line $y = -x$. Similarly, $A(-1)^2 = 2A(-1)$, so it equals twice the orthogonal projection matrix $P_{y=-x} = \frac{1}{2}\begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}$.
   - In the inverse formula, the denominator $1 - (-1)^2 = 1 - 1 = 0$, again causing division by zero, and $\ker(A(-1)) = \operatorname{span}\{(1, 1)^T\}$.

3. **Behavior Near the Excluded Values:**
   As $t \to 1$ or $t \to -1$, the determinant approaches zero, meaning the inverse matrix entries diverge:
   $$
   \lim_{t \to 1} \|A(t)^{-1}\| = \infty
   $$
   This indicates that near singular configurations, an infinitesimal perturbation in the output requires an arbitrarily large input to invert (high condition number / ill-conditioning).

---

## 4. Verification and Consistency Checks

1. **Matrix Multiplication Check ($A(t) A(t)^{-1} = I$):**
   $$
   A(t) A(t)^{-1} = \begin{pmatrix} 1 & t \\ t & 1 \end{pmatrix} \cdot \frac{1}{1 - t^2} \begin{pmatrix} 1 & -t \\ -t & 1 \end{pmatrix}
   $$
   Multiply the matrices:
   - $(1, 1)$: $1(1) + t(-t) = 1 - t^2$
   - $(1, 2)$: $1(-t) + t(1) = -t + t = 0$
   - $(2, 1)$: $t(1) + 1(-t) = t - t = 0$
   - $(2, 2)$: $t(-t) + 1(1) = -t^2 + 1 = 1 - t^2$

   Dividing by the scalar $1 - t^2$:
   $$
   A(t) A(t)^{-1} = \frac{1}{1 - t^2} \begin{pmatrix} 1 - t^2 & 0 \\ 0 & 1 - t^2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I \quad \checkmark
   $$

2. **Special Value ($t = 0$):**
   - At $t = 0$, $A(0) = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I$.
   - From formula: $A(0)^{-1} = \frac{1}{1 - 0} \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I \quad \checkmark$.
