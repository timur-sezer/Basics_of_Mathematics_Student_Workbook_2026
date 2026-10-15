# Solution to Exercise 1: Definition of the Inverse

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix}
$$

1. Without using any explicit inversion formula, determine whether $B = A^{-1}$.
2. Compute the matrix products $AB$ and $BA$.
3. Relate the results directly to the formal definition of the inverse matrix.

---

## 2. Theoretical Background and Concepts

1. **Definition of the Inverse Matrix:**
   Let $A$ be a square matrix of size $n \times n$. A matrix $B$ of size $n \times n$ is said to be the **inverse** of $A$ (denoted $B = A^{-1}$) if and only if:
   $$
   AB = I_n \quad \text{and} \quad BA = I_n
   $$
   where $I_n$ is the $n \times n$ identity matrix.

2. **Uniqueness of the Inverse:**
   If such a matrix $B$ exists, it is unique. For square matrices with entries in a field (such as $\mathbb{R}$), satisfying either one-sided condition ($AB = I$ or $BA = I$) is sufficient to imply the other, but verifying both confirms the two-sided definition directly from first principles.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Product $AB$

Multiply $A$ by $B$:
$$
AB = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix}
$$

Computing each entry:
- **Entry $(1, 1)$:** $(2)(1) + (1)(-1) = 2 - 1 = 1$
- **Entry $(1, 2)$:** $(2)(-1) + (1)(2) = -2 + 2 = 0$
- **Entry $(2, 1)$:** $(1)(1) + (1)(-1) = 1 - 1 = 0$
- **Entry $(2, 2)$:** $(1)(-1) + (1)(2) = -1 + 2 = 1$

Thus:
$$
AB = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I
$$

---

### Step 2: Compute the Product $BA$

Multiply $B$ by $A$:
$$
BA = \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}
$$

Computing each entry:
- **Entry $(1, 1)$:** $(1)(2) + (-1)(1) = 2 - 1 = 1$
- **Entry $(1, 2)$:** $(1)(1) + (-1)(1) = 1 - 1 = 0$
- **Entry $(2, 1)$:** $(-1)(2) + (2)(1) = -2 + 2 = 0$
- **Entry $(2, 2)$:** $(-1)(1) + (2)(1) = -1 + 2 = 1$

Thus:
$$
BA = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I
$$

---

### Step 3: Relation to the Definition of the Inverse

1. The calculations show that:
   $$
   AB = BA = I
   $$
2. According to the definition of the inverse matrix, a matrix $B$ is the inverse of $A$ precisely when multiplying them in either order produces the identity matrix $I$.
3. Therefore, without relying on determinants or formulas, we conclude:
   $$
   B = A^{-1} \quad \text{and} \quad A = B^{-1}
   $$

---

## 4. Verification and Consistency Checks

1. **Independent Check via Determinant Formula:**
   For $A = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}$:
   $$
   \det A = (2)(1) - (1)(1) = 2 - 1 = 1
   $$
   Using the standard $2 \times 2$ formula:
   $$
   A^{-1} = \frac{1}{\det A} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix} = \frac{1}{1} \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix} = \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix} = B \quad \checkmark
   $$

2. **Vector Action Invariance:**
   For an arbitrary vector $v = \begin{pmatrix} x \\ y \end{pmatrix}$:
   $$
   Av = \begin{pmatrix} 2x + y \\ x + y \end{pmatrix}
   $$
   Applying $B$:
   $$
   B(Av) = \begin{pmatrix} 1(2x + y) - 1(x + y) \\ -1(2x + y) + 2(x + y) \end{pmatrix} = \begin{pmatrix} 2x - x + y - y \\ -2x + 2x - y + 2y \end{pmatrix} = \begin{pmatrix} x \\ y \end{pmatrix} = v \quad \checkmark
   $$
   Matrix $B$ perfectly undoes the transformation applied by $A$.
