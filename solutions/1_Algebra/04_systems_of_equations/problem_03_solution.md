# Solution to Exercise 3: Inconsistent System

## 1. Problem Statement

Given the system of linear equations:
$$
\begin{cases}
x + 2y = 3, \\
2x + 4y = 7.
\end{cases}
$$

1. Solve the system or demonstrate that it is inconsistent (has no solution).
2. Show explicitly how the contradiction appears in the augmented matrix after Gaussian elimination.
3. Interpret the contradiction both algebraically in terms of the original equations and geometrically in terms of lines in the plane.

---

## 2. Theoretical Background and Concepts

1. **Inconsistency in Linear Systems:**
   A system of linear equations is **inconsistent** if it possesses no solution. By the Rouché–Capelli theorem, a system $Ax = b$ is consistent if and only if the rank of the coefficient matrix equals the rank of the augmented matrix:
   $$
   \operatorname{rank}(A) = \operatorname{rank}[A \mid b]
   $$
   If $\operatorname{rank}[A \mid b] > \operatorname{rank}(A)$, the system is inconsistent.

2. **The Contradiction Row:**
   In row echelon form, an inconsistency manifests as a row of the form:
   $$
   \left(\begin{array}{cccc|c} 0 & 0 & \cdots & 0 & c \end{array}\right), \qquad \text{with } c \ne 0
   $$
   This row represents the impossible equation $0 x_1 + 0 x_2 + \cdots + 0 x_n = c \implies 0 = c$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up the Augmented Matrix

Write the system as an augmented matrix $[A \mid b]$:
$$
[A \mid b] = \left(\begin{array}{cc|c}
1 & 2 & 3 \\
2 & 4 & 7
\end{array}\right)
$$

---

### Step 2: Apply Gaussian Elimination

Pivot entry is in position $(1, 1)$, with value $1$.
To eliminate the entry $2$ in Row 2, perform the operation:
$$
R_2 \leftarrow R_2 - 2R_1
$$

Computing the new second row:
- Left block: $\begin{pmatrix} 2 & 4 \end{pmatrix} - 2\begin{pmatrix} 1 & 2 \end{pmatrix} = \begin{pmatrix} 2 - 2 & 4 - 4 \end{pmatrix} = \begin{pmatrix} 0 & 0 \end{pmatrix}$
- Right block: $7 - 2(3) = 7 - 6 = 1$

The augmented matrix in row echelon form is:
$$
\left(\begin{array}{cc|c}
1 & 2 & 3 \\
0 & 0 & 1
\end{array}\right)
$$

---

### Step 3: Identify the Contradiction in the Matrix

Looking at Row 2 of the reduced augmented matrix:
$$
\left(\begin{array}{cc|c} 0 & 0 & 1 \end{array}\right)
$$
Converting this back to equation form:
$$
0 \cdot x + 0 \cdot y = 1 \implies 0 = 1
$$
Because $0 = 1$ is universally false for all values of $(x, y) \in \mathbb{R}^2$, the system contains a logical contradiction.
Therefore, the system has **no solution** (it is **inconsistent**).

---

### Step 4: Interpretation in Terms of Equations and Geometry

1. **Algebraic Interpretation:**
   - Equation 1 is $x + 2y = 3$. If we multiply the entire equation by $2$, we obtain:
     $$
     2x + 4y = 6
     $$
   - Equation 2 states:
     $$
     2x + 4y = 7
     $$
   - For both equations to hold, the linear combination $2x + 4y$ would have to equal $6$ and $7$ at the exact same time. Since $6 \ne 7$, no pair of numbers $(x, y)$ can ever satisfy both conditions.

2. **Geometric Interpretation (Parallel Lines):**
   Solving each equation for $y$ in slope-intercept form $y = mx + b$:
   - Line 1 ($L_1$): $2y = -x + 3 \implies y = -\frac{1}{2}x + \frac{3}{2}$
   - Line 2 ($L_2$): $4y = -2x + 7 \implies y = -\frac{1}{2}x + \frac{7}{4}$

   Both lines share the exact same slope $m = -\frac{1}{2}$, but have different $y$-intercepts ($\frac{3}{2} = 1.5$ versus $\frac{7}{4} = 1.75$).
   In the Cartesian plane, two lines with equal slopes and distinct intercepts are **strictly parallel and non-intersecting**. The absence of any intersection point corresponds to the lack of algebraic solutions.

---

## 4. Verification and Consistency Checks

1. **Rank Comparison:**
   - Coefficient matrix $A = \begin{pmatrix} 1 & 2 \\ 2 & 4 \end{pmatrix} \xrightarrow{R_2 - 2R_1} \begin{pmatrix} 1 & 2 \\ 0 & 0 \end{pmatrix} \implies \operatorname{rank}(A) = 1$.
   - Augmented matrix $[A \mid b] \xrightarrow{R_2 - 2R_1} \begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & 1 \end{pmatrix} \implies \operatorname{rank}[A \mid b] = 2$.
   - Since $\operatorname{rank}(A) = 1 < 2 = \operatorname{rank}[A \mid b]$, the Rouché–Capelli theorem formally confirms that the system is inconsistent.

2. **Determinant Check:**
   $\det A = (1)(4) - (2)(2) = 4 - 4 = 0$, confirming that $A$ is singular and cannot have a unique solution.
