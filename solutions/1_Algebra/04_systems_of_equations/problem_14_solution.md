# Solution to Exercise 14: A Small Change in the Right-Hand Side

## 1. Problem Statement

Compare the two linear systems of three equations in two variables:
$$
\text{System A: } \begin{cases} x + y = 2, \\ 2x - y = 1, \\ 3x = 3. \end{cases} \qquad \text{System B: } \begin{cases} x + y = 2, \\ 2x - y = 1, \\ 3x = 3.1. \end{cases}
$$

1. Perform Gaussian elimination to test the consistency of each system.
2. Provide the complete solution set for both systems.
3. Explain geometrically and algebraically why a tiny perturbation in a single number (from $3$ to $3.1$) fundamentally alters the classification of the system from having a unique solution to having no solution.

---

## 2. Theoretical Background and Concepts

1. **Overdetermined Systems ($m > n$):**
   A system with more equations than variables ($m = 3$ equations, $n = 2$ variables) is overdetermined.
   - Geometrically in $\mathbb{R}^2$, each equation represents a line. A solution exists if and only if all $m$ lines are **concurrent** (intersect at a common point).
   - In matrix terms, $Ax = b$ is consistent if and only if the RHS vector $b \in \mathbb{R}^m$ lies strictly within the column space $\operatorname{col}(A) \subseteq \mathbb{R}^m$.

2. **Subspace Dimensionality and Sensitivity:**
   The column space $\operatorname{col}(A)$ is at most $n$-dimensional (here, a $2$-dimensional plane inside $\mathbb{R}^3$). A $2\text{D}$ subspace has zero volume in $\mathbb{R}^3$. While $b_A$ happens to lie precisely in this plane, an arbitrary perturbation $\Delta b$ almost surely points out of the plane, immediately rendering the system inconsistent.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Elimination and Consistency Analysis of System A

Write the augmented matrix $[A \mid b_A]$:
$$
[A \mid b_A] = \left(\begin{array}{cc|c}
1 & 1 & 2 \\
2 & -1 & 1 \\
3 & 0 & 3
\end{array}\right)
$$

1. **Eliminate column 1 below Row 1:**
   - $R_2 \leftarrow R_2 - 2R_1$:
     $$
     \begin{pmatrix} 2 & -1 \end{pmatrix} - 2\begin{pmatrix} 1 & 1 \end{pmatrix} = \begin{pmatrix} 0 & -3 \end{pmatrix}, \quad 1 - 2(2) = -3
     $$
   - $R_3 \leftarrow R_3 - 3R_1$:
     $$
     \begin{pmatrix} 3 & 0 \end{pmatrix} - 3\begin{pmatrix} 1 & 1 \end{pmatrix} = \begin{pmatrix} 0 & -3 \end{pmatrix}, \quad 3 - 3(2) = -3
     $$
   The matrix becomes:
   $$
   \left(\begin{array}{cc|c}
   1 & 1 & 2 \\
   0 & -3 & -3 \\
   0 & -3 & -3
   \end{array}\right)
   $$

2. **Eliminate column 2 in Row 3 ($R_3 \leftarrow R_3 - R_2$):**
   $$
   \left(\begin{array}{cc|c}
   1 & 1 & 2 \\
   0 & -3 & -3 \\
   0 & 0 & 0
   \end{array}\right)
   $$

3. **Solve by back-substitution:**
   - Row 2: $-3y = -3 \implies y = 1$
   - Row 1: $x + 1 = 2 \implies x = 1$

Here, $\operatorname{rank}(A) = \operatorname{rank}[A \mid b_A] = 2 = n$.
**System A is consistent with exactly one unique solution:**
$$
\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 1 \\ 1 \end{pmatrix}
$$

---

### Step 2: Elimination and Consistency Analysis of System B

Write the augmented matrix $[A \mid b_B]$:
$$
[A \mid b_B] = \left(\begin{array}{cc|c}
1 & 1 & 2 \\
2 & -1 & 1 \\
3 & 0 & 3.1
\end{array}\right)
$$

1. **Eliminate column 1 below Row 1:**
   - $R_2 \leftarrow R_2 - 2R_1$:
     $$
     \begin{pmatrix} 0 & -3 \end{pmatrix}, \quad 1 - 2(2) = -3
     $$
   - $R_3 \leftarrow R_3 - 3R_1$:
     $$
     \begin{pmatrix} 0 & -3 \end{pmatrix}, \quad 3.1 - 3(2) = 3.1 - 6 = -2.9
     $$
   The matrix becomes:
   $$
   \left(\begin{array}{cc|c}
   1 & 1 & 2 \\
   0 & -3 & -3 \\
   0 & -3 & -2.9
   \end{array}\right)
   $$

2. **Eliminate column 2 in Row 3 ($R_3 \leftarrow R_3 - R_2$):**
   - Left side: $\begin{pmatrix} 0 & -3 \end{pmatrix} - \begin{pmatrix} 0 & -3 \end{pmatrix} = \begin{pmatrix} 0 & 0 \end{pmatrix}$
   - Right side: $-2.9 - (-3) = -2.9 + 3.0 = 0.1$

   The matrix in row echelon form is:
   $$
   \left(\begin{array}{cc|c}
   1 & 1 & 2 \\
   0 & -3 & -3 \\
   0 & 0 & 0.1
   \end{array}\right)
   $$

3. **Evaluate Row 3:**
   Row 3 corresponds to the statement:
   $$
   0 \cdot x + 0 \cdot y = 0.1 \implies 0 = 0.1 \quad (\text{Contradiction!})
   $$
   We have:
   $$
   \operatorname{rank}(A) = 2, \qquad \operatorname{rank}[A \mid b_B] = 3
   $$
   Because $\operatorname{rank}(A) < \operatorname{rank}[A \mid b_B]$, **System B is inconsistent (no solution)**.

---

### Step 3: Why a Small Change Alters the System Type

1. **Geometric Interpretation (Concurrency of Lines):**
   - In System A, the first two lines intersect at $(1, 1)$:
     - Line 1: $y = 2 - x$
     - Line 2: $y = 2x - 1$
     - Intersection: $2 - x = 2x - 1 \implies 3x = 3 \implies x = 1, y = 1$.
   - The third equation in System A defines the vertical line $x = 1$. This vertical line passes **directly through the intersection point $(1, 1)$**. All three lines meet at that single common point (they are concurrent).
   - In System B, the third equation defines the vertical line $x = \frac{3.1}{3} \approx 1.0333$.
   - This vertical line is shifted to the right by $\Delta x = \frac{0.1}{3} \approx 0.0333$.
   - Although the shift is tiny, the line $x \approx 1.0333$ no longer passes through $(1, 1)$. The three lines now intersect pairwise in three separate points, forming a tiny triangle. There is no longer any single point common to all three lines simultaneously.

2. **Algebraic Interpretation (Column Space):**
   - The coefficient matrix $A$ has columns $a_1 = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}$ and $a_2 = \begin{pmatrix} 1 \\ -1 \\ 0 \end{pmatrix}$.
   - The column space $\operatorname{col}(A) = \operatorname{span}(a_1, a_2)$ is a $2$-dimensional plane embedded in $\mathbb{R}^3$.
   - For System A:
     $$
     b_A = \begin{pmatrix} 2 \\ 1 \\ 3 \end{pmatrix} = 1 \cdot \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix} + 1 \cdot \begin{pmatrix} 1 \\ -1 \\ 0 \end{pmatrix} \in \operatorname{col}(A)
     $$
     Because $b_A \in \operatorname{col}(A)$, exact consistency holds.
   - For System B:
     $$
     b_B = \begin{pmatrix} 2 \\ 1 \\ 3.1 \end{pmatrix} = b_A + \begin{pmatrix} 0 \\ 0 \\ 0.1 \end{pmatrix}
     $$
     The perturbation vector $\Delta b = \begin{pmatrix} 0 \\ 0 \\ 0.1 \end{pmatrix}$ has a component orthogonal to the plane $\operatorname{col}(A)$. Therefore, $b_B \notin \operatorname{col}(A)$.
   - Consistency requires the right-hand side to lie *exactly* on the subspace. Any deviation, no matter how small, knocks the vector out of the subspace and destroys consistency completely.

---

## 4. Verification and Consistency Checks

1. **System A Verification:**
   - Equation 1: $1 + 1 = 2$ ($\checkmark$)
   - Equation 2: $2(1) - 1 = 1$ ($\checkmark$)
   - Equation 3: $3(1) = 3$ ($\checkmark$)

2. **System B Contradiction Check:**
   - Using Equations 1 and 2: $x = 1, y = 1$.
   - Testing in Equation 3: $3(1) = 3 \ne 3.1$. Residual error is:
     $$
     |3x - 3.1| = |3(1) - 3.1| = 0.1 \ne 0
     $$
     Confirming the absence of any solution.

3. **Comparative Overview:**

| Property | System A | System B |
| :--- | :--- | :--- |
| **Augmented Matrix Echelon Form** | $\left(\begin{array}{cc\|c} 1 & 1 & 2 \\ 0 & -3 & -3 \\ 0 & 0 & 0 \end{array}\right)$ | $\left(\begin{array}{cc\|c} 1 & 1 & 2 \\ 0 & -3 & -3 \\ 0 & 0 & 0.1 \end{array}\right)$ |
| **$\operatorname{rank}(A)$ vs $\operatorname{rank}[A \mid b]$** | $\operatorname{rank}(A) = \operatorname{rank}[A \mid b] = 2$ | $\operatorname{rank}(A) = 2 < \operatorname{rank}[A \mid b] = 3$ |
| **Geometric Configuration** | 3 concurrent lines meeting at $(1, 1)$ | 3 non-concurrent lines forming a triangle |
| **Solution Set** | Exactly one: $\{(1, 1)\}$ | Empty set: $\emptyset$ (Inconsistent) |
