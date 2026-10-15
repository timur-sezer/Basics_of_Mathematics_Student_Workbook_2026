# Solution to Exercise 15: Two Methods for Solving the Same System

## 1. Problem Statement

Given the linear system $Ax = b$, where:
$$
A = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix}, \qquad b = \begin{pmatrix} 7 \\ 8 \end{pmatrix}
$$

1. Solve the system using the inverse matrix method: $x = A^{-1} b$.
2. Solve the system using Gaussian elimination on the augmented matrix $[A \mid b]$.
3. Compare both solutions and the number of essential arithmetic steps required.
4. Conclude which method was simpler in this specific example and explain when each method is preferred in practice.

---

## 2. Theoretical Background and Concepts

1. **The Inverse Matrix Method ($x = A^{-1} b$):**
   - Requires finding the full inverse matrix $A^{-1}$.
   - Once $A^{-1}$ is known, the solution is obtained by a single matrix-vector multiplication $x = A^{-1} b$.
   - **Advantage:** Ideal when the system $Ax = b$ must be solved repeatedly for many different right-hand side vectors $b_1, b_2, \dots, b_k$, as $A^{-1}$ is precomputed once.

2. **Gaussian Elimination (Row Reduction):**
   - Applies elementary row operations directly to the augmented matrix $[A \mid b]$ to achieve an upper-triangular form, followed by back-substitution.
   - **Advantage:** For a single right-hand side vector $b$, Gaussian elimination is computationally more efficient: for an $n \times n$ system, elimination takes approximately $\frac{2}{3} n^3$ operations, whereas computing $A^{-1}$ and multiplying takes approximately $2 n^3$ operations (three times more effort).

---

## 3. Detailed Step-by-Step Solution

### Method 1: Solving via the Inverse Matrix ($x = A^{-1} b$)

1. **Find $A^{-1}$:**
   - Compute the determinant of $A$:
     $$
     \det A = (2)(3) - (1)(1) = 6 - 1 = 5 \ne 0
     $$
   - Apply the $2 \times 2$ inverse formula:
     $$
     A^{-1} = \frac{1}{\det A} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix} = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix}
     $$

2. **Compute $x = A^{-1} b$:**
   $$
   x = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix} \begin{pmatrix} 7 \\ 8 \end{pmatrix}
   $$
   - First component: $3(7) + (-1)(8) = 21 - 8 = 13$
   - Second component: $(-1)(7) + 2(8) = -7 + 16 = 9$

   Multiplying by the scalar $\frac{1}{5}$:
   $$
   x = \begin{pmatrix} \frac{13}{5} \\ \frac{9}{5} \end{pmatrix} = \begin{pmatrix} 2.6 \\ 1.8 \end{pmatrix}
   $$

---

### Method 2: Solving via Gaussian Elimination

1. **Set up the Augmented Matrix $[A \mid b]$:**
   $$
   [A \mid b] = \left(\begin{array}{cc|c} 2 & 1 & 7 \\ 1 & 3 & 8 \end{array}\right)
   $$

2. **Row Interchange ($R_1 \leftrightarrow R_2$):**
   Swap rows to obtain a convenient pivot of $1$ in position $(1, 1)$:
   $$
   \left(\begin{array}{cc|c} 1 & 3 & 8 \\ 2 & 1 & 7 \end{array}\right)
   $$

3. **Row Elimination ($R_2 \leftarrow R_2 - 2R_1$):**
   Eliminate the entry $2$ below the pivot:
   $$
   \begin{pmatrix} 2 & 1 & 7 \end{pmatrix} - 2\begin{pmatrix} 1 & 3 & 8 \end{pmatrix} = \begin{pmatrix} 2 - 2 & 1 - 6 & 7 - 16 \end{pmatrix} = \begin{pmatrix} 0 & -5 & -9 \end{pmatrix}
   $$
   The upper-triangular augmented matrix is:
   $$
   \left(\begin{array}{cc|c} 1 & 3 & 8 \\ 0 & -5 & -9 \end{array}\right)
   $$

4. **Back-Substitution:**
   - From Row 2:
     $$
     -5 x_2 = -9 \implies x_2 = \frac{9}{5}
     $$
   - From Row 1:
     $$
     x_1 + 3 x_2 = 8 \implies x_1 = 8 - 3\left(\frac{9}{5}\right) = \frac{40 - 27}{5} = \frac{13}{5}
     $$

   Thus:
   $$
   x = \begin{pmatrix} \frac{13}{5} \\ \frac{9}{5} \end{pmatrix}
   $$

---

### Step 3: Comparison of Methods and Complexity

1. **Result Agreement:**
   Both calculation paths yield the identical solution vector:
   $$
   x = \begin{pmatrix} \frac{13}{5} \\ \frac{9}{5} \end{pmatrix} = \begin{pmatrix} 2.6 \\ 1.8 \end{pmatrix}
   $$

2. **Step Count and Computational Effort:**
   - **Method 1 (Inverse):** Required evaluating $\det A$ ($3$ operations), forming the $2 \times 2$ inverse matrix, and computing the matrix-vector product $A^{-1}b$ ($4$ multiplications, $2$ additions, plus scalar division).
   - **Method 2 (Elimination):** Required only $1$ row swap, $1$ row operation (eliminating position $(2,1)$), and immediate back-substitution of $2$ scalar linear equations.

3. **Conclusion on Simplicity:**
   - **In this example, Gaussian elimination is simpler and faster.** It computes the target vector directly without the auxiliary overhead of calculating and storing the entire inverse matrix $A^{-1}$.
   - **General Rule:** For solving a single specific linear system $Ax = b$, Gaussian elimination is always preferred. Finding the explicit inverse $A^{-1}$ is advantageous primarily when $A$ is fixed and solutions must be found for multiple different vectors $b$.

---

## 4. Verification and Consistency Checks

1. **Substitute into Equation 1:**
   $$
   2x_1 + x_2 = 2\left(\frac{13}{5}\right) + \frac{9}{5} = \frac{26 + 9}{5} = \frac{35}{5} = 7 = b_1 \quad \checkmark
   $$

2. **Substitute into Equation 2:**
   $$
   x_1 + 3x_2 = \frac{13}{5} + 3\left(\frac{9}{5}\right) = \frac{13 + 27}{5} = \frac{40}{5} = 8 = b_2 \quad \checkmark
   $$
   Both equations are satisfied with absolute precision.
