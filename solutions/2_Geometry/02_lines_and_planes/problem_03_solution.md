# Solution to Exercise 3: Plane Through a Point with a Given Normal Vector

## 1. Problem Statement

Find the equation of the plane passing through the point:
$$
P = (1, -2, 3)
$$
and perpendicular to the normal vector:
$$
n = (2, 1, -1)
$$

1. Derive the general (implicit) equation of the plane $Ax + By + Cz + D = 0$.
2. Check the result by substituting the coordinates of point $P$.
3. Explain the geometric and algebraic role of the normal vector in defining a plane in $\mathbb{R}^3$.

---

## 2. Theoretical Background and Concepts

1. **Definition of a Plane via a Normal Vector:**
   In three-dimensional Euclidean space $\mathbb{R}^3$, a plane $\Pi$ is uniquely determined by specifying:
   - A base point $P(x_0, y_0, z_0) \in \Pi$,
   - A non-zero normal vector $n = (A, B, C) \perp \Pi$.

2. **Vector Equation of the Plane:**
   A point $X(x, y, z)$ lies on the plane $\Pi$ if and only if the displacement vector $\overrightarrow{PX}$ lies completely in the plane.
   Since every vector in the plane is perpendicular to the normal vector $n$, the necessary and sufficient condition is:
   $$
   n \cdot \overrightarrow{PX} = 0 \iff n \cdot (X - P) = 0
   $$

3. **General Coordinate Form:**
   Expanding the dot product in Cartesian coordinates gives:
   $$
   A(x - x_0) + B(y - y_0) + C(z - z_0) = 0
   $$
   Expanding and grouping constants yields:
   $$
   Ax + By + Cz + D = 0, \quad \text{where } D = -(A x_0 + B y_0 + C z_0)
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up the Vector Equation

We are given:
- $P = (x_0, y_0, z_0) = (1, -2, 3)$
- $n = (A, B, C) = (2, 1, -1)$

Substitute into the point-normal equation $n \cdot (X - P) = 0$:
$$
2(x - 1) + 1(y - (-2)) + (-1)(z - 3) = 0
$$
$$
2(x - 1) + 1(y + 2) - 1(z - 3) = 0
$$

---

### Step 2: Expand and Simplify to General Form

Distribute the coefficients:
$$
2x - 2 + y + 2 - z + 3 = 0
$$
Combine the constant terms:
$$
(-2) + 2 + 3 = 3
$$
Thus:
$$
2x + y - z + 3 = 0
$$

Equivalently, writing with the constant term on the right-hand side:
$$
2x + y - z = -3
$$

---

### Step 3: Verification by Substituting Point $P$

Substitute the coordinates $(x, y, z) = (1, -2, 3)$ into the left-hand side of $2x + y - z + 3 = 0$:
$$
\text{LHS} = 2(1) + (-2) - (3) + 3 = 2 - 2 - 3 + 3 = 0
$$
Since $\text{LHS} = \text{RHS} = 0$, the plane equation is verified to pass through point $P$.

---

### Step 4: The Role of the Normal Vector

1. **Fixing the Spatial Orientation (Tilt):**
   - In $\mathbb{R}^3$, an infinite family of parallel planes share the same orientation.
   - The normal vector $n = (A, B, C)$ dictates the coefficients of the linear terms $Ax + By + Cz$. The ratios $A : B : C$ uniquely define the orientation (attitude) of the plane in space.
   - Any two planes sharing parallel normal vectors are parallel to each other.
2. **Orthogonality as a Filtering Mechanism:**
   - The equation $n \cdot (X - P) = 0$ acts as an algebraic filter: it accepts point $X$ if and only if the line segment from $P$ to $X$ is perpendicular to $n$.
   - While the base point $P$ anchors the plane at a specific location in space (fixing the constant $D$), the normal vector $n$ completely dictates its direction in space.

---

## 4. Verification and Consistency Checks

1. **Orthogonality to Displacement Vectors:**
   Choose another point on the plane, for instance set $x = 0, y = 0 \implies -z = -3 \implies z = 3$, giving $Q(0, 0, 3)$.
   - Check that $Q$ is on the plane: $2(0) + 0 - 3 = -3 \quad (\checkmark)$.
   - Form the in-plane displacement vector:
     $$
     \overrightarrow{PQ} = Q - P = (0 - 1, 0 - (-2), 3 - 3) = (-1, 2, 0)
     $$
   - Evaluate $n \cdot \overrightarrow{PQ}$:
     $$
     n \cdot \overrightarrow{PQ} = (2)(-1) + (1)(2) + (-1)(0) = -2 + 2 + 0 = 0 \quad (\checkmark)
     $$
   The vector within the plane is perpendicular to $n$.

2. **Distance from the Origin Check:**
   The signed distance from the origin $(0, 0, 0)$ to the plane is:
   $$
   d_0 = \frac{D}{\|n\|} = \frac{3}{\sqrt{2^2 + 1^2 + (-1)^2}} = \frac{3}{\sqrt{6}} = \frac{\sqrt{6}}{2} \quad (\checkmark)
   $$
