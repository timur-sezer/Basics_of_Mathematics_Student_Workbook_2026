# Solution to Exercise 5: Row Echelon Form and Number of Solutions

## 1. Problem Statement

Given the augmented matrix in row echelon form:
$$
\left[\begin{array}{ccc|c}
1 & 2 & -1 & 3 \\
0 & 1 & 2 & 1 \\
0 & 0 & 0 & 0
\end{array}\right]
$$

1. Determine the number of solutions to the linear system.
2. Explain how to determine the exact number of variables that may be chosen freely.
3. Express the complete solution set in parametric vector form.

---

## 2. Theoretical Background and Concepts

1. **Row Echelon Form and Pivot Columns:**
   In an augmented matrix $[A \mid b]$ in row echelon form:
   - A **pivot** is the first non-zero entry in a non-zero row.
   - The columns containing pivots correspond to **basic (leading) variables**.
   - The columns without pivots correspond to **free variables** (parameters).

2. **Classification of the Number of Solutions:**
   - **No solution:** Occurs if the rightmost augmented column contains a pivot (a row of the form $[0 \cdots 0 \mid c]$ with $c \ne 0$).
   - **Exactly one solution:** Occurs if the system is consistent and every column of $A$ contains a pivot (no free variables, $\operatorname{rank}(A) = n$).
   - **Infinitely many solutions:** Occurs if the system is consistent and there is at least one free variable ($\operatorname{rank}(A) < n$).

3. **Dimension of the Solution Space (Degrees of Freedom):**
   By the Rank-Nullity Theorem, for a consistent system with $n$ unknowns and rank $r = \operatorname{rank}(A)$:
   $$
   \text{Number of Free Variables} = n - r = n - \text{number of pivots}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify Pivots and Consistency

Examine the augmented matrix:
$$
\left[\begin{array}{ccc|c}
\mathbf{1} & 2 & -1 & 3 \\
0 & \mathbf{1} & 2 & 1 \\
0 & 0 & 0 & 0
\end{array}\right]
$$

1. **Pivots in $A$:**
   - Row 1 has a pivot in **Column 1** (value $1$).
   - Row 2 has a pivot in **Column 2** (value $1$).
   - Row 3 contains no pivot (all entries are zero).
   Thus, $\operatorname{rank}(A) = 2$.

2. **Augmented Column Check (Consistency):**
   - The third row reads $0 x_1 + 0 x_2 + 0 x_3 = 0$, which is $0 = 0$ (a true identity, not a contradiction).
   - The augmented column contains no pivot, so $\operatorname{rank}[A \mid b] = 2 = \operatorname{rank}(A)$.
   - The system is **consistent**.

---

### Step 2: Determine Free Variables and the Number of Solutions

1. **Number of Unknowns:** $n = 3$ (variables $x_1, x_2, x_3$).
2. **Number of Pivots (Rank):** $r = 2$.
3. **Number of Free Variables:**
   $$
   \text{Free Variables} = n - r = 3 - 2 = 1
   $$
   - Columns 1 and 2 contain pivots $\implies x_1$ and $x_2$ are basic variables.
   - Column 3 contains no pivot $\implies x_3$ is the single **free variable**.

Because the system is consistent and has $1$ free variable, which can take any real value $t \in \mathbb{R}$, there are **infinitely many solutions**.

---

### Step 3: Find the Parametric Form

Let the free variable be parameterized by $x_3 = t$, where $t \in \mathbb{R}$.

1. **Solve for $x_2$ from Row 2:**
   $$
   x_2 + 2x_3 = 1 \implies x_2 + 2t = 1 \implies x_2 = 1 - 2t
   $$

2. **Solve for $x_1$ from Row 1:**
   $$
   x_1 + 2x_2 - x_3 = 3
   $$
   Substitute $x_2 = 1 - 2t$ and $x_3 = t$:
   $$
   x_1 + 2(1 - 2t) - t = 3 \implies x_1 + 2 - 4t - t = 3 \implies x_1 + 2 - 5t = 3 \implies x_1 = 1 + 5t
   $$

3. **Parametric Vector Form:**
   Assemble the solution into a vector:
   $$
   \begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix} = \begin{pmatrix} 1 + 5t \\ 1 - 2t \\ t \end{pmatrix} = \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix} + t \begin{pmatrix} 5 \\ -2 \\ 1 \end{pmatrix}, \qquad t \in \mathbb{R}
   $$

This represents a line in $\mathbb{R}^3$ passing through $(1, 1, 0)$ with direction vector $(5, -2, 1)$.

---

## 4. Verification and Consistency Checks

1. **Test with $t = 0$ (Particular Solution):**
   At $t = 0$: $x = \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}$.
   - Row 1: $1(1) + 2(1) - 1(0) = 1 + 2 - 0 = 3 \quad \checkmark$
   - Row 2: $0(1) + 1(1) + 2(0) = 1 \quad \checkmark$
   - Row 3: $0 = 0 \quad \checkmark$

2. **Test with $t = 1$:**
   At $t = 1$: $x = \begin{pmatrix} 6 \\ -1 \\ 1 \end{pmatrix}$.
   - Row 1: $1(6) + 2(-1) - 1(1) = 6 - 2 - 1 = 3 \quad \checkmark$
   - Row 2: $0(6) + 1(-1) + 2(1) = -1 + 2 = 1 \quad \checkmark$
   - Row 3: $0 = 0 \quad \checkmark$

3. **Homogeneous Kernel Check:**
   Multiply the coefficient matrix $A$ by the direction vector $v = \begin{pmatrix} 5 \\ -2 \\ 1 \end{pmatrix}$:
   $$
   A v = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & 2 \\ 0 & 0 & 0 \end{pmatrix} \begin{pmatrix} 5 \\ -2 \\ 1 \end{pmatrix} = \begin{pmatrix} 1(5) + 2(-2) - 1(1) \\ 0(5) + 1(-2) + 2(1) \\ 0 \end{pmatrix} = \begin{pmatrix} 5 - 4 - 1 \\ -2 + 2 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix} \quad \checkmark
   $$
   Vector $v$ is in the nullspace of $A$, validating the parametric direction.
