# Solution to Exercise 4: Matrix Multiplication and Noncommutativity

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix}
$$

1. Compute the product $AB$.
2. Compute the product $BA$.
3. Determine whether $AB = BA$.
4. Use this example to explain what noncommutativity of matrix multiplication means.

---

## 2. Theoretical Background and Concepts

1. **Definition of Matrix Multiplication ($2 \times 2$ Case):**
   For two $2 \times 2$ matrices:
   $$
   M = \begin{pmatrix} m_{11} & m_{12} \\ m_{21} & m_{22} \end{pmatrix}, \qquad N = \begin{pmatrix} n_{11} & n_{12} \\ n_{21} & n_{22} \end{pmatrix}
   $$
   the product $MN$ is computed by taking the dot product of rows of $M$ with columns of $N$:
   $$
   MN = \begin{pmatrix}
   m_{11}n_{11} + m_{12}n_{21} & m_{11}n_{12} + m_{12}n_{22} \\
   m_{21}n_{11} + m_{22}n_{21} & m_{21}n_{12} + m_{22}n_{22}
   \end{pmatrix}
   $$

2. **Commutativity vs. Noncommutativity:**
   - In ordinary arithmetic of numbers, multiplication is commutative: for any real numbers $a, b$, $a \cdot b = b \cdot a$.
   - In matrix algebra, multiplication is generally **noncommutative**. Even when two matrices are square of the same dimension (so both $AB$ and $BA$ exist and have identical sizes), in general:
     $$
     AB \ne BA
     $$
   Matrices that satisfy $AB = BA$ are special exceptions said to *commute*.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $AB$

Multiply $A$ by $B$:
$$
AB = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix}
$$

Compute each entry:
- **Entry $(1, 1)$:** Row 1 of $A$ and Column 1 of $B$:
  $$
  (1)(2) + (2)(3) = 2 + 6 = 8
  $$
- **Entry $(1, 2)$:** Row 1 of $A$ and Column 2 of $B$:
  $$
  (1)(0) + (2)(1) = 0 + 2 = 2
  $$
- **Entry $(2, 1)$:** Row 2 of $A$ and Column 1 of $B$:
  $$
  (0)(2) + (1)(3) = 0 + 3 = 3
  $$
- **Entry $(2, 2)$:** Row 2 of $A$ and Column 2 of $B$:
  $$
  (0)(0) + (1)(1) = 0 + 1 = 1
  $$

Thus:
$$
AB = \begin{pmatrix} 8 & 2 \\ 3 & 1 \end{pmatrix}
$$

### Step 2: Compute $BA$

Multiply $B$ by $A$:
$$
BA = \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix} \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}
$$

Compute each entry:
- **Entry $(1, 1)$:** Row 1 of $B$ and Column 1 of $A$:
  $$
  (2)(1) + (0)(0) = 2 + 0 = 2
  $$
- **Entry $(1, 2)$:** Row 1 of $B$ and Column 2 of $A$:
  $$
  (2)(2) + (0)(1) = 4 + 0 = 4
  $$
- **Entry $(2, 1)$:** Row 2 of $B$ and Column 1 of $A$:
  $$
  (3)(1) + (1)(0) = 3 + 0 = 3
  $$
- **Entry $(2, 2)$:** Row 2 of $B$ and Column 2 of $A$:
  $$
  (3)(2) + (1)(1) = 6 + 1 = 7
  $$

Thus:
$$
BA = \begin{pmatrix} 2 & 4 \\ 3 & 7 \end{pmatrix}
$$

### Step 3: Comparison

Comparing the matrices:
$$
AB = \begin{pmatrix} 8 & 2 \\ 3 & 1 \end{pmatrix} \ne \begin{pmatrix} 2 & 4 \\ 3 & 7 \end{pmatrix} = BA
$$
Therefore, **$AB \ne BA$**.

### Step 4: Explanation of Noncommutativity

Noncommutativity of matrix multiplication means that the **order of factors directly affects the outcome**. 

Geometrically and operationally:
- Matrices represent linear transformations.
- The product $AB$ corresponds to applying transformation $B$ first, followed by transformation $A$: $(AB)x = A(Bx)$.
- The product $BA$ corresponds to applying transformation $A$ first, followed by transformation $B$: $(BA)x = B(Ax)$.
- In general, changing the order in which two geometric transformations are performed produces a completely different result.
- As shown by this concrete example, even for simple $2 \times 2$ matrices with integer coefficients, reversing the order yields entirely different matrix entries ($8 \ne 2$, $2 \ne 4$, $1 \ne 7$).

---

## 4. Verification and Consistency Checks

1. **Determinant Multiplicative Property Check:**
   Determinants satisfy $\det(MN) = \det(M)\det(N)$. Since real scalar multiplication commutes, $\det(AB) = \det(BA) = \det(A)\det(B)$:
   - For $A$: $\det(A) = (1)(1) - (2)(0) = 1$.
   - For $B$: $\det(B) = (2)(1) - (0)(3) = 2$.
   - Expected determinant of the product: $\det(A)\det(B) = 1 \cdot 2 = 2$.
   - Determinant of our $AB$:
     $$
     \det(AB) = (8)(1) - (2)(3) = 8 - 6 = 2 \quad \checkmark
     $$
   - Determinant of our $BA$:
     $$
     \det(BA) = (2)(7) - (4)(3) = 14 - 12 = 2 \quad \checkmark
     $$
   Both determinants equal $2$, confirming our arithmetic while highlighting that matrices can have the exact same determinant without being equal.

2. **Trace Check:**
   The cyclic property of trace states $\operatorname{tr}(AB) = \operatorname{tr}(BA)$:
   - $\operatorname{tr}(AB) = 8 + 1 = 9$.
   - $\operatorname{tr}(BA) = 2 + 7 = 9$.
   The traces match, further verifying algebraic consistency.

