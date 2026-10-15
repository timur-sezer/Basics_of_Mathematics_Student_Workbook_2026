# Solution to Exercise 12: Intersection Line of Two Planes

## 1. Problem Statement

Given the Cartesian equations of two non-parallel planes in $\mathbb{R}^3$:
$$
\Pi_1: x + y + z = 3, \qquad \Pi_2: x - y + z = 1
$$

1. Find a parametric vector equation for the straight line $L = \Pi_1 \cap \Pi_2$ formed by their intersection.
2. Determine the direction vector of the line in **two distinct ways**:
   - **Method A:** By solving the system of linear equations directly via variable elimination.
   - **Method B:** By computing the cross product of the normal vectors of the two planes ($v = n_1 \times n_2$).
3. Compare the two direction vectors obtained and explain why they describe the same line.

---

## 2. Theoretical Background and Concepts

1. **Intersection Line as the Solution of an Underdetermined Linear System:**
   Two non-parallel planes intersect along a 1-dimensional straight line. The points on this line satisfy the system of two equations in three unknowns:
   $$
   \begin{cases}
   A_1 x + B_1 y + C_1 z = d_1 \\
   A_2 x + B_2 y + C_2 z = d_2
   \end{cases}
   $$
   Because the coefficient matrix has rank $2$, the solution space has dimension $3 - 2 = 1$ degree of freedom, yielding the parametric line $X(t) = P_0 + t v$.

2. **Geometric Cross Product Method:**
   The line of intersection $L$ lies entirely inside plane $\Pi_1$ and entirely inside plane $\Pi_2$.
   - Any vector parallel to $L$ must be perpendicular to the normal vector $n_1$ of $\Pi_1$.
   - It must also be perpendicular to the normal vector $n_2$ of $\Pi_2$.
   - Therefore, the direction vector $v$ of the line must be parallel to the cross product of the two normals:
     $$
     v \parallel (n_1 \times n_2)
     $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Method A — Direct Elimination from the System of Equations

Set up the system:
$$
\begin{cases}
x + y + z = 3, & \text{(Equation 1)} \\
x - y + z = 1. & \text{(Equation 2)}
\end{cases}
$$

1. **Eliminate $x$ and $z$ by subtracting Equation 2 from Equation 1:**
   $$
   (x + y + z) - (x - y + z) = 3 - 1
   $$
   $$
   2y = 2 \implies y = 1
   $$
   The $y$-coordinate is constant and identically $1$ for all points on the intersection line.

2. **Substitute $y = 1$ back into Equation 1:**
   $$
   x + 1 + z = 3 \implies x + z = 2 \implies x = 2 - z
   $$

3. **Choose $z$ as the free parameter $t$ ($z = t$ with $t \in \mathbb{R}$):**
   - $x(t) = 2 - t$
   - $y(t) = 1$
   - $z(t) = t$

4. **Write in parametric vector form:**
   $$
   \begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} 2 \\ 1 \\ 0 \end{pmatrix} + t \begin{pmatrix} -1 \\ 0 \\ 1 \end{pmatrix}, \quad t \in \mathbb{R}
   $$
   From Method A, the direction vector is:
   $$
   v_A = \begin{pmatrix} -1 \\ 0 \\ 1 \end{pmatrix}
   $$

---

### Step 2: Method B — Cross Product of the Normal Vectors

1. **Read off the normal vectors:**
   - From $\Pi_1: 1x + 1y + 1z = 3 \implies n_1 = (1, 1, 1)$
   - From $\Pi_2: 1x - 1y + 1z = 1 \implies n_2 = (1, -1, 1)$

2. **Compute $v_B = n_1 \times n_2$:**
   $$
   v_B = \det \begin{pmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 1 & 1 \\ 1 & -1 & 1 \end{pmatrix}
   $$
   Expand along the first row:
   $$
   v_B = \mathbf{i} \det \begin{pmatrix} 1 & 1 \\ -1 & 1 \end{pmatrix} - \mathbf{j} \det \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix} + \mathbf{k} \det \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}
   $$
   Evaluate components:
   - $\mathbf{i}$-component: $(1)(1) - (1)(-1) = 1 - (-1) = 2$
   - $\mathbf{j}$-component: $-[(1)(1) - (1)(1)] = -(1 - 1) = 0$
   - $\mathbf{k}$-component: $(1)(-1) - (1)(1) = -1 - 1 = -2$

   Thus:
   $$
   v_B = 2\mathbf{i} + 0\mathbf{j} - 2\mathbf{k} = \begin{pmatrix} 2 \\ 0 \\ -2 \end{pmatrix}
   $$

---

### Step 3: Comparison of the Results

Compare the two direction vectors $v_A$ and $v_B$:
$$
v_B = \begin{pmatrix} 2 \\ 0 \\ -2 \end{pmatrix} = -2 \begin{pmatrix} -1 \\ 0 \\ 1 \end{pmatrix} = -2 v_A
$$

1. **Collinearity:**
   The two vectors are scalar multiples of each other with scale factor $\lambda = -2 \ne 0$.
2. **Geometric Equivalence:**
   In affine geometry, any non-zero scalar multiple of a direction vector generates the exact same line, merely re-scaling or reversing the orientation of the parameterization ($t' = -2t$).
3. **Synthesis:**
   Using $P_0(2, 1, 0)$ as the base point, both:
   $$
   X(t) = \begin{pmatrix} 2 \\ 1 \\ 0 \end{pmatrix} + t \begin{pmatrix} -1 \\ 0 \\ 1 \end{pmatrix} \quad \text{and} \quad X(s) = \begin{pmatrix} 2 \\ 1 \\ 0 \end{pmatrix} + s \begin{pmatrix} 1 \\ 0 \\ -1 \end{pmatrix}
   $$
   describe the identical geometric intersection line.

---

## 4. Verification and Consistency Checks

1. **Verify Base Point $P_0(2, 1, 0)$ in Both Planes:**
   - In $\Pi_1$: $x + y + z = 2 + 1 + 0 = 3 \quad (\checkmark)$
   - In $\Pi_2$: $x - y + z = 2 - 1 + 0 = 1 \quad (\checkmark)$

2. **Orthogonality of the Cross Product Vector $v_B$:**
   - $v_B \cdot n_1 = (2)(1) + (0)(1) + (-2)(1) = 2 + 0 - 2 = 0 \quad (\checkmark)$
   - $v_B \cdot n_2 = (2)(1) + (0)(-1) + (-2)(1) = 2 + 0 - 2 = 0 \quad (\checkmark)$
   Vector $v_B$ is perpendicular to both plane normals.

3. **Arbitrary Point Check on the Line:**
   Let $t = 4 \implies P(4) = (2 - 4, 1, 4) = (-2, 1, 4)$:
   - In $\Pi_1$: $(-2) + 1 + 4 = 3 \quad (\checkmark)$
   - In $\Pi_2$: $(-2) - 1 + 4 = 1 \quad (\checkmark)$
   Both planes contain every point on the line.
