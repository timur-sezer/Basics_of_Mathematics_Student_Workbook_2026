# Solution to Exercise 12: Finding Inverses Without Starting from Scratch

## 1. Problem Statement

It is known that the inverse of an invertible matrix $A$ is:
$$
A^{-1} = \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix}
$$

Without first finding the original matrix $A$, compute:
1. $(3A)^{-1}$
2. $(A^T)^{-1}$
3. $(A^2)^{-1}$

Justify each result using the appropriate theoretical property of matrix inverses.

---

## 2. Theoretical Background and Concepts

1. **Scalar Multiple Property:**
   For any non-zero scalar $c \ne 0$ and invertible matrix $M$:
   $$
   (cM)^{-1} = \frac{1}{c} M^{-1}
   $$
   *Proof:* $(cM) \left(\frac{1}{c} M^{-1}\right) = \left(c \cdot \frac{1}{c}\right) (M M^{-1}) = 1 \cdot I = I$.

2. **Transpose Property:**
   The inverse of the transpose is the transpose of the inverse:
   $$
   (M^T)^{-1} = (M^{-1})^T
   $$
   *Proof:* Taking the transpose of $M M^{-1} = I$ gives $(M M^{-1})^T = (M^{-1})^T M^T = I^T = I$.

3. **Power Property:**
   For any integer $k \ge 1$:
   $$
   (M^k)^{-1} = (M^{-1})^k
   $$
   *Proof:* Applying the reversal rule for products repeatedly:
   $$
   (M \cdot M \cdots M)^{-1} = M^{-1} \cdot M^{-1} \cdots M^{-1} = (M^{-1})^k
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $(3A)^{-1}$

- **Applicable Property:** $(cA)^{-1} = \frac{1}{c} A^{-1}$ with $c = 3$.
- Substitute $A^{-1}$:
  $$
  (3A)^{-1} = \frac{1}{3} A^{-1} = \frac{1}{3} \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix}
  $$
- Multiply each entry by the scalar $\frac{1}{3}$:
  $$
  (3A)^{-1} = \begin{pmatrix} \frac{2}{3} & -\frac{1}{3} \\ -1 & \frac{2}{3} \end{pmatrix}
  $$

---

### Step 2: Compute $(A^T)^{-1}$

- **Applicable Property:** $(A^T)^{-1} = (A^{-1})^T$.
- Transpose matrix $A^{-1}$ (swap rows and columns):
  $$
  A^{-1} = \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix} \implies (A^{-1})^T = \begin{pmatrix} 2 & -3 \\ -1 & 2 \end{pmatrix}
  $$
- Therefore:
  $$
  (A^T)^{-1} = \begin{pmatrix} 2 & -3 \\ -1 & 2 \end{pmatrix}
  $$

---

### Step 3: Compute $(A^2)^{-1}$

- **Applicable Property:** $(A^2)^{-1} = (A^{-1})^2 = A^{-1} \cdot A^{-1}$.
- Multiply $A^{-1}$ by itself:
  $$
  (A^2)^{-1} = \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix} \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix}
  $$
- Compute the entries:
  - **Entry $(1, 1)$:** $(2)(2) + (-1)(-3) = 4 + 3 = 7$
  - **Entry $(1, 2)$:** $(2)(-1) + (-1)(2) = -2 - 2 = -4$
  - **Entry $(2, 1)$:** $(-3)(2) + (2)(-3) = -6 - 6 = -12$
  - **Entry $(2, 2)$:** $(-3)(-1) + (2)(2) = 3 + 4 = 7$

Thus:
$$
(A^2)^{-1} = \begin{pmatrix} 7 & -4 \\ -12 & 7 \end{pmatrix}
$$

---

## 4. Verification and Consistency Checks

1. **Reconstruction of $A$ and Independent Verification:**
   Since $(A^{-1})^{-1} = A$:
   $$
   \det(A^{-1}) = (2)(2) - (-1)(-3) = 4 - 3 = 1
   $$
   $$
   A = \frac{1}{1} \begin{pmatrix} 2 & 1 \\ 3 & 2 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 3 & 2 \end{pmatrix}
   $$

2. **Verify $(3A)^{-1}$:**
   $$
   3A = \begin{pmatrix} 6 & 3 \\ 9 & 6 \end{pmatrix} \implies \det(3A) = 36 - 27 = 9
   $$
   $$
   (3A)^{-1} = \frac{1}{9} \begin{pmatrix} 6 & -3 \\ -9 & 6 \end{pmatrix} = \begin{pmatrix} \frac{2}{3} & -\frac{1}{3} \\ -1 & \frac{2}{3} \end{pmatrix} \quad \checkmark
   $$

3. **Verify $(A^T)^{-1}$:**
   $$
   A^T = \begin{pmatrix} 2 & 3 \\ 1 & 2 \end{pmatrix} \implies \det(A^T) = 4 - 3 = 1
   $$
   $$
   (A^T)^{-1} = \frac{1}{1} \begin{pmatrix} 2 & -3 \\ -1 & 2 \end{pmatrix} = \begin{pmatrix} 2 & -3 \\ -1 & 2 \end{pmatrix} \quad \checkmark
   $$

4. **Verify $(A^2)^{-1}$:**
   $$
   A^2 = \begin{pmatrix} 2 & 1 \\ 3 & 2 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 3 & 2 \end{pmatrix} = \begin{pmatrix} 7 & 4 \\ 12 & 7 \end{pmatrix}
   $$
   $$
   \det(A^2) = 49 - 48 = 1 \implies (A^2)^{-1} = \begin{pmatrix} 7 & -4 \\ -12 & 7 \end{pmatrix} \quad \checkmark
   $$
   All three property-based calculations are validated.
