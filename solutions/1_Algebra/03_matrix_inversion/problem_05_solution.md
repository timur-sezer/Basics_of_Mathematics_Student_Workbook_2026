# Solution to Exercise 5: A 3×3 Matrix

## 1. Problem Statement

Given the $3 \times 3$ matrix:
$$
A = \begin{pmatrix} 1 & 1 & 0 \\ 0 & 1 & 1 \\ 1 & 0 & 1 \end{pmatrix}
$$

1. Use Gauss–Jordan elimination to find the inverse matrix $A^{-1}$.
2. Check the calculated result by computing the product $A A^{-1}$ and confirming that it equals the $3 \times 3$ identity matrix $I_3$.

---

## 2. Theoretical Background and Concepts

1. **Gauss–Jordan Inversion for $3 \times 3$ Matrices:**
   We form the $3 \times 6$ augmented matrix:
   $$
   [A \mid I_3] = \left(\begin{array}{ccc|ccc}
   a_{11} & a_{12} & a_{13} & 1 & 0 & 0 \\
   a_{21} & a_{22} & a_{23} & 0 & 1 & 0 \\
   a_{31} & a_{32} & a_{33} & 0 & 0 & 1
   \end{array}\right)
   $$
   Using elementary row operations, we reduce the left block into the identity matrix $I_3$. The sequence of row operations automatically transforms the right block into $A^{-1}$:
   $$
   [A \mid I_3] \xrightarrow{\text{row operations}} [I_3 \mid A^{-1}]
   $$

2. **Invertibility Condition:**
   Gauss–Jordan elimination succeeds if and only if matrix $A$ has full rank ($3$ non-zero pivots), which is equivalent to $\det A \ne 0$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up the Augmented Matrix

$$
[A \mid I_3] = \left(\begin{array}{ccc|ccc}
1 & 1 & 0 & 1 & 0 & 0 \\
0 & 1 & 1 & 0 & 1 & 0 \\
1 & 0 & 1 & 0 & 0 & 1
\end{array}\right)
$$

---

### Step 2: Forward Elimination (Create Upper-Triangular Form)

1. **Eliminate entry $(3, 1)$:**
   Subtract Row 1 from Row 3 ($R_3 \leftarrow R_3 - R_1$):
   $$
   R_3 - R_1 = \begin{pmatrix} 1 & 0 & 1 & 0 & 0 & 1 \end{pmatrix} - \begin{pmatrix} 1 & 1 & 0 & 1 & 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & -1 & 1 & -1 & 0 & 1 \end{pmatrix}
   $$
   The augmented matrix becomes:
   $$
   \left(\begin{array}{ccc|ccc}
   1 & 1 & 0 & 1 & 0 & 0 \\
   0 & 1 & 1 & 0 & 1 & 0 \\
   0 & -1 & 1 & -1 & 0 & 1
   \end{array}\right)
   $$

2. **Eliminate entry $(3, 2)$:**
   Add Row 2 to Row 3 ($R_3 \leftarrow R_3 + R_2$):
   $$
   R_3 + R_2 = \begin{pmatrix} 0 & -1 & 1 & -1 & 0 & 1 \end{pmatrix} + \begin{pmatrix} 0 & 1 & 1 & 0 & 1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 0 & 2 & -1 & 1 & 1 \end{pmatrix}
   $$
   The augmented matrix becomes:
   $$
   \left(\begin{array}{ccc|ccc}
   1 & 1 & 0 & 1 & 0 & 0 \\
   0 & 1 & 1 & 0 & 1 & 0 \\
   0 & 0 & 2 & -1 & 1 & 1
   \end{array}\right)
   $$

---

### Step 3: Back-Substitution (Reduce to Identity Matrix)

3. **Normalize the third pivot to $1$:**
   Multiply Row 3 by $\frac{1}{2}$ ($R_3 \leftarrow \frac{1}{2} R_3$):
   $$
   R_3 \leftarrow \begin{pmatrix} 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{pmatrix}
   $$
   The augmented matrix becomes:
   $$
   \left(\begin{array}{ccc|ccc}
   1 & 1 & 0 & 1 & 0 & 0 \\
   0 & 1 & 1 & 0 & 1 & 0 \\
   0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
   \end{array}\right)
   $$

4. **Eliminate entry $(2, 3)$:**
   Subtract Row 3 from Row 2 ($R_2 \leftarrow R_2 - R_3$):
   $$
   R_2 - R_3 = \begin{pmatrix} 0 & 1 & 1 & 0 & 1 & 0 \end{pmatrix} - \begin{pmatrix} 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{pmatrix} = \begin{pmatrix} 0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \end{pmatrix}
   $$
   The augmented matrix becomes:
   $$
   \left(\begin{array}{ccc|ccc}
   1 & 1 & 0 & 1 & 0 & 0 \\
   0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\
   0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
   \end{array}\right)
   $$

5. **Eliminate entry $(1, 2)$:**
   Subtract Row 2 from Row 1 ($R_1 \leftarrow R_1 - R_2$):
   $$
   R_1 - R_2 = \begin{pmatrix} 1 & 1 & 0 & 1 & 0 & 0 \end{pmatrix} - \begin{pmatrix} 0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \end{pmatrix} = \begin{pmatrix} 1 & 0 & 0 & \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \end{pmatrix}
   $$
   The augmented matrix is now fully reduced:
   $$
   \left(\begin{array}{ccc|ccc}
   1 & 0 & 0 & \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\
   0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\
   0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
   \end{array}\right)
   $$

---

### Step 4: Extract the Inverse Matrix

The right-hand block gives $A^{-1}$:
$$
A^{-1} = \begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\
\frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\
-\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
\end{pmatrix} = \frac{1}{2} \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ -1 & 1 & 1 \end{pmatrix}
$$

---

### Step 5: Check by Matrix Multiplication

Multiply $A$ by $A^{-1}$:
$$
A A^{-1} = \begin{pmatrix} 1 & 1 & 0 \\ 0 & 1 & 1 \\ 1 & 0 & 1 \end{pmatrix} \cdot \frac{1}{2} \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ -1 & 1 & 1 \end{pmatrix}
$$

Compute the product entry-by-entry:
- Row 1:
  - $(1, 1)$: $1(1) + 1(1) + 0(-1) = 2$
  - $(1, 2)$: $1(-1) + 1(1) + 0(1) = 0$
  - $(1, 3)$: $1(1) + 1(-1) + 0(1) = 0$
- Row 2:
  - $(2, 1)$: $0(1) + 1(1) + 1(-1) = 0$
  - $(2, 2)$: $0(-1) + 1(1) + 1(1) = 2$
  - $(2, 3)$: $0(1) + 1(-1) + 1(1) = 0$
- Row 3:
  - $(3, 1)$: $1(1) + 0(1) + 1(-1) = 0$
  - $(3, 2)$: $1(-1) + 0(1) + 1(1) = 0$
  - $(3, 3)$: $1(1) + 0(-1) + 1(1) = 2$

Multiplying by the scalar $\frac{1}{2}$:
$$
A A^{-1} = \frac{1}{2} \begin{pmatrix} 2 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 2 \end{pmatrix} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} = I_3
$$
The product is identically the identity matrix $I_3$.

---

## 4. Verification and Consistency Checks

1. **Verification via Adjugate Formula:**
   Compute $\det A$:
   $$
   \det A = 1(1 \cdot 1 - 1 \cdot 0) - 1(0 \cdot 1 - 1 \cdot 1) + 0 = 1 - (-1) = 2
   $$
   Compute the cofactor matrix $C$:
   - $C_{11} = 1, \; C_{12} = 1, \; C_{13} = -1$
   - $C_{21} = -1, \; C_{22} = 1, \; C_{23} = 1$
   - $C_{31} = 1, \; C_{32} = -1, \; C_{33} = 1$
   The adjugate is $\operatorname{adj}(A) = C^T$:
   $$
   \operatorname{adj}(A) = \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ -1 & 1 & 1 \end{pmatrix}
   $$
   Therefore:
   $$
   A^{-1} = \frac{1}{\det A} \operatorname{adj}(A) = \frac{1}{2} \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ -1 & 1 & 1 \end{pmatrix} \quad \checkmark
   $$
   Matches the Gauss–Jordan result exactly.
