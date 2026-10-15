# Solution to Exercise 14: A System of Equations and the Determinant

## 1. Problem Statement

Consider the linear system $Ax = b$, where the coefficient matrix is:
$$
A = \begin{pmatrix} 1 & 2 \\ k & 4 \end{pmatrix}
$$

1. Determine all values of the parameter $k$ for which the system has exactly one (unique) solution for every right-hand side vector $b$.
2. For the remaining critical value of $k$:
   - Provide an example of a right-hand side vector $b$ for which the system has **infinitely many solutions**.
   - Provide an example of a right-hand side vector $b$ for which the system has **no solution** (is inconsistent).

---

## 2. Theoretical Background and Concepts

1. **Cramer's Rule and Uniqueness of Solutions:**
   For a square linear system $Ax = b$, the system has a unique solution for every vector $b$ if and only if the coefficient matrix $A$ is invertible, which holds if and only if its determinant is non-zero:
   $$
   \det(A) \ne 0 \iff \text{unique solution for every } b \in \mathbb{R}^n
   $$

2. **Rouché–Capelli (Kronecker–Capelli) Theorem:**
   When $\det(A) = 0$, the matrix is singular, and the behavior depends on the augmented matrix $[A \mid b]$:
   - **Infinitely many solutions (Consistent and Dependent):** Occurs when the right-hand side $b$ lies in the column space of $A$ ($\operatorname{rank}[A] = \operatorname{rank}[A \mid b] < n$).
   - **No solution (Inconsistent):** Occurs when the right-hand side $b$ does not lie in the column space of $A$ ($\operatorname{rank}[A \mid b] > \operatorname{rank}[A]$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $\det A$ and Find the Condition for a Unique Solution

Compute the determinant of the $2 \times 2$ coefficient matrix:
$$
\det A = \det\begin{pmatrix} 1 & 2 \\ k & 4 \end{pmatrix} = (1)(4) - (2)(k) = 4 - 2k
$$

The system has a unique solution for every vector $b$ if and only if $\det A \ne 0$:
$$
4 - 2k \ne 0 \implies 2k \ne 4 \implies k \ne 2
$$

**Conclusion:** The system has exactly one solution for every $b$ for all **$k \in \mathbb{R} \setminus \{2\}$**.

---

### Step 2: Analyze the Remaining Case $k = 2$

When $k = 2$, $\det A = 0$. The coefficient matrix becomes:
$$
A = \begin{pmatrix} 1 & 2 \\ 2 & 4 \end{pmatrix}
$$

Writing the system explicitly in terms of variables $x_1, x_2$:
$$
\begin{cases}
1 x_1 + 2 x_2 = b_1 \\
2 x_1 + 4 x_2 = b_2
\end{cases}
$$

Notice that the left-hand side of the second equation is exactly twice the left-hand side of the first equation:
$$
2(x_1 + 2x_2) = 2x_1 + 4x_2
$$
For the equations to be compatible, the right-hand sides must satisfy:
$$
b_2 = 2b_1
$$

---

### Step 3: Example with Infinitely Many Solutions ($k = 2$)

Choose a right-hand side vector satisfying $b_2 = 2b_1$, for example:
$$
b = \begin{pmatrix} 1 \\ 2 \end{pmatrix}
$$

The system becomes:
$$
\begin{cases}
x_1 + 2x_2 = 1 \\
2x_1 + 4x_2 = 2
\end{cases}
$$

Dividing the second equation by $2$ yields $x_1 + 2x_2 = 1$, which is identical to the first equation. The system reduces to a single linear equation in two unknowns:
$$
x_1 = 1 - 2x_2, \qquad x_2 \in \mathbb{R} \text{ (free parameter)}
$$
Expressed in parametric vector form:
$$
x = \begin{pmatrix} 1 - 2t \\ t \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \end{pmatrix} + t \begin{pmatrix} -2 \\ 1 \end{pmatrix}, \qquad t \in \mathbb{R}
$$
This demonstrates that there are **infinitely many solutions**.

---

### Step 4: Example with No Solution ($k = 2$)

Choose a right-hand side vector violating $b_2 = 2b_1$, for example:
$$
b = \begin{pmatrix} 1 \\ 0 \end{pmatrix}
$$

The system becomes:
$$
\begin{cases}
x_1 + 2x_2 = 1 \\
2x_1 + 4x_2 = 0
\end{cases}
$$

Multiply the first equation by $2$:
$$
2x_1 + 4x_2 = 2
$$
Subtracting the second equation from this gives:
$$
(2x_1 + 4x_2) - (2x_1 + 4x_2) = 2 - 0 \implies 0 = 2
$$
This is an impossible contradiction. Geometrically, the two equations describe distinct parallel lines that never intersect. Therefore, there is **no solution**.

---

## 4. Verification and Consistency Checks

1. **Cramer's Rule Verification (when $k \ne 2$):**
   Using determinants for $k \ne 2$:
   $$
   x_1 = \frac{\det\begin{pmatrix} b_1 & 2 \\ b_2 & 4 \end{pmatrix}}{\det A} = \frac{4b_1 - 2b_2}{4 - 2k} = \frac{2b_1 - b_2}{2 - k}
   $$
   $$
   x_2 = \frac{\det\begin{pmatrix} 1 & b_1 \\ k & b_2 \end{pmatrix}}{\det A} = \frac{b_2 - k b_1}{4 - 2k}
   $$
   Both expressions are well-defined for any $b = \begin{pmatrix} b_1 \\ b_2 \end{pmatrix}$ as long as $k \ne 2$.

2. **Column Space / Span Verification ($k = 2$):**
   The column space is:
   $$
   \operatorname{Col}(A) = \operatorname{span}\left\{ \begin{pmatrix} 1 \\ 2 \end{pmatrix}, \begin{pmatrix} 2 \\ 4 \end{pmatrix} \right\} = \operatorname{span}\left\{ \begin{pmatrix} 1 \\ 2 \end{pmatrix} \right\}
   $$
   - Vector $\begin{pmatrix} 1 \\ 2 \end{pmatrix} \in \operatorname{Col}(A) \implies$ consistent (infinite solutions).
   - Vector $\begin{pmatrix} 1 \\ 0 \end{pmatrix} \notin \operatorname{Col}(A) \implies$ inconsistent (no solution).

