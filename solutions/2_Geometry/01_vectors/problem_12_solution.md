# Solution to Exercise 12: A Normal Vector to a Plane

## 1. Problem Statement

Given three points in three-dimensional Euclidean space $\mathbb{R}^3$:
$$
A = (1, 0, 2), \qquad B = (2, 1, 0), \qquad C = (0, 3, 1)
$$

1. Construct two displacement vectors lying in the plane defined by points $A, B$, and $C$.
2. Find a normal vector $n$ perpendicular to both vectors (and hence perpendicular to the plane) using the cross product.
3. Verify the perpendicularity of $n$ to each spanning vector using the dot product.

---

## 2. Theoretical Background and Concepts

1. **Planar Representation via Displacement Vectors:**
   Any three non-collinear points $A, B, C$ uniquely determine a plane in $\mathbb{R}^3$. Two directional vectors lying entirely within this plane are formed by fixing a base vertex (say $A$) and taking differences with the other two vertices:
   $$
   u = \overrightarrow{AB} = B - A, \qquad v = \overrightarrow{AC} = C - A
   $$

2. **The Normal Vector to a Plane:**
   A vector $n$ is normal (perpendicular) to a plane if it is perpendicular to every vector lying in that plane.
   Because $u$ and $v$ span the directional subspace of the plane, any vector perpendicular to both $u$ and $v$ is automatically perpendicular to the entire plane.
   The standard algebraic tool to generate a vector simultaneously perpendicular to two 3D vectors is their **cross product**:
   $$
   n = u \times v
   $$

3. **Orthogonality Check via Dot Product:**
   By the fundamental property of the dot product, vector $n$ is perpendicular to $u$ and $v$ if and only if:
   $$
   n \cdot u = 0 \quad \text{and} \quad n \cdot v = 0
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Construct Two Vectors in the Plane

Choose point $A$ as the reference vertex:

1. **Construct vector $u = \overrightarrow{AB}$:**
   $$
   u = \overrightarrow{AB} = B - A = \begin{pmatrix} 2 - 1 \\ 1 - 0 \\ 0 - 2 \end{pmatrix} = \begin{pmatrix} 1 \\ 1 \\ -2 \end{pmatrix}
   $$

2. **Construct vector $v = \overrightarrow{AC}$:**
   $$
   v = \overrightarrow{AC} = C - A = \begin{pmatrix} 0 - 1 \\ 3 - 0 \\ 1 - 2 \end{pmatrix} = \begin{pmatrix} -1 \\ 3 \\ -1 \end{pmatrix}
   $$

In row notation:
$$
u = (1, 1, -2), \qquad v = (-1, 3, -1)
$$

---

### Step 2: Compute the Normal Vector $n = u \times v$

Set up the formal cross product determinant:
$$
n = u \times v = \det \begin{pmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 1 & -2 \\ -1 & 3 & -1 \end{pmatrix}
$$

Expand along the first row:
$$
n = \mathbf{i} \det \begin{pmatrix} 1 & -2 \\ 3 & -1 \end{pmatrix} - \mathbf{j} \det \begin{pmatrix} 1 & -2 \\ -1 & -1 \end{pmatrix} + \mathbf{k} \det \begin{pmatrix} 1 & 1 \\ -1 & 3 \end{pmatrix}
$$

Evaluate each $2 \times 2$ minor determinant:
- $\mathbf{i}$-component: $(1)(-1) - (-2)(3) = -1 - (-6) = -1 + 6 = 5$
- $\mathbf{j}$-component: $-[(1)(-1) - (-2)(-1)] = -[-1 - 2] = -(-3) = 3$
- $\mathbf{k}$-component: $(1)(3) - (1)(-1) = 3 - (-1) = 3 + 1 = 4$

Thus, the normal vector is:
$$
n = 5\mathbf{i} + 3\mathbf{j} + 4\mathbf{k} = \begin{pmatrix} 5 \\ 3 \\ 4 \end{pmatrix}
$$

In row notation:
$$
n = (5, 3, 4)
$$

*(Note: Any non-zero scalar multiple $k \cdot n$, such as $(-5, -3, -4)$, is also a valid normal vector.)*

---

### Step 3: Check Perpendicularity Using Dot Products

1. **Test orthogonality to $u = (1, 1, -2)$:**
   $$
   n \cdot u = (5)(1) + (3)(1) + (4)(-2) = 5 + 3 - 8 = 0 \quad (\checkmark)
   $$
   Since $n \cdot u = 0$, $n$ is perpendicular to $u$.

2. **Test orthogonality to $v = (-1, 3, -1)$:**
   $$
   n \cdot v = (5)(-1) + (3)(3) + (4)(-1) = -5 + 9 - 4 = 0 \quad (\checkmark)
   $$
   Since $n \cdot v = 0$, $n$ is perpendicular to $v$.

Because $n$ is perpendicular to both spanning vectors, it is confirmed to be perpendicular to the plane containing $A, B$, and $C$.

---

## 4. Verification and Consistency Checks

1. **Third In-Plane Vector Check ($\overrightarrow{BC}$):**
   The displacement vector between $B$ and $C$ also lies in the plane:
   $$
   \overrightarrow{BC} = C - B = (0 - 2, 3 - 1, 1 - 0) = (-2, 2, 1)
   $$
   Test the dot product with $n = (5, 3, 4)$:
   $$
   n \cdot \overrightarrow{BC} = (5)(-2) + (3)(2) + (4)(1) = -10 + 6 + 4 = 0 \quad (\checkmark)
   $$
   $n$ is orthogonal to $\overrightarrow{BC}$ as well.

2. **Equation of the Plane:**
   Using point $A(1, 0, 2)$ and normal vector $n = (5, 3, 4)$, the Cartesian equation of the plane is:
   $$
   5(x - 1) + 3(y - 0) + 4(z - 2) = 0 \implies 5x + 3y + 4z - 13 = 0
   $$
   Substitute all three points to verify:
   - For $A(1, 0, 2)$: $5(1) + 3(0) + 4(2) = 5 + 8 = 13 \quad (\checkmark)$
   - For $B(2, 1, 0)$: $5(2) + 3(1) + 4(0) = 10 + 3 = 13 \quad (\checkmark)$
   - For $C(0, 3, 1)$: $5(0) + 3(3) + 4(1) = 9 + 4 = 13 \quad (\checkmark)$
   All three points satisfy the plane equation.
