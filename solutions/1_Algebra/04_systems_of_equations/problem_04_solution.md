# Solution to Exercise 4: Infinitely Many Solutions

## 1. Problem Statement

Given the system of linear equations:
$$
\begin{cases}
x + y + z = 2, \\
2x + 2y + 2z = 4, \\
x - y + z = 0.
\end{cases}
$$

1. Solve the system and express the general solution in parametric vector form.
2. Clearly identify the pivot variables and the free variable.
3. Choose a specific parameter value, find the corresponding coordinate point, and verify that it satisfies all three original equations.

---

## 2. Theoretical Background and Concepts

1. **Underdetermined / Linearly Dependent Systems:**
   When a linear system has fewer independent equations than variables ($\operatorname{rank}(A) < n$) and is consistent ($\operatorname{rank}(A) = \operatorname{rank}[A \mid b]$), there is no contradiction, but there is not enough information to fix all variables uniquely. This results in **infinitely many solutions**.

2. **Basic (Pivot) vs. Free Variables:**
   - In row echelon form, columns containing leading non-zero entries (pivots) correspond to **basic (pivot) variables**.
   - Columns with no pivots correspond to **free variables** (parameters), which can assume any real value $t \in \mathbb{R}$.
   - The number of free variables is given by:
     $$
     \text{Degrees of Freedom} = n - \operatorname{rank}(A)
     $$

3. **Geometric Interpretation:**
   In three-dimensional space, each linear equation represents a plane.
   - The first two equations represent the exact same plane ($2x+2y+2z=4 \iff x+y+z=2$).
   - The third equation represents a second non-parallel plane.
   - Two distinct non-parallel planes intersect along a single straight line in $\mathbb{R}^3$, giving a 1-dimensional continuum of solutions.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up the Augmented Matrix

$$
[A \mid b] = \left(\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\
2 & 2 & 2 & 4 \\
1 & -1 & 1 & 0
\end{array}\right)
$$

---

### Step 2: Apply Gaussian Elimination

Pivot entry is in position $(1, 1)$, with value $1$.

1. Eliminate entry $(2, 1)$ via $R_2 \leftarrow R_2 - 2R_1$:
   $$
   \begin{pmatrix} 2 & 2 & 2 & 4 \end{pmatrix} - 2\begin{pmatrix} 1 & 1 & 1 & 2 \end{pmatrix} = \begin{pmatrix} 0 & 0 & 0 & 0 \end{pmatrix}
   $$

2. Eliminate entry $(3, 1)$ via $R_3 \leftarrow R_3 - R_1$:
   $$
   \begin{pmatrix} 1 & -1 & 1 & 0 \end{pmatrix} - \begin{pmatrix} 1 & 1 & 1 & 2 \end{pmatrix} = \begin{pmatrix} 0 & -2 & 0 & -2 \end{pmatrix}
   $$

The augmented matrix becomes:
$$
\left(\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\
0 & 0 & 0 & 0 \\
0 & -2 & 0 & -2
\end{array}\right)
$$

Swap Row 2 and Row 3 to push the zero row to the bottom ($R_2 \leftrightarrow R_3$):
$$
\left(\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\
0 & -2 & 0 & -2 \\
0 & 0 & 0 & 0
\end{array}\right)
$$

Scale Row 2 by $-\frac{1}{2}$ ($R_2 \leftarrow -\frac{1}{2} R_2$):
$$
\left(\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\
0 & 1 & 0 & 1 \\
0 & 0 & 0 & 0
\end{array}\right)
$$

---

### Step 3: Back-Substitution and Parametric Solution

1. **Identify Pivots and Free Variables:**
   - Column 1 has a pivot $\implies x$ is a **basic variable**.
   - Column 2 has a pivot $\implies y$ is a **basic variable**.
   - Column 3 has no pivot $\implies z$ is a **free variable**.

2. **Solve for Basic Variables:**
   - Let $z = t$, where $t \in \mathbb{R}$ is an arbitrary parameter.
   - From Row 2:
     $$
     1y + 0z = 1 \implies y = 1
     $$
   - From Row 1:
     $$
     x + y + z = 2 \implies x + 1 + t = 2 \implies x = 1 - t
     $$

3. **Parametric Vector Form:**
   $$
   \begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} 1 - t \\ 1 \\ t \end{pmatrix} = \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix} + t \begin{pmatrix} -1 \\ 0 \\ 1 \end{pmatrix}, \qquad t \in \mathbb{R}
   $$

---

### Step 4: Verification of a Chosen Parameter Value

Select the parameter value **$t = 2$**:
$$
x = 1 - 2 = -1, \qquad y = 1, \qquad z = 2
$$
The candidate point is $(-1, 1, 2)$.

Substitute $(-1, 1, 2)$ into each of the original equations:
1. **Equation 1:**
   $$
   x + y + z = -1 + 1 + 2 = 2 \quad \checkmark
   $$
2. **Equation 2:**
   $$
   2x + 2y + 2z = 2(-1) + 2(1) + 2(2) = -2 + 2 + 4 = 4 \quad \checkmark
   $$
3. **Equation 3:**
   $$
   x - y + z = -1 - 1 + 2 = 0 \quad \checkmark
   $$

All three equations are satisfied simultaneously, confirming the validity of the parametric solution.

---

## 4. Verification and Consistency Checks

1. **Test with $t = 0$:**
   At $t = 0$, $(x, y, z) = (1, 1, 0)$:
   - $1 + 1 + 0 = 2 \quad \checkmark$
   - $2(1) + 2(1) + 2(0) = 4 \quad \checkmark$
   - $1 - 1 + 0 = 0 \quad \checkmark$

2. **Direction Vector Orthogonality Check:**
   The direction vector $v = \begin{pmatrix} -1 \\ 0 \\ 1 \end{pmatrix}$ must be perpendicular to the normal vectors of all three equations:
   - $n_1 \cdot v = (1)(-1) + (1)(0) + (1)(1) = -1 + 1 = 0 \quad \checkmark$
   - $n_2 \cdot v = (2)(-1) + (2)(0) + (2)(1) = -2 + 2 = 0 \quad \checkmark$
   - $n_3 \cdot v = (1)(-1) + (-1)(0) + (1)(1) = -1 + 1 = 0 \quad \checkmark$
   The solution line lies entirely inside the intersection of all three planes.
