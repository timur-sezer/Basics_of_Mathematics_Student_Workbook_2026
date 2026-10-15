# Solution to Exercise 2: Gaussian Elimination — One Solution

## 1. Problem Statement

Solve the following system of linear equations using Gaussian elimination:
$$
\begin{cases}
x + y + z = 6, \\
2x - y + z = 3, \\
x + 2y - z = 2.
\end{cases}
$$

After obtaining the solution, substitute the result into all three original equations to verify consistency.

---

## 2. Theoretical Background and Concepts

1. **Gaussian Elimination:**
   Gaussian elimination is an algorithm that converts a linear system's augmented matrix $[A \mid b]$ into an upper-triangular (row echelon) form through elementary row operations:
   - Row interchange ($R_i \leftrightarrow R_j$),
   - Row scaling ($R_i \leftarrow c R_i$, $c \ne 0$),
   - Row replacement ($R_i \leftarrow R_i + c R_j$).

2. **Back-Substitution:**
   Once the augmented matrix is in row echelon form with non-zero pivots on the diagonal, the value of the last variable is solved directly from the bottom row and substituted sequentially upwards to determine all remaining variables.

3. **Unique Solution Condition:**
   An $n \times n$ system has a unique solution if and only if the coefficient matrix has full rank ($n$ non-zero pivots, $\det A \ne 0$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up the Augmented Matrix

$$
[A \mid b] = \left(\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
2 & -1 & 1 & 3 \\
1 & 2 & -1 & 2
\end{array}\right)
$$

---

### Step 2: Forward Elimination (Column 1)

Pivot entry in position $(1, 1)$ is $1$.

1. Eliminate entry $(2, 1)$ via $R_2 \leftarrow R_2 - 2R_1$:
   $$
   \begin{pmatrix} 2 & -1 & 1 & 3 \end{pmatrix} - 2\begin{pmatrix} 1 & 1 & 1 & 6 \end{pmatrix} = \begin{pmatrix} 0 & -3 & -1 & -9 \end{pmatrix}
   $$

2. Eliminate entry $(3, 1)$ via $R_3 \leftarrow R_3 - R_1$:
   $$
   \begin{pmatrix} 1 & 2 & -1 & 2 \end{pmatrix} - \begin{pmatrix} 1 & 1 & 1 & 6 \end{pmatrix} = \begin{pmatrix} 0 & 1 & -2 & -4 \end{pmatrix}
   $$

The augmented matrix becomes:
$$
\left(\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & -3 & -1 & -9 \\
0 & 1 & -2 & -4
\end{array}\right)
$$

---

### Step 3: Forward Elimination (Column 2)

Interchange Row 2 and Row 3 to obtain a simpler pivot of $1$ ($R_2 \leftrightarrow R_3$):
$$
\left(\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & 1 & -2 & -4 \\
0 & -3 & -1 & -9
\end{array}\right)
$$

Eliminate entry $(3, 2)$ via $R_3 \leftarrow R_3 + 3R_2$:
$$
\begin{pmatrix} 0 & -3 & -1 & -9 \end{pmatrix} + 3\begin{pmatrix} 0 & 1 & -2 & -4 \end{pmatrix} = \begin{pmatrix} 0 & 0 & -7 & -21 \end{pmatrix}
$$

The augmented matrix is now in row echelon form:
$$
\left(\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & 1 & -2 & -4 \\
0 & 0 & -7 & -21
\end{array}\right)
$$

---

### Step 4: Back-Substitution

Translate the row echelon matrix back into scalar equations:

1. **From Row 3:**
   $$
   -7z = -21 \implies z = \frac{-21}{-7} = 3
   $$

2. **From Row 2:**
   $$
   y - 2z = -4 \implies y - 2(3) = -4 \implies y - 6 = -4 \implies y = 2
   $$

3. **From Row 1:**
   $$
   x + y + z = 6 \implies x + 2 + 3 = 6 \implies x + 5 = 6 \implies x = 1
   $$

Thus, the unique solution is:
$$
x = 1, \qquad y = 2, \qquad z = 3
$$
or in vector form:
$$
\begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}
$$

---

## 4. Verification and Consistency Checks

Substitute $(x, y, z) = (1, 2, 3)$ into each of the original equations:

1. **Equation 1 Check:**
   $$
   x + y + z = 1 + 2 + 3 = 6 \quad \checkmark
   $$
2. **Equation 2 Check:**
   $$
   2x - y + z = 2(1) - 2 + 3 = 2 - 2 + 3 = 3 \quad \checkmark
   $$
3. **Equation 3 Check:**
   $$
   x + 2y - z = 1 + 2(2) - 3 = 1 + 4 - 3 = 2 \quad \checkmark
   $$

All three equations are satisfied simultaneously, proving that $(1, 2, 3)$ is the exact, consistent solution.
