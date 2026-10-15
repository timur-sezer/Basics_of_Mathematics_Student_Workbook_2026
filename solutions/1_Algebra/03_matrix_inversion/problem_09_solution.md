# Solution to Exercise 9: Matrix Equation

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix}
$$

1. Solve the matrix equation:
   $$
   AX = B
   $$
   for the unknown matrix $X$.
2. Before carrying out the calculation, justify on which side (left or right) of the equation $A^{-1}$ must be multiplied.
3. Check the solution by explicitly computing the product $AX$ and confirming that it equals $B$.

---

## 2. Theoretical Background and Concepts

1. **Noncommutativity in Matrix Equations:**
   Because matrix multiplication is noncommutative ($MN \ne NM$), the side on which a matrix appears is critical:
   - To isolate $X$ in $AX = B$, we must pre-multiply (multiply from the **left**) by $A^{-1}$:
     $$
     A^{-1} (AX) = A^{-1} B \implies (A^{-1} A) X = A^{-1} B \implies I X = X = A^{-1} B
     $$
   - Post-multiplying (multiplying from the right) by $A^{-1}$ would produce $A X A^{-1} = B A^{-1}$, which does not simplify to $X$ because $A$ and $X$ cannot be commuted.
   - (Conversely, for an equation of the form $XA = B$, one must post-multiply by $A^{-1}$ from the right, yielding $X = BA^{-1}$).

2. **Inverting Shear Matrices:**
   For an upper triangular unipotent matrix $A = \begin{pmatrix} 1 & k \\ 0 & 1 \end{pmatrix}$, $\det A = 1$, and its inverse simply negates the shear factor:
   $$
   A^{-1} = \begin{pmatrix} 1 & -k \\ 0 & 1 \end{pmatrix}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Decision on the Side for $A^{-1}$

In the equation:
$$
AX = B
$$
the coefficient matrix $A$ appears to the **left** of $X$.
To cancel $A$, we must multiply both sides from the **left** by $A^{-1}$:
$$
A^{-1} (AX) = A^{-1} B
$$
Using the associative property:
$$
(A^{-1} A) X = A^{-1} B \implies I X = A^{-1} B \implies X = A^{-1} B
$$

Multiplying from the right would yield $(AX)A^{-1} = B A^{-1}$, which cannot isolate $X$. Therefore, **left multiplication** is strictly required.

---

### Step 2: Compute $A^{-1}$

For $A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}$:
- Determinant: $\det A = (1)(1) - (2)(0) = 1$.
- Inversion formula:
  $$
  A^{-1} = \frac{1}{1} \begin{pmatrix} 1 & -2 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & -2 \\ 0 & 1 \end{pmatrix}
  $$

---

### Step 3: Compute $X = A^{-1} B$

Multiply $A^{-1}$ by $B$:
$$
X = \begin{pmatrix} 1 & -2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix}
$$

Computing each entry:
- **Entry $(1, 1)$:**
  $$
  (1)(3) + (-2)(2) = 3 - 4 = -1
  $$
- **Entry $(1, 2)$:**
  $$
  (1)(1) + (-2)(4) = 1 - 8 = -7
  $$
- **Entry $(2, 1)$:**
  $$
  (0)(3) + (1)(2) = 0 + 2 = 2
  $$
- **Entry $(2, 2)$:**
  $$
  (0)(1) + (1)(4) = 0 + 4 = 4
  $$

Thus:
$$
X = \begin{pmatrix} -1 & -7 \\ 2 & 4 \end{pmatrix}
$$

---

### Step 4: Check by Computing $AX$

Multiply the original matrix $A$ by the computed solution $X$:
$$
AX = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -1 & -7 \\ 2 & 4 \end{pmatrix}
$$

Computing each entry:
- **Entry $(1, 1)$:**
  $$
  (1)(-1) + (2)(2) = -1 + 4 = 3
  $$
- **Entry $(1, 2)$:**
  $$
  (1)(-7) + (2)(4) = -7 + 8 = 1
  $$
- **Entry $(2, 1)$:**
  $$
  (0)(-1) + (1)(2) = 0 + 2 = 2
  $$
- **Entry $(2, 2)$:**
  $$
  (0)(-7) + (1)(4) = 0 + 4 = 4
  $$

Thus:
$$
AX = \begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix} = B
$$
The product matches matrix $B$ exactly.

---

## 4. Verification and Consistency Checks

1. **Determinant Multiplicative Check:**
   If $AX = B$, then $\det(A) \det(X) = \det(B)$:
   - $\det A = 1$.
   - $\det B = (3)(4) - (1)(2) = 12 - 2 = 10$.
   - $\det X = (-1)(4) - (-7)(2) = -4 + 14 = 10$.
   - Check: $\det(A) \det(X) = 1 \cdot 10 = 10 = \det(B) \quad \checkmark$.

2. **Column-by-Column Vector Check:**
   Partition $B = \begin{pmatrix} b_1 & b_2 \end{pmatrix}$ and $X = \begin{pmatrix} x_1 & x_2 \end{pmatrix}$:
   - $Ax_1 = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -1 \\ 2 \end{pmatrix} = \begin{pmatrix} 3 \\ 2 \end{pmatrix} = b_1 \quad \checkmark$
   - $Ax_2 = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -7 \\ 4 \end{pmatrix} = \begin{pmatrix} 1 \\ 4 \end{pmatrix} = b_2 \quad \checkmark$
