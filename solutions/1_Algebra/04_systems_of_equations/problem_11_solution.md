# Solution to Exercise 11: A Parameter in a System of Three Equations

## 1. Problem Statement

Analyze the number of solutions of the linear system depending on the real parameter $t$:
$$
\begin{cases}
x + y + z = 1, \\
x + ty + z = 2, \\
x + y + tz = 3.
\end{cases}
$$

1. Use Gaussian elimination to reduce the system.
2. Identify the critical value of $t$ for which the standard elimination step (division by pivot) ceases to be valid.
3. Completely classify the system for all $t \in \mathbb{R}$ into the categories: exactly one solution, infinitely many solutions, or no solution.
4. When a unique solution exists, express $(x, y, z)$ in terms of $t$.

---

## 2. Theoretical Background and Concepts

1. **Rouché–Capelli Theorem with Parameters:**
   For a linear system $Ax = b$ with $n = 3$ variables:
   - A **unique solution** exists if and only if $\operatorname{rank}(A) = \operatorname{rank}[A \mid b] = 3$, which for a square system is equivalent to $\det(A) \ne 0$.
   - **Infinitely many solutions** exist if and only if $\operatorname{rank}(A) = \operatorname{rank}[A \mid b] < 3$.
   - **No solution** (inconsistent) occurs if and only if $\operatorname{rank}(A) < \operatorname{rank}[A \mid b]$ (a contradiction row $\left(\begin{array}{ccc|c} 0 & 0 & 0 & c \end{array}\right)$ with $c \ne 0$).

2. **Validity of Row Operations:**
   Multiplying or dividing a row by an expression involving a parameter $t$ is an elementary row operation **if and only if** that expression is non-zero. If the pivot expression equals zero, division by zero is undefined, and that specific parameter value must be investigated separately.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up and Eliminate the Augmented Matrix

Write the augmented matrix $[A \mid b]$:
$$
[A \mid b] = \left(\begin{array}{ccc|c}
1 & 1 & 1 & 1 \\
1 & t & 1 & 2 \\
1 & 1 & t & 3
\end{array}\right)
$$

Perform elementary row operations using Row 1 as the pivot row:
1. **$R_2 \leftarrow R_2 - R_1$:**
   - Left side: $\begin{pmatrix} 1 & t & 1 \end{pmatrix} - \begin{pmatrix} 1 & 1 & 1 \end{pmatrix} = \begin{pmatrix} 0 & t - 1 & 0 \end{pmatrix}$
   - Right side: $2 - 1 = 1$

2. **$R_3 \leftarrow R_3 - R_1$:**
   - Left side: $\begin{pmatrix} 1 & 1 & t \end{pmatrix} - \begin{pmatrix} 1 & 1 & 1 \end{pmatrix} = \begin{pmatrix} 0 & 0 & t - 1 \end{pmatrix}$
   - Right side: $3 - 1 = 2$

The reduced augmented matrix is:
$$
\left(\begin{array}{ccc|c}
1 & 1 & 1 & 1 \\
0 & t - 1 & 0 & 1 \\
0 & 0 & t - 1 & 2
\end{array}\right)
$$

The matrix is now in upper triangular form. The pivot positions in columns 2 and 3 both contain the factor $(t - 1)$.

---

### Step 2: Analysis of the Singular Case ($t = 1$)

If $t = 1$, the factor $t - 1$ vanishes, making division by $t - 1$ invalid.

Substituting $t = 1$ into the reduced matrix:
$$
\left(\begin{array}{ccc|c}
1 & 1 & 1 & 1 \\
0 & 0 & 0 & 1 \\
0 & 0 & 0 & 2
\end{array}\right)
$$

- Row 2 yields the algebraic equation:
  $$
  0 \cdot x + 0 \cdot y + 0 \cdot z = 1 \implies 0 = 1 \quad (\text{Contradiction})
  $$
- Row 3 yields:
  $$
  0 \cdot x + 0 \cdot y + 0 \cdot z = 2 \implies 0 = 2 \quad (\text{Contradiction})
  $$

Here:
$$
\operatorname{rank}(A) = 1, \qquad \operatorname{rank}[A \mid b] = 2
$$
Because $\operatorname{rank}(A) < \operatorname{rank}[A \mid b]$, the system is **inconsistent**.

**Conclusion for $t = 1$:** **No solution**.

---

### Step 3: Analysis of the Regular Case ($t \ne 1$)

If $t \ne 1$, then $t - 1 \ne 0$. The diagonal entries are non-zero pivots, so $\operatorname{rank}(A) = \operatorname{rank}[A \mid b] = 3$.

We solve by back-substitution:

1. **Solve for $z$ from Row 3:**
   $$
   (t - 1)z = 2 \implies z = \frac{2}{t - 1}
   $$

2. **Solve for $y$ from Row 2:**
   $$
   (t - 1)y = 1 \implies y = \frac{1}{t - 1}
   $$

3. **Solve for $x$ from Row 1:**
   $$
   x + y + z = 1 \implies x = 1 - y - z
   $$
   Substitute $y$ and $z$:
   $$
   x = 1 - \frac{1}{t - 1} - \frac{2}{t - 1} = 1 - \frac{3}{t - 1} = \frac{(t - 1) - 3}{t - 1} = \frac{t - 4}{t - 1}
   $$

**Conclusion for $t \ne 1$:** **Exactly one unique solution**:
$$
\begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} \frac{t - 4}{t - 1} \\ \frac{1}{t - 1} \\ \frac{2}{t - 1} \end{pmatrix}
$$

---

### Step 4: Summary of Case Classification

| Parameter Range | Number of Solutions | Explicit Solution Form |
| :--- | :--- | :--- |
| **$t \ne 1$** | **Exactly one (unique)** | $(x, y, z) = \left(\frac{t-4}{t-1}, \frac{1}{t-1}, \frac{2}{t-1}\right)$ |
| **$t = 1$** | **No solution (inconsistent)** | $\emptyset$ |
| **Any $t$** | **Infinitely many solutions** | **Never occurs** (contradictions arise when rank drops) |

---

## 4. Verification and Consistency Checks

1. **Determinant Verification:**
   Compute $\det(A)$ from the triangularized matrix:
   $$
   \det(A) = 1 \cdot (t - 1) \cdot (t - 1) = (t - 1)^2
   $$
   - $\det(A) = 0 \iff t = 1$, confirming that $t = 1$ is the sole singular value.
   - For all $t \ne 1$, $\det(A) \ne 0$, confirming that a unique solution must exist.

2. **Substitute the Unique Solution for a Test Value (e.g., $t = 2$):**
   When $t = 2$:
   $$
   x = \frac{2 - 4}{2 - 1} = -2, \quad y = \frac{1}{2 - 1} = 1, \quad z = \frac{2}{2 - 1} = 2
   $$
   Check in original equations with $t = 2$:
   - Equation 1: $x + y + z = (-2) + 1 + 2 = 1$ ($\checkmark$)
   - Equation 2: $x + 2y + z = (-2) + 2(1) + 2 = 2$ ($\checkmark$)
   - Equation 3: $x + y + 2z = (-2) + 1 + 2(2) = 3$ ($\checkmark$)

3. **Substitute the Unique Solution for another Test Value (e.g., $t = 4$):**
   When $t = 4$:
   $$
   x = \frac{4 - 4}{4 - 1} = 0, \quad y = \frac{1}{3}, \quad z = \frac{2}{3}
   $$
   Check:
   - Equation 1: $0 + \frac{1}{3} + \frac{2}{3} = 1$ ($\checkmark$)
   - Equation 2: $0 + 4\left(\frac{1}{3}\right) + \frac{2}{3} = \frac{6}{3} = 2$ ($\checkmark$)
   - Equation 3: $0 + \frac{1}{3} + 4\left(\frac{2}{3}\right) = \frac{9}{3} = 3$ ($\checkmark$)
