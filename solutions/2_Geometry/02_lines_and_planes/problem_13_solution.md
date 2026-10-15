# Solution to Exercise 13: Closest Point on a Plane

## 1. Problem Statement

Given the point $P = (3, 0, 0)$ in $\mathbb{R}^3$ and the plane $\Pi$ defined by:
$$
\Pi: x + 2y + 2z = 4
$$

1. Find the coordinates of the point $Q \in \Pi$ that is closest to point $P$.
2. Compute the minimum Euclidean distance $d(P, \Pi)$ from point $P$ to the plane.
3. Verify that the displacement segment $\overrightarrow{PQ}$ is strictly perpendicular to the plane $\Pi$.

---

## 2. Theoretical Background and Concepts

1. **Orthogonal Projection onto a Plane (Closest Point):**
   The point $Q$ on a plane $\Pi: Ax + By + Cz = d$ closest to an external point $P(x_0, y_0, z_0)$ is the orthogonal projection of $P$ onto $\Pi$.
   - The line through $P$ perpendicular to $\Pi$ has direction vector given by the plane's normal vector $n = (A, B, C)$:
     $$
     X(t) = P + t n = \begin{pmatrix} x_0 + t A \\ y_0 + t B \\ z_0 + t C \end{pmatrix}
     $$
   - Substituting into the plane equation determines the parameter value $t^*$:
     $$
     t^* = \frac{d - (A x_0 + B y_0 + C z_0)}{A^2 + B^2 + C^2} = \frac{d - n \cdot P}{\|n\|^2}
     $$
   - The closest point is $Q = P + t^* n$.

2. **Distance and Perpendicularity:**
   - The Euclidean distance is given by the length of the normal displacement vector:
     $$
     d(P, \Pi) = \|\overrightarrow{PQ}\| = |t^*| \, \|n\| = \frac{|A x_0 + B y_0 + C z_0 - d|}{\sqrt{A^2 + B^2 + C^2}}
     $$
   - Because $\overrightarrow{PQ} = t^* n$, the segment is inherently parallel to $n$, making it perpendicular to every line in the plane.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up the Perpendicular Line

From plane $\Pi: x + 2y + 2z = 4$, read off:
- Normal vector: $n = (1, 2, 2)$
- Constant term: $d = 4$

The perpendicular line passing through $P(3, 0, 0)$ is:
$$
\begin{pmatrix} x(t) \\ y(t) \\ z(t) \end{pmatrix} = \begin{pmatrix} 3 \\ 0 \\ 0 \end{pmatrix} + t \begin{pmatrix} 1 \\ 2 \\ 2 \end{pmatrix} = \begin{pmatrix} 3 + t \\ 2t \\ 2t \end{pmatrix}
$$

---

### Step 2: Intersect the Line with the Plane to Find Point $Q$

Substitute $x(t), y(t), z(t)$ into $x + 2y + 2z = 4$:
$$
(3 + t) + 2(2t) + 2(2t) = 4
$$
Expand and combine terms:
$$
3 + t + 4t + 4t = 4
$$
$$
3 + 9t = 4 \implies 9t = 4 - 3 = 1 \implies t^* = \frac{1}{9}
$$

Substitute $t^* = \frac{1}{9}$ into the coordinates:
- $x = 3 + \frac{1}{9} = \frac{27 + 1}{9} = \frac{28}{9}$
- $y = 2\left(\frac{1}{9}\right) = \frac{2}{9}$
- $z = 2\left(\frac{1}{9}\right) = \frac{2}{9}$

Thus, the closest point on the plane is:
$$
Q = \left(\frac{28}{9}, \frac{2}{9}, \frac{2}{9}\right)
$$

Check that $Q \in \Pi$:
$$
\frac{28}{9} + 2\left(\frac{2}{9}\right) + 2\left(\frac{2}{9}\right) = \frac{28 + 4 + 4}{9} = \frac{36}{9} = 4 \quad (\checkmark)
$$

---

### Step 3: Compute the Distance $d(P, \Pi)$

1. **Construct the displacement vector $\overrightarrow{PQ}$:**
   $$
   \overrightarrow{PQ} = Q - P = \begin{pmatrix} \frac{28}{9} - 3 \\ \frac{2}{9} - 0 \\ \frac{2}{9} - 0 \end{pmatrix} = \begin{pmatrix} \frac{1}{9} \\ \frac{2}{9} \\ \frac{2}{9} \end{pmatrix} = \frac{1}{9} \begin{pmatrix} 1 \\ 2 \\ 2 \end{pmatrix}
   $$

2. **Compute its Euclidean norm:**
   $$
   d(P, \Pi) = \|\overrightarrow{PQ}\| = \left\| \frac{1}{9} \begin{pmatrix} 1 \\ 2 \\ 2 \end{pmatrix} \right\| = \frac{1}{9} \sqrt{1^2 + 2^2 + 2^2} = \frac{1}{9} \sqrt{1 + 4 + 4} = \frac{1}{9} \sqrt{9} = \frac{3}{9} = \frac{1}{3}
   $$

The minimum distance is:
$$
d(P, \Pi) = \frac{1}{3} \approx 0.3333
$$

---

### Step 4: Verify Perpendicularity of $\overrightarrow{PQ}$ to the Plane

1. **Collinearity with the Normal Vector:**
   From Step 3, the displacement vector is:
   $$
   \overrightarrow{PQ} = \frac{1}{9} \begin{pmatrix} 1 \\ 2 \\ 2 \end{pmatrix} = \frac{1}{9} n
   $$
   Because $\overrightarrow{PQ}$ is a non-zero scalar multiple of the plane's normal vector $n = (1, 2, 2)$, the line segment connecting $P$ and $Q$ is parallel to the normal line, and therefore **strictly perpendicular to the plane $\Pi$**.

2. **Orthogonality to Any In-Plane Vector:**
   Let $w$ be any displacement vector lying in plane $\Pi$ (for example, pick points $A(4, 0, 0)$ and $B(0, 2, 0)$ on $\Pi$):
   $$
   w = B - A = (-4, 2, 0)
   $$
   Evaluate the dot product with $\overrightarrow{PQ}$:
   $$
   \overrightarrow{PQ} \cdot w = \frac{1}{9} \begin{pmatrix} 1 \\ 2 \\ 2 \end{pmatrix} \cdot \begin{pmatrix} -4 \\ 2 \\ 0 \end{pmatrix} = \frac{1}{9} [1(-4) + 2(2) + 2(0)] = \frac{1}{9} [-4 + 4 + 0] = 0 \quad (\checkmark)
   $$
   Perpendicularity to the plane is confirmed.

---

## 4. Verification and Consistency Checks

1. **Standard Point-to-Plane Distance Formula:**
   $$
   d = \frac{|A x_0 + B y_0 + C z_0 - d|}{\sqrt{A^2 + B^2 + C^2}} = \frac{|1(3) + 2(0) + 2(0) - 4|}{\sqrt{1^2 + 2^2 + 2^2}} = \frac{|3 - 4|}{\sqrt{9}} = \frac{|-1|}{3} = \frac{1}{3} \quad (\checkmark)
   $$
   The analytic distance formula produces the identical result $\frac{1}{3}$.

2. **Minimality Verification (Calculus Check):**
   The squared distance from $P(3, 0, 0)$ to an arbitrary point $(x, y, z)$ on $\Pi$ where $x = 4 - 2y - 2z$ is:
   $$
   f(y, z) = (4 - 2y - 2z - 3)^2 + y^2 + z^2 = (1 - 2y - 2z)^2 + y^2 + z^2
   $$
   Setting partial derivatives to zero:
   - $\frac{\partial f}{\partial y} = -4(1 - 2y - 2z) + 2y = 10y + 8z - 4 = 0$
   - $\frac{\partial f}{\partial z} = -4(1 - 2y - 2z) + 2z = 8y + 10z - 4 = 0$
   By symmetry $y = z \implies 18y = 4 \implies y = \frac{2}{9}, z = \frac{2}{9}$, and $x = 4 - 2(2/9) - 2(2/9) = \frac{28}{9} \quad (\checkmark)$.
