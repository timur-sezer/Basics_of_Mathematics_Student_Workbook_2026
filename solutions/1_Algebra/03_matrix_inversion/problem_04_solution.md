# Solution to Exercise 4: Gauss–Jordan Inversion

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 2 \\ 3 & 5 \end{pmatrix}
$$

1. Find the inverse matrix $A^{-1}$ using the Gauss–Jordan elimination method.
2. Show the augmented matrix $[A \mid I]$ after each successive row operation.
3. Explain why transforming the left block to the identity matrix $I$ necessarily produces the inverse $A^{-1}$ in the right block.

---

## 2. Theoretical Background and Concepts

1. **The Augmented Matrix $[A \mid I]$:**
   To invert an $n \times n$ matrix $A$, we form the $n \times 2n$ augmented matrix:
   $$
   [A \mid I_n]
   $$
   where $I_n$ is the $n \times n$ identity matrix.

2. **Elementary Matrices and Row Operations:**
   Every elementary row operation on an augmented matrix corresponds to multiplying the matrix from the left by an invertible **elementary matrix** $E$:
   $$
   \text{Row Operation} \iff [A \mid I] \mapsto [E A \mid E I] = [E A \mid E]
   $$

3. **Theoretical Justification of Gauss–Jordan Elimination:**
   If a sequence of $k$ elementary row operations represented by elementary matrices $E_1, E_2, \dots, E_k$ transforms the left block $A$ into the identity matrix $I$:
   $$
   (E_k \cdots E_2 E_1) A = I
   $$
   Let $E = E_k \cdots E_2 E_1$. Since $E A = I$, by definition of matrix inverse:
   $$
   E = A^{-1}
   $$
   Applying this same sequence of row operations to the right block $I$ simultaneously computes:
   $$
   (E_k \cdots E_2 E_1) I = E I = E = A^{-1}
   $$
   Hence, when the augmented matrix reaches reduced row echelon form:
   $$
   [A \mid I] \xrightarrow{\text{Gauss–Jordan}} [I \mid A^{-1}]
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up the Augmented Matrix

Place $A$ and the $2 \times 2$ identity matrix $I$ side by side:
$$
[A \mid I] = \left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 3 & 5 & 0 & 1 \end{array}\right)
$$

---

### Step 2: Eliminate the Entry Below the First Pivot

The pivot in Row 1, Column 1 is already $1$.
To eliminate the $3$ in Row 2, subtract $3R_1$ from $R_2$:
$$
R_2 \leftarrow R_2 - 3R_1
$$

Computing the new second row:
- Left block: $(3, 5) - 3(1, 2) = (3 - 3, 5 - 6) = (0, -1)$
- Right block: $(0, 1) - 3(1, 0) = (0 - 3, 1 - 0) = (-3, 1)$

The augmented matrix becomes:
$$
\left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & -1 & -3 & 1 \end{array}\right)
$$

---

### Step 3: Normalize the Second Pivot

Make the leading entry of Row 2 equal to $+1$ by multiplying $R_2$ by $-1$:
$$
R_2 \leftarrow -R_2
$$

Computing the new second row:
- Left block: $-(0, -1) = (0, 1)$
- Right block: $-(-3, 1) = (3, -1)$

The augmented matrix becomes:
$$
\left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & 1 & 3 & -1 \end{array}\right)
$$

---

### Step 4: Eliminate the Entry Above the Second Pivot

To eliminate the entry $2$ in Row 1 using the pivot in Row 2, subtract $2R_2$ from $R_1$:
$$
R_1 \leftarrow R_1 - 2R_2
$$

Computing the new first row:
- Left block: $(1, 2) - 2(0, 1) = (1 - 0, 2 - 2) = (1, 0)$
- Right block: $(1, 0) - 2(3, -1) = (1 - 6, 0 - (-2)) = (-5, 2)$

The augmented matrix becomes:
$$
\left(\begin{array}{cc|cc} 1 & 0 & -5 & 2 \\ 0 & 1 & 3 & -1 \end{array}\right)
$$

The left block is now the identity matrix $I$.

---

### Step 5: Read Off the Inverse Matrix

The right block is the desired inverse:
$$
A^{-1} = \begin{pmatrix} -5 & 2 \\ 3 & -1 \end{pmatrix}
$$

---

## 4. Verification and Consistency Checks

1. **Direct Matrix Multiplication ($A A^{-1} = I$):**
   $$
   A A^{-1} = \begin{pmatrix} 1 & 2 \\ 3 & 5 \end{pmatrix} \begin{pmatrix} -5 & 2 \\ 3 & -1 \end{pmatrix} = \begin{pmatrix} 1(-5) + 2(3) & 1(2) + 2(-1) \\ 3(-5) + 5(3) & 3(2) + 5(-1) \end{pmatrix}
   $$
   $$
   = \begin{pmatrix} -5 + 6 & 2 - 2 \\ -15 + 15 & 6 - 5 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I \quad \checkmark
   $$

2. **Verification via $2 \times 2$ Determinant Formula:**
   For $A = \begin{pmatrix} 1 & 2 \\ 3 & 5 \end{pmatrix}$:
   $$
   \det A = (1)(5) - (2)(3) = 5 - 6 = -1
   $$
   Using the formula:
   $$
   A^{-1} = \frac{1}{-1} \begin{pmatrix} 5 & -2 \\ -3 & 1 \end{pmatrix} = \begin{pmatrix} -5 & 2 \\ 3 & -1 \end{pmatrix} \quad \checkmark
   $$
   Both methods produce the identical inverse matrix.
