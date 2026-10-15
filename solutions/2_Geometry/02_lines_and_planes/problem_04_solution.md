# Solution to Exercise 4: Plane Through Three Points

## 1. Problem Statement

Find the Cartesian equation of the plane passing through the three points:
$$
A = (1, 0, 0), \qquad B = (0, 1, 0), \qquad C = (0, 0, 1)
$$

1. Construct two linearly independent displacement vectors lying in the plane.
2. Use the vector cross product to find a normal vector $n$ to the plane.
3. Formulate the general equation of the plane $Ax + By + Cz + D = 0$.
4. Check that all three points $A, B$, and $C$ satisfy the resulting equation.

---

## 2. Theoretical Background and Concepts

1. **Coplanar Vectors and Normal Construction:**
   Given three non-collinear points $A, B, C$ in $\mathbb{R}^3$, the vectors:
   $$
   u = \overrightarrow{AB} = B - A, \qquad v = \overrightarrow{AC} = C - A
   $$
   lie completely within the plane $\Pi$ defined by these points and span its 2-dimensional tangent subspace.

2. **The Cross Product as Normal Vector:**
   The cross product $u \times v$ yields a non-zero vector that is simultaneously perpendicular to both $u$ and $v$:
   $$
   n = u \times v
   $$
   Since $n$ is perpendicular to two non-parallel vectors in the plane, it is perpendicular to the entire plane.

3. **Intercept Form of a Plane:**
   When a plane intersects the coordinate axes at points $(a, 0, 0)$, $(0, b, 0)$, and $(0, 0, c)$ with $a, b, c \ne 0$, its equation can be represented in the symmetric intercept form:
   $$
   \frac{x}{a} + \frac{y}{b} + \frac{z}{c} = 1
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Construct Two Vectors Lying in the Plane

Using $A(1, 0, 0)$ as the common base vertex:

1. **Vector $u = \overrightarrow{AB}$:**
   $$
   u = B - A = \begin{pmatrix} 0 - 1 \\ 1 - 0 \\ 0 - 0 \end{pmatrix} = \begin{pmatrix} -1 \\ 1 \\ 0 \end{pmatrix}
   $$

2. **Vector $v = \overrightarrow{AC}$:**
   $$
   v = C - A = \begin{pmatrix} 0 - 1 \\ 0 - 0 \\ 1 - 0 \end{pmatrix} = \begin{pmatrix} -1 \\ 0 \\ 1 \end{pmatrix}
   $$

In row notation:
$$
u = (-1, 1, 0), \qquad v = (-1, 0, 1)
$$

---

### Step 2: Compute the Normal Vector via Cross Product

Compute $n = u \times v$:
$$
n = \det \begin{pmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ -1 & 1 & 0 \\ -1 & 0 & 1 \end{pmatrix}
$$

Expand along the first row:
$$
n = \mathbf{i} \det \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} - \mathbf{j} \det \begin{pmatrix} -1 & 0 \\ -1 & 1 \end{pmatrix} + \mathbf{k} \det \begin{pmatrix} -1 & 1 \\ -1 & 0 \end{pmatrix}
$$

Evaluate the minor determinants:
- $\mathbf{i}$-component: $(1)(1) - (0)(0) = 1 - 0 = 1$
- $\mathbf{j}$-component: $-[(-1)(1) - (0)(-1)] = -[-1 - 0] = 1$
- $\mathbf{k}$-component: $(-1)(0) - (1)(-1) = 0 - (-1) = 1$

Thus, the normal vector is:
$$
n = \mathbf{i} + \mathbf{j} + \mathbf{k} = \begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix}
$$

In row notation:
$$
n = (1, 1, 1)
$$

---

### Step 3: Formulate the Equation of the Plane

Using normal vector $n = (1, 1, 1)$ and base point $A(1, 0, 0)$:
$$
n \cdot (X - A) = 0
$$
$$
1(x - 1) + 1(y - 0) + 1(z - 0) = 0
$$
$$
(x - 1) + y + z = 0 \implies x + y + z - 1 = 0
$$

Writing in standard Cartesian form:
$$
x + y + z = 1
$$

---

### Step 4: Verification of All Three Points

1. **Test Point $A(1, 0, 0)$:**
   $$
   1 + 0 + 0 = 1 \quad (\checkmark)
   $$
2. **Test Point $B(0, 1, 0)$:**
   $$
   0 + 1 + 0 = 1 \quad (\checkmark)
   $$
3. **Test Point $C(0, 0, 1)$:**
   $$
   0 + 0 + 1 = 1 \quad (\checkmark)
   $$

All three given points satisfy the equation.

---

## 4. Verification and Consistency Checks

1. **Intercept Form Equivalence:**
   The coordinate intercepts on the $x$-, $y$-, and $z$-axes are $a = 1$, $b = 1$, and $c = 1$.
   The intercept formula yields:
   $$
   \frac{x}{1} + \frac{y}{1} + \frac{z}{1} = 1 \iff x + y + z = 1 \quad (\checkmark)
   $$

2. **Orthogonality of the Normal Vector to the Triangle Edges:**
   - $n \cdot \overrightarrow{AB} = (1)(-1) + (1)(1) + (1)(0) = -1 + 1 + 0 = 0 \quad (\checkmark)$
   - $n \cdot \overrightarrow{AC} = (1)(-1) + (1)(0) + (1)(1) = -1 + 0 + 1 = 0 \quad (\checkmark)$
   - $n \cdot \overrightarrow{BC} = (1, 1, 1) \cdot (0 - 0, 0 - 1, 1 - 0) = (1, 1, 1) \cdot (0, -1, 1) = 0 - 1 + 1 = 0 \quad (\checkmark)$
   Vector $n = (1, 1, 1)$ is orthogonal to all three perimeter edges of $\triangle ABC$.
