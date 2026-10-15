# Solution to Exercise 14: A Matrix That Is Its Own Inverse

## 1. Problem Statement

Assume that a square matrix $A$ satisfies the condition:
$$
A^2 = I
$$

1. Show from the definition of the matrix inverse that:
   $$
   A^{-1} = A
   $$
2. Construct a concrete example of a $2 \times 2$ matrix $A$ that is different from both $I$ and $-I$ ($A \ne I$ and $A \ne -I$) satisfying $A^2 = I$.
3. Verify your constructed example by direct matrix multiplication.

---

## 2. Theoretical Background and Concepts

1. **Definition of the Inverse Matrix:**
   Let $A$ be an $n \times n$ matrix. If there exists a matrix $B$ such that:
   $$
   AB = BA = I_n
   $$
   then $A$ is invertible, and $B$ is called the inverse of $A$, denoted $A^{-1} = B$.
   Furthermore, whenever an inverse exists, it is strictly **unique**.

2. **Involutory Matrices (Involutions):**
   A matrix satisfying $A^2 = I$ is called an **involutory matrix** (or an **involution**). Involutions represent geometric operations that are self-reversing, meaning applying the operation twice restores every point to its starting position.

3. **Geometric Examples in $\mathbb{R}^2$:**
   In two-dimensional Euclidean geometry, any reflection across a line passing through the origin is an involution:
   - Reflecting a point across a mirror line and then reflecting it across the same line again returns it to its original position.
   - Standard examples include reflection across the $x$-axis ($\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$) and reflection across the line $y = x$ ($\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Prove That $A^{-1} = A$

1. We are given the premise:
   $$
   A^2 = I
   $$
2. By the definition of matrix exponentiation:
   $$
   A^2 = A \cdot A
   $$
   Therefore:
   $$
   A \cdot A = I
   $$
3. By the definition of the inverse matrix, a matrix $B$ is the inverse of $A$ if $AB = I$ and $BA = I$.
4. Setting $B = A$, we have:
   $$
   A \cdot A = I \quad \text{and} \quad A \cdot A = I
   $$
5. Because the inverse of a matrix is unique, the matrix that inverts $A$ must be $A$ itself:
   $$
   A^{-1} = A
   $$
This completes the mathematical proof.

---

### Step 2: Construct an Example of a $2 \times 2$ Involution

We seek a matrix $A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$ such that $A^2 = I$, with $A \ne \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$ and $A \ne \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$.

Consider the reflection matrix across the line $y = x$:
$$
A = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}
$$

- Clearly, $A \ne I$ (since $a_{11} = 0 \ne 1$).
- Clearly, $A \ne -I$ (since $a_{11} = 0 \ne -1$).

*(Another standard valid choice is the reflection across the $x$-axis: $A = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$)*.

---

### Step 3: Verify the Example by Direct Matrix Multiplication

Compute $A^2 = A \cdot A$:
$$
A^2 = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}
$$

Compute each entry:
- **Entry $(1, 1)$:** $(0)(0) + (1)(1) = 0 + 1 = 1$
- **Entry $(1, 2)$:** $(0)(1) + (1)(0) = 0 + 0 = 0$
- **Entry $(2, 1)$:** $(1)(0) + (0)(1) = 0 + 0 = 0$
- **Entry $(2, 2)$:** $(1)(1) + (0)(0) = 1 + 0 = 1$

Thus:
$$
A^2 = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I
$$
This verifies that $A = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$ satisfies $A^2 = I$, and therefore $A^{-1} = A$.

---

## 4. Verification and Consistency Checks

1. **Check Inverse Formula on the Example:**
   For $A = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$:
   - Determinant: $\det A = (0)(0) - (1)(1) = -1$.
   - Using the $2 \times 2$ formula:
     $$
     A^{-1} = \frac{1}{-1} \begin{pmatrix} 0 & -1 \\ -1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} = A \quad \checkmark
     $$

2. **Geometric Action Check:**
   Let $v = \begin{pmatrix} x \\ y \end{pmatrix}$:
   $$
   Av = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} y \\ x \end{pmatrix}
   $$
   Applying $A$ a second time:
   $$
   A(Av) = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} y \\ x \end{pmatrix} = \begin{pmatrix} x \\ y \end{pmatrix} = v \quad \checkmark
   $$
   Swapping coordinates twice restores the original coordinate order.

3. **Determinant and Eigenvalues of Involutions:**
   Since $A^2 = I$, $\det(A^2) = (\det A)^2 = \det(I) = 1 \implies \det A = \pm 1$.
   For our example, $\det A = -1$.
   Its eigenvalues satisfy $\lambda^2 = 1 \implies \lambda \in \{1, -1\}$.
   Here the eigenvalues are $+1$ (along the reflection line $y = x$) and $-1$ (perpendicular to the reflection line $y = -x$).
