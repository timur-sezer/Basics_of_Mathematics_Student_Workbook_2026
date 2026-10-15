# Solution to Exercise 13: Do Four Points Lie in One Plane?

## 1. Problem Statement

Given the four points in $\mathbb{R}^3$:
$$
A = (0, 0, 0), \qquad B = (1, 2, 0), \qquad C = (0, 1, 1), \qquad D = (2, 5, 1)
$$

1. Construct the displacement vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$.
2. Compute the normal vector $n = \overrightarrow{AB} \times \overrightarrow{AC}$.
3. Construct the displacement vector $\overrightarrow{AD}$ and compute the dot product $\overrightarrow{AD} \cdot n$.
4. Based on this dot product, decide whether point $D$ lies in the plane determined by $A, B$, and $C$, and justify the geometric criterion.

---

## 2. Theoretical Background and Concepts

1. **Coplanarity of Vectors and the Scalar Triple Product:**
   Three vectors $u, v, w \in \mathbb{R}^3$ are coplanar (lie in the same plane through the origin) if and only if their **scalar triple product** is zero:
   $$
   (u \times v) \cdot w = 0
   $$
   Geometrically, the absolute value $|(u \times v) \cdot w|$ represents the volume of the parallelepiped spanned by $u, v$, and $w$. If this volume is zero, the parallelepiped is completely flattened, meaning the three vectors lie in a single plane.

2. **Geometric Coplanarity Criterion for Four Points:**
   Four points $A, B, C, D$ lie in the same plane if and only if the displacement vector $\overrightarrow{AD}$ lies in the plane spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$.
   - The vector $n = \overrightarrow{AB} \times \overrightarrow{AC}$ is perpendicular to the plane containing $A, B, C$.
   - Any vector lying in that plane must be perpendicular to $n$.
   - Therefore, $D$ belongs to the plane if and only if:
     $$
     \overrightarrow{AD} \cdot n = 0
     $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Construct Vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$

Subtract vertex $A(0, 0, 0)$ from $B(1, 2, 0)$ and $C(0, 1, 1)$:
$$
\overrightarrow{AB} = B - A = \begin{pmatrix} 1 - 0 \\ 2 - 0 \\ 0 - 0 \end{pmatrix} = \begin{pmatrix} 1 \\ 2 \\ 0 \end{pmatrix}
$$
$$
\overrightarrow{AC} = C - A = \begin{pmatrix} 0 - 0 \\ 1 - 0 \\ 1 - 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \\ 1 \end{pmatrix}
$$

In row notation:
$$
\overrightarrow{AB} = (1, 2, 0), \qquad \overrightarrow{AC} = (0, 1, 1)
$$

---

### Step 2: Compute $n = \overrightarrow{AB} \times \overrightarrow{AC}$

Set up the determinant:
$$
n = \overrightarrow{AB} \times \overrightarrow{AC} = \det \begin{pmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix}
$$

Expand along the first row:
$$
n = \mathbf{i} \det \begin{pmatrix} 2 & 0 \\ 1 & 1 \end{pmatrix} - \mathbf{j} \det \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} + \mathbf{k} \det \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}
$$

Evaluate each component:
- $\mathbf{i}$-component: $(2)(1) - (0)(1) = 2 - 0 = 2$
- $\mathbf{j}$-component: $-[(1)(1) - (0)(0)] = -(1 - 0) = -1$
- $\mathbf{k}$-component: $(1)(1) - (2)(0) = 1 - 0 = 1$

Thus, the normal vector to the plane $ABC$ is:
$$
n = 2\mathbf{i} - \mathbf{j} + \mathbf{k} = \begin{pmatrix} 2 \\ -1 \\ 1 \end{pmatrix}
$$

In row notation:
$$
n = (2, -1, 1)
$$

---

### Step 3: Construct $\overrightarrow{AD}$ and Evaluate $\overrightarrow{AD} \cdot n$

1. **Construct vector $\overrightarrow{AD}$:**
   $$
   \overrightarrow{AD} = D - A = \begin{pmatrix} 2 - 0 \\ 5 - 0 \\ 1 - 0 \end{pmatrix} = \begin{pmatrix} 2 \\ 5 \\ 1 \end{pmatrix}
   $$

2. **Compute the dot product $\overrightarrow{AD} \cdot n$:**
   $$
   \overrightarrow{AD} \cdot n = (2)(2) + (5)(-1) + (1)(1)
   $$
   $$
   \overrightarrow{AD} \cdot n = 4 - 5 + 1 = 0
   $$

The dot product evaluates to exactly zero:
$$
\overrightarrow{AD} \cdot n = 0
$$

---

### Step 4: Decision and Justification of the Criterion

**Decision:**
**Yes, point $D$ lies in the plane determined by points $A, B$, and $C$.** The four points $A, B, C, D$ are coplanar.

**Justification of the Criterion:**
1. The cross product $n = \overrightarrow{AB} \times \overrightarrow{AC}$ defines the normal direction orthogonal to every line and displacement lying in the plane $\Pi$ containing $A, B$, and $C$.
2. The plane $\Pi$ consists of all points $P \in \mathbb{R}^3$ such that $\overrightarrow{AP} \perp n$, which is algebraically expressed by the equation:
   $$
   \overrightarrow{AP} \cdot n = 0
   $$
3. Since point $A$ is in the plane and $\overrightarrow{AD} \cdot n = 0$, the segment connecting $A$ to $D$ has zero projection onto the normal direction $n$. Thus, starting from $A$ and moving along $\overrightarrow{AD}$ keeps one entirely within the plane $\Pi$.
4. Equivalently, the scalar triple product $[\overrightarrow{AB}, \overrightarrow{AC}, \overrightarrow{AD}] = 0$ means the volume of the parallelepiped spanned by the three vectors is zero. The three vectors are linearly dependent, so $\overrightarrow{AD}$ can be expressed as a linear combination of $\overrightarrow{AB}$ and $\overrightarrow{AC}$.

---

## 4. Verification and Consistency Checks

1. **Direct Linear Combination Check:**
   Express $\overrightarrow{AD} = (2, 5, 1)$ as $\alpha \overrightarrow{AB} + \beta \overrightarrow{AC}$:
   $$
   \alpha \begin{pmatrix} 1 \\ 2 \\ 0 \end{pmatrix} + \beta \begin{pmatrix} 0 \\ 1 \\ 1 \end{pmatrix} = \begin{pmatrix} 2 \\ 5 \\ 1 \end{pmatrix}
   $$
   - From row 1: $\alpha = 2$.
   - From row 3: $\beta = 1$.
   - Check in row 2: $2\alpha + \beta = 2(2) + 1 = 4 + 1 = 5 \quad (\checkmark)$.
   Since $\overrightarrow{AD} = 2\overrightarrow{AB} + \overrightarrow{AC}$, $\overrightarrow{AD}$ lies strictly in the plane spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$.

2. **Cartesian Plane Equation Check:**
   With point $A(0, 0, 0)$ and normal $n = (2, -1, 1)$, the plane equation is:
   $$
   2(x - 0) - 1(y - 0) + 1(z - 0) = 0 \implies 2x - y + z = 0
   $$
   Substitute coordinates of $D(2, 5, 1)$:
   $$
   2(2) - (5) + (1) = 4 - 5 + 1 = 0 \quad (\checkmark)
   $$
   Point $D$ satisfies the plane equation.
