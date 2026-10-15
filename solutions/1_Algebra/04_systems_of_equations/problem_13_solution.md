# Solution to Exercise 13: Does Every Equation Add New Information?

## 1. Problem Statement

Consider the linear system:
$$
\begin{cases}
x_1 + x_2 = 10, \\
x_2 + x_3 = 8, \\
x_1 - x_3 = 2.
\end{cases}
$$

1. Solve the system completely using Gaussian elimination.
2. Determine whether all three equations are independently necessary to specify the solution set.
3. If one equation follows from the others (is redundant), demonstrate this algebraically through an explicit linear combination.
4. Express the complete solution set in parametric vector form.

---

## 2. Theoretical Background and Concepts

1. **Linear Dependence and Redundancy:**
   An equation in a linear system is said to be **redundant** if it can be expressed as a linear combination of the other equations:
   $$
   \operatorname{Eq}_k = \sum_{j \ne k} c_j \operatorname{Eq}_j
   $$
   When an equation is redundant, it adds no new geometrical constraints; the hyperplanes intersect along the same geometric object whether the redundant equation is included or omitted.

2. **Rank and Degrees of Freedom:**
   In Gaussian elimination, a redundant equation manifests as a row of zeros $\left(\begin{array}{ccc|c} 0 & 0 & 0 & 0 \end{array}\right)$ in the augmented matrix. If $n = 3$ and $\operatorname{rank}(A) = \operatorname{rank}[A \mid b] = 2$, there is $n - \operatorname{rank}(A) = 3 - 2 = 1$ free variable, describing a 1-dimensional line of solutions.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Algebraic Demonstration of Redundancy

Examine the first two equations:
- Equation 1: $x_1 + x_2 = 10$
- Equation 2: $x_2 + x_3 = 8$

Subtract Equation 2 from Equation 1:
$$
(x_1 + x_2) - (x_2 + x_3) = 10 - 8
$$
Simplify the left-hand side:
$$
x_1 + x_2 - x_2 - x_3 = x_1 - x_3
$$
Simplify the right-hand side:
$$
10 - 8 = 2
$$
This yields:
$$
x_1 - x_3 = 2
$$
which is **identically Equation 3**.

Therefore, Equation 3 is a direct linear consequence of Equations 1 and 2:
$$
\operatorname{Eq}_3 = 1 \cdot \operatorname{Eq}_1 - 1 \cdot \operatorname{Eq}_2
$$
Equation 3 provides **no new information**; it is entirely redundant.

---

### Step 2: Gaussian Elimination on the Augmented Matrix

Set up the augmented matrix $[A \mid b]$:
$$
[A \mid b] = \left(\begin{array}{ccc|c}
1 & 1 & 0 & 10 \\
0 & 1 & 1 & 8 \\
1 & 0 & -1 & 2
\end{array}\right)
$$

1. **Eliminate column 1 in Row 3 ($R_3 \leftarrow R_3 - R_1$):**
   - Left side: $\begin{pmatrix} 1 & 0 & -1 \end{pmatrix} - \begin{pmatrix} 1 & 1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & -1 & -1 \end{pmatrix}$
   - Right side: $2 - 10 = -8$
   $$
   \left(\begin{array}{ccc|c}
   1 & 1 & 0 & 10 \\
   0 & 1 & 1 & 8 \\
   0 & -1 & -1 & -8
   \end{array}\right)
   $$

2. **Eliminate column 2 in Row 3 ($R_3 \leftarrow R_3 + R_2$):**
   - Left side: $\begin{pmatrix} 0 & -1 & -1 \end{pmatrix} + \begin{pmatrix} 0 & 1 & 1 \end{pmatrix} = \begin{pmatrix} 0 & 0 & 0 \end{pmatrix}$
   - Right side: $-8 + 8 = 0$

   The matrix in row echelon form is:
   $$
   \left(\begin{array}{ccc|c}
   1 & 1 & 0 & 10 \\
   0 & 1 & 1 & 8 \\
   0 & 0 & 0 & 0
   \end{array}\right)
   $$

The third row reduces completely to $\left(\begin{array}{ccc|c} 0 & 0 & 0 & 0 \end{array}\right)$, confirming that the third equation adds no constraint and $\operatorname{rank}(A) = \operatorname{rank}[A \mid b] = 2$.

---

### Step 3: Back-Substitution and Parametric Solution

- **Pivot variables:** $x_1$ and $x_2$ (columns 1 and 2).
- **Free variable:** $x_3$ (column 3).

Set the parameter $x_3 = t$ for any $t \in \mathbb{R}$:
1. **From Row 2:**
   $$
   x_2 + x_3 = 8 \implies x_2 = 8 - t
   $$

2. **From Row 1:**
   $$
   x_1 + x_2 = 10 \implies x_1 = 10 - x_2 = 10 - (8 - t) = 2 + t
   $$

Writing in vector parametric form:
$$
\begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix} = \begin{pmatrix} 2 + t \\ 8 - t \\ t \end{pmatrix} = \begin{pmatrix} 2 \\ 8 \\ 0 \end{pmatrix} + t \begin{pmatrix} 1 \\ -1 \\ 1 \end{pmatrix}, \quad t \in \mathbb{R}
$$

The solution set is a straight line in $\mathbb{R}^3$ passing through $(2, 8, 0)$ with direction vector $(1, -1, 1)^T$.

---

## 4. Verification and Consistency Checks

1. **Test with $t = 0 \implies (x_1, x_2, x_3) = (2, 8, 0)$:**
   - Equation 1: $2 + 8 = 10$ ($\checkmark$)
   - Equation 2: $8 + 0 = 8$ ($\checkmark$)
   - Equation 3: $2 - 0 = 2$ ($\checkmark$)

2. **Test with $t = 3 \implies (x_1, x_2, x_3) = (5, 5, 3)$:**
   - Equation 1: $5 + 5 = 10$ ($\checkmark$)
   - Equation 2: $5 + 3 = 8$ ($\checkmark$)
   - Equation 3: $5 - 3 = 2$ ($\checkmark$)

3. **Check with Only the First Two Equations:**
   If we omit Equation 3 completely:
   $$
   \begin{cases} x_1 + x_2 = 10 \\ x_2 + x_3 = 8 \end{cases}
   $$
   Choosing $x_3 = t \implies x_2 = 8 - t \implies x_1 = 10 - (8 - t) = 2 + t$.
   This produces the exact same solution line $\begin{pmatrix} 2 + t \\ 8 - t \\ t \end{pmatrix}$, confirming that Equation 3 was entirely dispensable.
