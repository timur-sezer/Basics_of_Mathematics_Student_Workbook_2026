# Solution to Exercise 5: Relative Position of Two Lines

## 1. Problem Statement

Analyze the relative geometric position of the two lines in $\mathbb{R}^3$:
$$
L_1: (x, y, z) = (1, 1, 0) + t(1, 2, 1), \quad t \in \mathbb{R}
$$
$$
L_2: (x, y, z) = (2, 0, 1) + s(0, 1, -1), \quad s \in \mathbb{R}
$$

1. Determine whether the lines are parallel, intersecting at a unique point, or skew (non-intersecting and non-parallel).
2. If they intersect, calculate their point of intersection.
3. If they do not intersect, provide a complete mathematical justification of their classification.

---

## 2. Theoretical Background and Concepts

1. **Relative Positions of Two Lines in 3D Euclidean Space:**
   In $\mathbb{R}^3$, two lines $L_1: P_1 + t v_1$ and $L_2: P_2 + s v_2$ fall into exactly one of four mutually exclusive geometric categories:
   - **Coincident (Identical):** $v_1 \parallel v_2$ and $P_1 \in L_2$ (infinitely many common points).
   - **Parallel and Distinct:** $v_1 \parallel v_2$ and $P_1 \notin L_2$ (zero common points, coplanar).
   - **Intersecting:** $v_1 \nparallel v_2$ and there exists a unique pair $(t, s)$ such that $P_1 + t v_1 = P_2 + s v_2$ (one common point, coplanar).
   - **Skew:** $v_1 \nparallel v_2$ and no intersection point exists (zero common points, non-coplanar).

2. **The Coplanarity Criterion via Scalar Triple Product:**
   Two lines are coplanar (either parallel or intersecting) if and only if the vector connecting their base points $\overrightarrow{P_1 P_2}$ lies in the plane spanned by $v_1$ and $v_2$, which is algebraically equivalent to:
   $$
   [v_1, v_2, \overrightarrow{P_1 P_2}] = (v_1 \times v_2) \cdot \overrightarrow{P_1 P_2} = 0
   $$
   If this scalar triple product is non-zero, the volume of the parallelepiped spanned by the three vectors is strictly positive, proving definitively that the lines are **skew**.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Extract Base Points and Direction Vectors

From the parametric descriptions:
- For $L_1$: $P_1 = (1, 1, 0)$ and direction vector $v_1 = (1, 2, 1)$.
- For $L_2$: $P_2 = (2, 0, 1)$ and direction vector $v_2 = (0, 1, -1)$.

---

### Step 2: Test for Parallelism

Two lines are parallel if and only if their direction vectors are proportional ($v_1 = k v_2$ for some $k \in \mathbb{R}$):
$$
\begin{pmatrix} 1 \\ 2 \\ 1 \end{pmatrix} = k \begin{pmatrix} 0 \\ 1 \\ -1 \end{pmatrix}
$$
Examining the first coordinate:
$$
1 = k \cdot 0 \implies 1 = 0 \quad (\text{Impossible})
$$
Because no such scalar $k$ exists, the direction vectors $v_1$ and $v_2$ are **not parallel**. Therefore, the lines are neither parallel nor coincident.

---

### Step 3: Test for an Intersection Point

Equate the parametric coordinate expressions of $L_1$ and $L_2$:
$$
\begin{cases}
1 + t = 2 + 0s, & \text{(from $x$-coordinate)} \\
1 + 2t = 0 + s, & \text{(from $y$-coordinate)} \\
0 + t = 1 - s. & \text{(from $z$-coordinate)}
\end{cases}
$$

1. **From the $x$-equation:**
   $$
   1 + t = 2 \implies t = 1
   $$

2. **Substitute $t = 1$ into the $y$-equation to find $s$:**
   $$
   1 + 2(1) = s \implies s = 3
   $$

3. **Check consistency in the $z$-equation:**
   - Left-hand side (using $t = 1$):
     $$
     \text{LHS} = t = 1
     $$
   - Right-hand side (using $s = 3$):
     $$
     \text{RHS} = 1 - s = 1 - 3 = -2
     $$
   - Comparing both sides:
     $$
     1 \ne -2 \quad (\text{Contradiction!})
     $$

The linear system in unknowns $(t, s)$ is **inconsistent** (has no solution). There is no point common to both lines.

---

### Step 4: Conclusion and Classification

Because:
1. The direction vectors $v_1$ and $v_2$ are **not parallel**, and
2. The lines have **no point of intersection**,

the two lines $L_1$ and $L_2$ are **skew lines**.

---

## 4. Verification and Consistency Checks

1. **Scalar Triple Product Coplanarity Test:**
   - Connecting vector: $\overrightarrow{P_1 P_2} = P_2 - P_1 = (2 - 1, 0 - 1, 1 - 0) = (1, -1, 1)$.
   - Compute the cross product $v_1 \times v_2$:
     $$
     v_1 \times v_2 = \det \begin{pmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 2 & 1 \\ 0 & 1 & -1 \end{pmatrix} = \begin{pmatrix} 2(-1) - 1(1) \\ -(1(-1) - 1(0)) \\ 1(1) - 2(0) \end{pmatrix} = \begin{pmatrix} -3 \\ 1 \\ 1 \end{pmatrix}
     $$
   - Compute the scalar triple product:
     $$
     (v_1 \times v_2) \cdot \overrightarrow{P_1 P_2} = (-3)(1) + (1)(-1) + (1)(1) = -3 - 1 + 1 = -3
     $$
   Because $(v_1 \times v_2) \cdot \overrightarrow{P_1 P_2} = -3 \ne 0$, the vectors are not coplanar, confirming that $L_1$ and $L_2$ are strictly skew.

2. **Distance Between the Two Skew Lines:**
   The shortest distance between two skew lines is:
   $$
   d(L_1, L_2) = \frac{|(v_1 \times v_2) \cdot \overrightarrow{P_1 P_2}|}{\|v_1 \times v_2\|} = \frac{|-3|}{\sqrt{(-3)^2 + 1^2 + 1^2}} = \frac{3}{\sqrt{9 + 1 + 1}} = \frac{3}{\sqrt{11}} \approx 0.9045 > 0
   $$
   The strictly positive minimum distance ($d > 0$) confirms that the lines never meet.
