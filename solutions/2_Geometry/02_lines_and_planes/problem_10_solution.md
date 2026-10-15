# Solution to Exercise 10: Projection of a Point onto a Plane

## 1. Problem Statement

Given the point $P = (2, 1, 3)$ in $\mathbb{R}^3$ and the plane $\Pi$ defined by:
$$
\Pi: x + y + z = 3
$$

1. Find the coordinates of the orthogonal projection $P_0$ of point $P$ onto the plane $\Pi$.
2. Find the coordinates of the reflection $P'$ of point $P$ across the plane $\Pi$.
3. Verify that the midpoint of the line segment $PP'$ lies directly on the plane $\Pi$.

---

## 2. Theoretical Background and Concepts

1. **Orthogonal Projection of a Point onto a Plane:**
   The orthogonal projection $P_0$ of a point $P(x_P, y_P, z_P)$ onto a plane $\Pi: Ax + By + Cz = d$ is the foot of the perpendicular line dropped from $P$ onto $\Pi$.
   - The normal line passing through $P$ with direction $n = (A, B, C)$ has the parametric form:
     $$
     L_{\text{norm}}(t) = P + t n = \begin{pmatrix} x_P + t A \\ y_P + t B \\ z_P + t C \end{pmatrix}
     $$
   - Intersecting $L_{\text{norm}}(t)$ with the plane yields the parameter value $t_0$:
     $$
     t_0 = \frac{d - (Ax_P + By_P + Cz_P)}{A^2 + B^2 + C^2} = \frac{d - n \cdot P}{\|n\|^2}
     $$
   - The projection is:
     $$
     P_0 = P + t_0 n
     $$

2. **Specular Reflection Across a Plane:**
   The reflection $P'$ of point $P$ across the plane lies on the same normal line, at an equal distance on the opposite side of the plane:
   $$
   P' = P + 2 t_0 n = 2 P_0 - P
   $$
   By construction, the midpoint of the line segment $PP'$ is identically the projection point $P_0$:
   $$
   M = \frac{P + P'}{2} = P_0
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up the Normal Line Through Point $P$

From the plane $\Pi: x + y + z = 3$, read off the normal vector:
$$
n = \begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix}
$$
The line passing through $P(2, 1, 3)$ perpendicular to $\Pi$ is parameterized by:
$$
\begin{pmatrix} x(t) \\ y(t) \\ z(t) \end{pmatrix} = \begin{pmatrix} 2 \\ 1 \\ 3 \end{pmatrix} + t \begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix} = \begin{pmatrix} 2 + t \\ 1 + t \\ 3 + t \end{pmatrix}
$$

---

### Step 2: Intersect the Normal Line with Plane $\Pi$

Substitute the parametric coordinates into the plane equation $x + y + z = 3$:
$$
(2 + t) + (1 + t) + (3 + t) = 3
$$
Simplify:
$$
6 + 3t = 3 \implies 3t = 3 - 6 = -3 \implies t_0 = -1
$$

---

### Step 3: Compute the Orthogonal Projection $P_0$

Substitute $t_0 = -1$ into the line equations:
- $x = 2 + (-1) = 1$
- $y = 1 + (-1) = 0$
- $z = 3 + (-1) = 2$

Thus, the orthogonal projection is:
$$
P_0 = (1, 0, 2)
$$

Check that $P_0 \in \Pi$:
$$
1 + 0 + 2 = 3 = 3 \quad (\checkmark)
$$

---

### Step 4: Compute the Reflection Point $P'$

Using the double displacement $P' = P + 2t_0 n$ with $t = 2(-1) = -2$:
- $x = 2 + (-2)(1) = 0$
- $y = 1 + (-2)(1) = -1$
- $z = 3 + (-2)(1) = 1$

Alternatively, using $P' = 2P_0 - P$:
$$
P' = 2 \begin{pmatrix} 1 \\ 0 \\ 2 \end{pmatrix} - \begin{pmatrix} 2 \\ 1 \\ 3 \end{pmatrix} = \begin{pmatrix} 2 - 2 \\ 0 - 1 \\ 4 - 3 \end{pmatrix} = \begin{pmatrix} 0 \\ -1 \\ 1 \end{pmatrix}
$$

Thus, the reflection point is:
$$
P' = (0, -1, 1)
$$

---

### Step 5: Verification of the Midpoint on the Plane

Compute the midpoint $M$ of segment $PP'$:
$$
M = \frac{P + P'}{2} = \frac{1}{2} \left[ \begin{pmatrix} 2 \\ 1 \\ 3 \end{pmatrix} + \begin{pmatrix} 0 \\ -1 \\ 1 \end{pmatrix} \right] = \frac{1}{2} \begin{pmatrix} 2 \\ 0 \\ 4 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \\ 2 \end{pmatrix}
$$

Notice that:
$$
M = (1, 0, 2) = P_0
$$

Substitute the coordinates of $M(1, 0, 2)$ into the plane equation $\Pi: x + y + z = 3$:
$$
\text{LHS} = 1 + 0 + 2 = 3 = \text{RHS} \quad (\checkmark)
$$

The midpoint $M$ lies on the plane $\Pi$.

---

## 4. Verification and Consistency Checks

1. **Equidistance Verification ($d(P, \Pi) = d(P', \Pi)$):**
   - Distance from $P(2, 1, 3)$ to $\Pi$:
     $$
     d(P, \Pi) = \frac{|2 + 1 + 3 - 3|}{\sqrt{1^2 + 1^2 + 1^2}} = \frac{3}{\sqrt{3}} = \sqrt{3}
     $$
   - Distance from $P'(0, -1, 1)$ to $\Pi$:
     $$
     d(P', \Pi) = \frac{|0 + (-1) + 1 - 3|}{\sqrt{3}} = \frac{|-3|}{\sqrt{3}} = \frac{3}{\sqrt{3}} = \sqrt{3}
     $$
   Both points are at the exact same distance $\sqrt{3}$ from the plane.

2. **Perpendicularity of $\overrightarrow{PP'}$ to the Plane:**
   $$
   \overrightarrow{PP'} = P' - P = \begin{pmatrix} 0 - 2 \\ -1 - 1 \\ 1 - 3 \end{pmatrix} = \begin{pmatrix} -2 \\ -2 \\ -2 \end{pmatrix} = -2 \begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix} = -2 n \quad (\checkmark)
   $$
   The segment $PP'$ is strictly parallel to the normal vector $n$, confirming that the reflection was executed perpendicular to the plane.
