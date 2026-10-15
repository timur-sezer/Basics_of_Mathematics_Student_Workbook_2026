# Solution to Exercise 6: A System with a Parameter — Which Cases Actually Occur?

## 1. Problem Statement

Analyze the linear system depending on the real parameter $a$:
$$
\begin{cases}
x + y = 2, \\
ax + ay = 4.
\end{cases}
$$

1. Among the three theoretical possibilities:
   - **Exactly one solution**,
   - **Infinitely many solutions**,
   - **No solution**,
   determine which cases actually occur and state for which values of $a$ they arise.
2. If any of the three cases cannot occur for any value of $a$, provide a complete mathematical explanation of why it is impossible.

---

## 2. Theoretical Background and Concepts

1. **Rouché–Capelli Theorem for Systems with Parameters:**
   For a system $Ax = b$ in $n$ variables:
   - A unique solution exists if and only if $\operatorname{rank}(A) = \operatorname{rank}[A \mid b] = n$.
   - Infinitely many solutions exist if and only if $\operatorname{rank}(A) = \operatorname{rank}[A \mid b] < n$.
   - No solution exists if and only if $\operatorname{rank}(A) < \operatorname{rank}[A \mid b]$.

2. **Rank and Determinant of the Coefficient Matrix:**
   For a $2 \times 2$ system, a unique solution strictly requires that the coefficient matrix $A$ be invertible, meaning $\det A \ne 0$. If $\det A = 0$ identically for all parameter values, the rank can never reach $2$, entirely ruling out the unique solution case.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up and Eliminate the Augmented Matrix

Write the augmented matrix $[A \mid b]$:
$$
[A \mid b] = \left(\begin{array}{cc|c}
1 & 1 & 2 \\
a & a & 4
\end{array}\right)
$$

Perform the elementary row operation to eliminate the $a$ in Row 2:
$$
R_2 \leftarrow R_2 - a R_1
$$

Computing the new second row:
- Left block: $\begin{pmatrix} a & a \end{pmatrix} - a \begin{pmatrix} 1 & 1 \end{pmatrix} = \begin{pmatrix} a - a & a - a \end{pmatrix} = \begin{pmatrix} 0 & 0 \end{pmatrix}$
- Right block: $4 - a(2) = 4 - 2a$

The row echelon form of the augmented matrix is:
$$
\left(\begin{array}{cc|c}
1 & 1 & 2 \\
0 & 0 & 4 - 2a
\end{array}\right)
$$

---

### Step 2: Case Analysis Based on $4 - 2a$

The second row represents the equation:
$$
0 \cdot x + 0 \cdot y = 4 - 2a \implies 0 = 4 - 2a
$$

1. **Case 1: $4 - 2a = 0 \iff a = 2$**
   - When $a = 2$, Row 2 becomes:
     $$
     \left(\begin{array}{cc|c} 0 & 0 & 0 \end{array}\right)
     $$
   - The augmented matrix is:
     $$
     \left(\begin{array}{cc|c} 1 & 1 & 2 \\ 0 & 0 & 0 \end{array}\right)
     $$
   - We have $\operatorname{rank}(A) = \operatorname{rank}[A \mid b] = 1 < 2$ (one free variable, $y = t$).
   - The system reduces to the single equation $x + y = 2 \implies x = 2 - t$.
   - **Conclusion:** **Infinitely many solutions** occur when **$a = 2$**.

2. **Case 2: $4 - 2a \ne 0 \iff a \ne 2$**
   - When $a \ne 2$, the right-hand side $4 - 2a$ is non-zero.
   - Row 2 yields the contradiction $0 = 4 - 2a \ne 0$.
   - Here, $\operatorname{rank}(A) = 1$, but $\operatorname{rank}[A \mid b] = 2$.
   - **Conclusion:** **No solution (inconsistent)** occurs for all **$a \ne 2$**.

---

### Step 3: Why "Exactly One Solution" Cannot Occur

The case of **exactly one solution cannot occur for any value of $a$**.

**Mathematical Explanation:**
1. Consider the coefficient matrix:
   $$
   A = \begin{pmatrix} 1 & 1 \\ a & a \end{pmatrix}
   $$
2. Compute its determinant for an arbitrary $a \in \mathbb{R}$:
   $$
   \det A = (1)(a) - (1)(a) = a - a = 0
   $$
3. The determinant is identically zero for **all** real numbers $a$.
4. By the Invertible Matrix Theorem, a square $2 \times 2$ system has a unique solution if and only if $\det A \ne 0$ ($\operatorname{rank}(A) = 2$).
5. Because Row 2 of $A$, $\begin{pmatrix} a & a \end{pmatrix} = a \begin{pmatrix} 1 & 1 \end{pmatrix}$, is always parallel to Row 1 for every choice of $a$, the columns/rows of $A$ are permanently linearly dependent. The rank of $A$ can never equal $2$.
6. Therefore, the possibility of a unique solution is completely precluded by the intrinsic geometry of the system.

---

## 4. Verification and Consistency Checks

1. **Geometric Parallelism Check:**
   - Equation 1 represents the line $L_1: y = -x + 2$ (slope $m_1 = -1$).
   - Equation 2 is $a(x + y) = 4$.
     - If $a = 0$: $0 = 4$ (no solution, impossible condition).
     - If $a \ne 0$: $x + y = \frac{4}{a} \implies L_2: y = -x + \frac{4}{a}$ (slope $m_2 = -1$).
   - Since both lines always have slope $-1$, they are parallel for every $a \ne 0$:
     - When $\frac{4}{a} = 2 \iff a = 2$, the lines coincide ($L_1 = L_2$), giving infinitely many intersection points.
     - When $\frac{4}{a} \ne 2 \iff a \ne 2$, the lines are strictly parallel and distinct, giving zero intersection points.
   - Non-parallel lines can never be formed, confirming that a single intersection point is impossible.
