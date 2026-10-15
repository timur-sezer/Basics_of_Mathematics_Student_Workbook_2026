# Solution to Exercise 6: Solving a System Using the Inverse

## 1. Problem Statement

Given the linear system $Ax = b$, where:
$$
A = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix}, \qquad b = \begin{pmatrix} 5 \\ 7 \end{pmatrix}
$$

1. Find the inverse matrix $A^{-1}$.
2. Solve the system for the unknown vector $x$ using the matrix equation:
   $$
   x = A^{-1} b
   $$
3. Substitute the resulting vector back into $Ax$ to check and verify the solution.

---

## 2. Theoretical Background and Concepts

1. **Solving Matrix Equations via Inverses:**
   Given a linear system of $n$ equations in $n$ unknowns written in matrix form:
   $$
   Ax = b
   $$
   If the coefficient matrix $A$ is invertible ($A^{-1}$ exists), we can multiply both sides of the equation from the left by $A^{-1}$:
   $$
   A^{-1}(Ax) = A^{-1}b \implies (A^{-1}A)x = A^{-1}b \implies Ix = A^{-1}b \implies x = A^{-1}b
   $$
   Because the inverse is unique, this yields the one and only solution to the system.

2. **Inversion of a $2 \times 2$ Matrix:**
   For $A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$:
   $$
   A^{-1} = \frac{1}{ad - bc} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $A^{-1}$

1. **Determinant of $A$:**
   $$
   \det A = (2)(3) - (1)(1) = 6 - 1 = 5
   $$
   Since $\det A = 5 \ne 0$, $A$ is invertible.

2. **Apply the $2 \times 2$ inversion formula:**
   $$
   A^{-1} = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix} = \begin{pmatrix} \frac{3}{5} & -\frac{1}{5} \\ -\frac{1}{5} & \frac{2}{5} \end{pmatrix}
   $$

---

### Step 2: Compute $x = A^{-1} b$

Multiply the inverse matrix $A^{-1}$ by the vector $b$:
$$
x = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix} \begin{pmatrix} 5 \\ 7 \end{pmatrix}
$$

Compute the matrix-vector product:
- **First component ($x_1$):**
  $$
  3(5) + (-1)(7) = 15 - 7 = 8
  $$
- **Second component ($x_2$):**
  $$
  (-1)(5) + (2)(7) = -5 + 14 = 9
  $$

Multiplying by the scalar $\frac{1}{5}$:
$$
x = \begin{pmatrix} \frac{8}{5} \\ \frac{9}{5} \end{pmatrix}
$$

In decimal form, $x = \begin{pmatrix} 1.6 \\ 1.8 \end{pmatrix}$.

---

### Step 3: Check by Direct Substitution into $Ax = b$

Substitute $x = \begin{pmatrix} 8/5 \\ 9/5 \end{pmatrix}$ back into the left-hand side $Ax$:
$$
Ax = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix} \begin{pmatrix} \frac{8}{5} \\ \frac{9}{5} \end{pmatrix}
$$

Evaluate each component:
- **Row 1:**
  $$
  2\left(\frac{8}{5}\right) + 1\left(\frac{9}{5}\right) = \frac{16}{5} + \frac{9}{5} = \frac{25}{5} = 5
  $$
- **Row 2:**
  $$
  1\left(\frac{8}{5}\right) + 3\left(\frac{9}{5}\right) = \frac{8}{5} + \frac{27}{5} = \frac{35}{5} = 7
  $$

Thus:
$$
Ax = \begin{pmatrix} 5 \\ 7 \end{pmatrix} = b
$$
The substitution confirms the solution identically.

---

## 4. Verification and Consistency Checks

1. **Independent Verification via Elimination / Substitution:**
   The scalar system of equations is:
   $$
   \begin{cases}
   2x_1 + x_2 = 5 \implies x_2 = 5 - 2x_1 \\
   x_1 + 3x_2 = 7
   \end{cases}
   $$
   Substitute $x_2$ into equation (2):
   $$
   x_1 + 3(5 - 2x_1) = 7 \implies x_1 + 15 - 6x_1 = 7 \implies -5x_1 = -8 \implies x_1 = \frac{8}{5}
   $$
   Then:
   $$
   x_2 = 5 - 2\left(\frac{8}{5}\right) = \frac{25 - 16}{5} = \frac{9}{5}
   $$
   Both components match our matrix solution.

2. **Cramer's Rule Check:**
   - $x_1 = \frac{\det\begin{pmatrix}5&1\\7&3\end{pmatrix}}{\det A} = \frac{15 - 7}{5} = \frac{8}{5} \quad \checkmark$
   - $x_2 = \frac{\det\begin{pmatrix}2&5\\1&7\end{pmatrix}}{\det A} = \frac{14 - 5}{5} = \frac{9}{5} \quad \checkmark$
