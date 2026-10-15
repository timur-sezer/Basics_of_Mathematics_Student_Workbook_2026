# Solution to Exercise 6: Angle Between Planes

## 1. Problem Statement

Given the Cartesian equations of two planes in $\mathbb{R}^3$:
$$
\Pi_1: x + y + z = 1, \qquad \Pi_2: x - y = 2
$$

1. Extract the normal vectors of both planes and determine whether the planes are parallel.
2. If they are not parallel, compute the acute dihedral angle $\theta$ between the two planes (in radians and degrees).
3. Explain why the normal vectors alone contain all the geometric information necessary to determine parallelism and the angle between planes.

---

## 2. Theoretical Background and Concepts

1. **Normal Vectors to Planes:**
   For a plane given in general form $Ax + By + Cz + D = 0$, the vector:
   $$
   n = (A, B, C)
   $$
   is perpendicular to every vector lying within that plane.

2. **Parallelism of Planes:**
   Two planes $\Pi_1$ and $\Pi_2$ are parallel if and only if their respective normal vectors $n_1$ and $n_2$ are collinear:
   $$
   \Pi_1 \parallel \Pi_2 \iff n_1 = k n_2 \text{ for some } k \ne 0
   $$

3. **Dihedral Angle Between Two Planes:**
   The angle $\theta \in [0, \pi/2]$ between two non-parallel planes is defined as the acute angle between their normal lines:
   $$
   \cos \theta = \frac{|n_1 \cdot n_2|}{\|n_1\| \, \|n_2\|}
   $$
   The absolute value in the numerator ensures that the calculated dihedral angle is acute ($\theta \le 90^\circ$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Extract Normal Vectors and Test Parallelism

Read off the linear coefficients from each plane equation:
- For $\Pi_1: 1x + 1y + 1z = 1 \implies n_1 = (1, 1, 1)$
- For $\Pi_2: 1x - 1y + 0z = 2 \implies n_2 = (1, -1, 0)$

**Test for Parallelism:**
Check if $n_1$ is proportional to $n_2$:
$$
\begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix} = k \begin{pmatrix} 1 \\ -1 \\ 0 \end{pmatrix}
$$
- From the first coordinate: $1 = k \implies k = 1$.
- From the second coordinate: $1 = k(-1) = -1 \implies 1 = -1$ (Contradiction).
- From the third coordinate: $1 = k(0) = 0$ (Contradiction).

Because the normal vectors are not proportional ($n_1 \nparallel n_2$), **the planes $\Pi_1$ and $\Pi_2$ are not parallel**; they intersect along a straight line in space.

---

### Step 2: Compute the Angle Between the Planes

1. **Compute the dot product $n_1 \cdot n_2$:**
   $$
   n_1 \cdot n_2 = (1)(1) + (1)(-1) + (1)(0) = 1 - 1 + 0 = 0
   $$

2. **Compute the norms $\|n_1\|$ and $\|n_2\|$:**
   $$
   \|n_1\| = \sqrt{1^2 + 1^2 + 1^2} = \sqrt{3}
   $$
   $$
   \|n_2\| = \sqrt{1^2 + (-1)^2 + 0^2} = \sqrt{1 + 1 + 0} = \sqrt{2}
   $$

3. **Evaluate $\cos \theta$:**
   $$
   \cos \theta = \frac{|n_1 \cdot n_2|}{\|n_1\| \, \|n_2\|} = \frac{|0|}{\sqrt{3}\sqrt{2}} = 0
   $$

4. **Determine the angle $\theta$:**
   $$
   \theta = \arccos(0) = \frac{\pi}{2} \text{ radians} = 90^\circ
   $$

The planes $\Pi_1$ and $\Pi_2$ are **perpendicular (orthogonal)** to each other.

---

### Step 3: Why Normal Vectors Alone Suffice

1. **Invariance Under Translation:**
   - The position of a plane in space is defined by its orientation (tilt) plus an offset distance from the origin.
   - The dihedral angle between two planes measures only their relative spatial inclination; translating either plane along any direction alters its intersection line but leaves the angle between the planar surfaces unchanged.
2. **Geometric Normal Rotation:**
   - The normal vector $n_1$ is obtained by rotating the tangent plane $\Pi_1$ by $90^\circ$ around any in-plane axis.
   - Rotating both planes by $90^\circ$ preserves the relative angle between them identically:
     $$
     \angle(\Pi_1, \Pi_2) = \angle(n_1, n_2)
     $$
   - Therefore, the constant terms ($D_1 = -1, D_2 = -2$) have zero influence on parallelism or angles, making the normal vectors $n_1$ and $n_2$ completely sufficient.

---

## 4. Verification and Consistency Checks

1. **Direction Vector of the Intersection Line:**
   The intersection line of two planes must be perpendicular to both normal vectors. Its direction is given by $v = n_1 \times n_2$:
   $$
   v = \det \begin{pmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 1 & 1 \\ 1 & -1 & 0 \end{pmatrix} = \begin{pmatrix} 0 - (-1) \\ -(0 - 1) \\ -1 - 1 \end{pmatrix} = \begin{pmatrix} 1 \\ 1 \\ -2 \end{pmatrix}
   $$
   Check that $v \perp n_1$ and $v \perp n_2$:
   - $v \cdot n_1 = 1(1) + 1(1) - 2(1) = 1 + 1 - 2 = 0 \quad (\checkmark)$
   - $v \cdot n_2 = 1(1) + 1(-1) - 2(0) = 1 - 1 + 0 = 0 \quad (\checkmark)$

2. **Pythagorean Identity on Normals:**
   When two vectors are orthogonal, $\|n_1 + n_2\|^2 = \|n_1\|^2 + \|n_2\|^2$:
   - $n_1 + n_2 = (1+1, 1-1, 1+0) = (2, 0, 1)$
   - $\|n_1 + n_2\|^2 = 2^2 + 0^2 + 1^2 = 5$
   - $\|n_1\|^2 + \|n_2\|^2 = (\sqrt{3})^2 + (\sqrt{2})^2 = 3 + 2 = 5 \quad (\checkmark)$
   The Pythagorean theorem confirms $\theta = 90^\circ$.
