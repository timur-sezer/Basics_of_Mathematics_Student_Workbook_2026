# Solution to Exercise 2: Formula for a 2×2 Matrix

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 3 & 2 \\ 5 & 4 \end{pmatrix}
$$

1. Find the inverse matrix $A^{-1}$ using the explicit formula for a $2 \times 2$ matrix.
2. Check the result by computing the product $A A^{-1}$ (or $A^{-1} A$) and showing that it equals the identity matrix $I$.

---

## 2. Theoretical Background and Concepts

1. **Explicit Inversion Formula for a $2 \times 2$ Matrix:**
   Let $M = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$ be a $2 \times 2$ matrix.
   - The determinant of $M$ is $\det M = ad - bc$.
   - If $\det M \ne 0$, the inverse exists and is given by:
     $$
     M^{-1} = \frac{1}{\det M} \operatorname{adj}(M) = \frac{1}{ad - bc} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}
     $$
   - The classical recipe: swap the diagonal entries ($a \leftrightarrow d$) and negate the off-diagonal entries ($b \to -b, c \to -c$), then divide each entry by the determinant.

2. **Verification Condition:**
   By definition of the inverse:
   $$
   A A^{-1} = I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Determinant of $A$

For $A = \begin{pmatrix} 3 & 2 \\ 5 & 4 \end{pmatrix}$:
- $a = 3, \quad b = 2, \quad c = 5, \quad d = 4$

Calculate the determinant:
$$
\det A = ad - bc = (3)(4) - (2)(5) = 12 - 10 = 2
$$

Since $\det A = 2 \ne 0$, the matrix $A$ is invertible.

---

### Step 2: Apply the Inversion Formula

Using the formula:
$$
A^{-1} = \frac{1}{\det A} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix} = \frac{1}{2} \begin{pmatrix} 4 & -2 \\ -5 & 3 \end{pmatrix}
$$

Distributing the scalar factor $\frac{1}{2}$ to each entry:
$$
A^{-1} = \begin{pmatrix} \frac{4}{2} & \frac{-2}{2} \\ \frac{-5}{2} & \frac{3}{2} \end{pmatrix} = \begin{pmatrix} 2 & -1 \\ -\frac{5}{2} & \frac{3}{2} \end{pmatrix}
$$

---

### Step 3: Check by Computing the Product $A A^{-1}$

Multiply the original matrix $A$ by the candidate inverse $A^{-1}$:
$$
A A^{-1} = \begin{pmatrix} 3 & 2 \\ 5 & 4 \end{pmatrix} \begin{pmatrix} 2 & -1 \\ -\frac{5}{2} & \frac{3}{2} \end{pmatrix}
$$

Compute each entry:
- **Entry $(1, 1)$:**
  $$
  (3)(2) + (2)\left(-\frac{5}{2}\right) = 6 - 5 = 1
  $$
- **Entry $(1, 2)$:**
  $$
  (3)(-1) + (2)\left(\frac{3}{2}\right) = -3 + 3 = 0
  $$
- **Entry $(2, 1)$:**
  $$
  (5)(2) + (4)\left(-\frac{5}{2}\right) = 10 - 10 = 0
  $$
- **Entry $(2, 2)$:**
  $$
  (5)(-1) + (4)\left(\frac{3}{2}\right) = -5 + 6 = 1
  $$

Thus:
$$
A A^{-1} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I
$$
The product equals the identity matrix, confirming that our calculated inverse is correct.

---

## 4. Verification and Consistency Checks

1. **Reverse Order Product Check ($A^{-1} A$):**
   $$
   A^{-1} A = \begin{pmatrix} 2 & -1 \\ -\frac{5}{2} & \frac{3}{2} \end{pmatrix} \begin{pmatrix} 3 & 2 \\ 5 & 4 \end{pmatrix} = \begin{pmatrix} 2(3) + (-1)(5) & 2(2) + (-1)(4) \\ -\frac{5}{2}(3) + \frac{3}{2}(5) & -\frac{5}{2}(2) + \frac{3}{2}(4) \end{pmatrix}
   $$
   - Row 1: $(6 - 5, 4 - 4) = (1, 0)$
   - Row 2: $\left(-\frac{15}{2} + \frac{15}{2}, -5 + 6\right) = (0, 1)$
   $$
   A^{-1} A = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I \quad \checkmark
   $$

2. **Determinant of the Inverse Check:**
   $$
   \det(A^{-1}) = (2)\left(\frac{3}{2}\right) - (-1)\left(-\frac{5}{2}\right) = 3 - \frac{5}{2} = \frac{1}{2}
   $$
   Since $\det A = 2$, this perfectly matches the theoretical property $\det(A^{-1}) = \frac{1}{\det A} = \frac{1}{2}$.
