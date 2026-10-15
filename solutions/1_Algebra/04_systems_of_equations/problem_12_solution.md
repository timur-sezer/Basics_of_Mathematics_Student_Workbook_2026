# Solution to Exercise 12: Homogeneous System

## 1. Problem Statement

Solve the homogeneous linear system:
$$
\begin{cases}
x + 2y - z = 0, \\
2x + 4y - 2z = 0, \\
x - y + 2z = 0.
\end{cases}
$$

1. Determine all solutions and express them in parametric vector form.
2. Identify the pivot variables and the free variable(s).
3. Explain why the trivial solution $(0, 0, 0)$ is guaranteed to satisfy every homogeneous system.

---

## 2. Theoretical Background and Concepts

1. **Homogeneous Systems ($Ax = \mathbf{0}$):**
   A linear system is called homogeneous if all constant terms on the right-hand side are zero.
   - Every homogeneous system is **consistent** because the zero vector $\mathbf{x} = \mathbf{0} = (0, 0, \dots, 0)^T$ always satisfies $A\mathbf{0} = \mathbf{0}$. This is known as the **trivial solution**.
   - By the Rank-Nullity Theorem, if $\operatorname{rank}(A) = n$ (number of unknowns), the trivial solution is the *only* solution. If $\operatorname{rank}(A) = r < n$, there exist $n - r$ free variables, giving rise to infinitely many non-trivial solutions forming a subspace (the null space or kernel of $A$).

2. **Invariant Zero Vector Under Elementary Row Operations:**
   In an augmented matrix $[A \mid \mathbf{0}]$, any elementary row operation on the zero right-hand column leaves it identically zero ($c \cdot 0 + d \cdot 0 = 0$). Thus, row operations need only be tracked on the coefficient matrix $A$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Augmented Matrix Setup

Set up the augmented matrix $[A \mid \mathbf{0}]$:
$$
[A \mid \mathbf{0}] = \left(\begin{array}{ccc|c}
1 & 2 & -1 & 0 \\
2 & 4 & -2 & 0 \\
1 & -1 & 2 & 0
\end{array}\right)
$$

---

### Step 2: Gaussian Elimination to Row Echelon Form

1. **Eliminate column 1 below the pivot in Row 1:**
   - $R_2 \leftarrow R_2 - 2R_1$:
     $$
     \begin{pmatrix} 2 & 4 & -2 \end{pmatrix} - 2\begin{pmatrix} 1 & 2 & -1 \end{pmatrix} = \begin{pmatrix} 0 & 0 & 0 \end{pmatrix}
     $$
   - $R_3 \leftarrow R_3 - R_1$:
     $$
     \begin{pmatrix} 1 & -1 & 2 \end{pmatrix} - \begin{pmatrix} 1 & 2 & -1 \end{pmatrix} = \begin{pmatrix} 0 & -3 & 3 \end{pmatrix}
     $$

   The matrix becomes:
   $$
   \left(\begin{array}{ccc|c}
   1 & 2 & -1 & 0 \\
   0 & 0 & 0 & 0 \\
   0 & -3 & 3 & 0
   \end{array}\right)
   $$

2. **Interchange rows to move the zero row to the bottom ($R_2 \leftrightarrow R_3$):**
   $$
   \left(\begin{array}{ccc|c}
   1 & 2 & -1 & 0 \\
   0 & -3 & 3 & 0 \\
   0 & 0 & 0 & 0
   \end{array}\right)
   $$

3. **Scale Row 2 ($R_2 \leftarrow -\frac{1}{3}R_2$):**
   $$
   \left(\begin{array}{ccc|c}
   1 & 2 & -1 & 0 \\
   0 & 1 & -1 & 0 \\
   0 & 0 & 0 & 0
   \end{array}\right)
   $$

---

### Step 3: Reduced Row Echelon Form (RREF)

Eliminate above the pivot in column 2 ($R_1 \leftarrow R_1 - 2R_2$):
$$
\begin{pmatrix} 1 & 2 & -1 \end{pmatrix} - 2\begin{pmatrix} 0 & 1 & -1 \end{pmatrix} = \begin{pmatrix} 1 & 0 & 1 \end{pmatrix}
$$

The matrix in RREF is:
$$
\left(\begin{array}{ccc|c}
1 & 0 & 1 & 0 \\
0 & 1 & -1 & 0 \\
0 & 0 & 0 & 0
\end{array}\right)
$$

---

### Step 4: Variable Classification and Parametric Solution

- **Pivot Columns:** Columns 1 and 2 correspond to pivot variables $x$ and $y$.
- **Free Column:** Column 3 has no pivot, so $z$ is a **free variable**.
- We have $\operatorname{rank}(A) = 2$ and $n = 3$, giving $n - \operatorname{rank}(A) = 3 - 2 = 1$ degree of freedom.

Let the free variable be parameterized by $t \in \mathbb{R}$:
$$
z = t
$$

From the RREF equations:
- Row 2: $y - z = 0 \implies y = z = t$
- Row 1: $x + z = 0 \implies x = -z = -t$

Writing in vector parametric form:
$$
\begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} -t \\ t \\ t \end{pmatrix} = t \begin{pmatrix} -1 \\ 1 \\ 1 \end{pmatrix}, \quad t \in \mathbb{R}
$$

The solution set is a 1-dimensional line in $\mathbb{R}^3$ passing through the origin along the direction vector $\mathbf{v} = (-1, 1, 1)^T$.

---

### Step 5: Why $(0, 0, 0)$ Always Satisfies a Homogeneous System

1. **Algebraic Proof via Matrix Multiplication:**
   Any homogeneous system of $m$ linear equations in $n$ variables has the form:
   $$
   A\mathbf{x} = \mathbf{0}
   $$
   For the zero vector $\mathbf{x} = \mathbf{0} = (0, 0, \dots, 0)^T$, the $i$-th equation evaluates to:
   $$
   (A\mathbf{0})_i = \sum_{j=1}^n a_{ij} \cdot 0 = a_{i1}(0) + a_{i2}(0) + \dots + a_{in}(0) = 0
   $$
   Because multiplying any real number by zero produces zero, and the sum of zeros is identically zero, $(A\mathbf{0})_i = 0$ holds identically for every row $i \in \{1, 2, \dots, m\}$.

2. **Geometric Interpretation:**
   In $\mathbb{R}^n$, an equation of the form $a_1 x_1 + \dots + a_n x_n = 0$ represents a hyperplane (or plane/line) passing directly through the coordinate origin. Since the constant term is zero, the origin $(0, 0, \dots, 0)$ lies on every single hyperplane defined by the system. Therefore, the origin must belong to their intersection.

3. **Consistency with the Parametric Solution:**
   Setting the parameter $t = 0$ in our parametric solution yields:
   $$
   \mathbf{x} = 0 \cdot \begin{pmatrix} -1 \\ 1 \\ 1 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}
   $$
   confirming that the trivial solution is an element of the solution set.

---

## 4. Verification and Consistency Checks

1. **Test with $t = 1 \implies (x, y, z) = (-1, 1, 1)$:**
   - Equation 1: $(-1) + 2(1) - 1 = -1 + 2 - 1 = 0$ ($\checkmark$)
   - Equation 2: $2(-1) + 4(1) - 2(1) = -2 + 4 - 2 = 0$ ($\checkmark$)
   - Equation 3: $(-1) - (1) + 2(1) = -1 - 1 + 2 = 0$ ($\checkmark$)

2. **Test with $t = -3 \implies (x, y, z) = (3, -3, -3)$:**
   - Equation 1: $3 + 2(-3) - (-3) = 3 - 6 + 3 = 0$ ($\checkmark$)
   - Equation 2: $2(3) + 4(-3) - 2(-3) = 6 - 12 + 6 = 0$ ($\checkmark$)
   - Equation 3: $3 - (-3) + 2(-3) = 3 + 3 - 6 = 0$ ($\checkmark$)

3. **Determinant Check:**
   $$
   \det(A) = 1(4\cdot 2 - (-2)(-1)) - 2(2\cdot 2 - (-2)(1)) + (-1)(2(-1) - 4\cdot 1)
   $$
   $$
   = 1(8 - 2) - 2(4 + 2) - 1(-2 - 4) = 6 - 12 + 6 = 0
   $$
   Since $\det(A) = 0$, the existence of non-trivial solutions is confirmed.
