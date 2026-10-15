# Solution to Exercise 14: Contrast: Intersection and Parallelism

## 1. Problem Statement

From the point $P = (0, 0, 1)$ in $\mathbb{R}^3$, two straight lines are drawn with direction vectors:
$$
v_1 = (2, 1, -1), \qquad v_2 = (2, 1, 0)
$$

For each line:
1. Analyze its geometric position relative to the horizontal coordinate plane $\Pi: z = 0$ (the $xy$-plane).
2. For the line that intersects the plane, compute the exact coordinates of the intersection point.
3. For the line that is parallel to the plane, explain how parallelism can be recognized immediately by structural inspection without having to solve an algebraic equation.

---

## 2. Theoretical Background and Concepts

1. **The Coordinate Plane $\Pi: z = 0$:**
   The equation $z = 0$ defines the horizontal $xy$-plane.
   - Its normal vector is the standard vertical basis vector:
     $$
     n = (0, 0, 1) = \mathbf{k}
     $$
   - A line $L: X(t) = P + t v$ has vertical coordinate:
     $$
     z(t) = z_P + t v_z
     $$

2. **The Role of the $z$-Component of the Direction Vector:**
   The dot product between a line's direction $v = (v_x, v_y, v_z)$ and the plane normal $n = (0, 0, 1)$ simplifies to:
   $$
   v \cdot n = (v_x)(0) + (v_y)(0) + (v_z)(1) = v_z
   $$
   - If $v_z \ne 0 \implies v \cdot n \ne 0$: The line has a non-zero vertical velocity component. It must eventually cross every horizontal level $z = c$, intersecting the plane $z = 0$ at a unique point.
   - If $v_z = 0 \implies v \cdot n = 0$: The line has zero vertical velocity. The $z$-coordinate is constant for all points ($z(t) \equiv z_P$). The line remains at fixed height $z = z_P$ and is parallel to the plane $z = 0$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Analysis of Line 1 ($v_1 = (2, 1, -1)$)

1. **Parametric Equation of Line 1:**
   Using base point $P(0, 0, 1)$ and direction $v_1 = (2, 1, -1)$:
   $$
   \begin{cases}
   x(t) = 0 + 2t = 2t, \\
   y(t) = 0 + 1t = t, \\
   z(t) = 1 - 1t = 1 - t.
   \end{cases}
   $$

2. **Test Relative Position:**
   Evaluate the dot product with the plane normal $n = (0, 0, 1)$:
   $$
   v_1 \cdot n = (2)(0) + (1)(0) + (-1)(1) = -1 \ne 0
   $$
   Because $v_1 \cdot n \ne 0$, **Line 1 is not parallel to the plane; it intersects the plane $\Pi: z = 0$ at a unique point**.

3. **Compute the Intersection Point:**
   Set the $z$-coordinate equal to $0$:
   $$
   z(t) = 0 \implies 1 - t = 0 \implies t = 1
   $$
   Substitute $t = 1$ into the parametric equations for $x$ and $y$:
   - $x = 2(1) = 2$
   - $y = 1$
   - $z = 1 - 1 = 0$

   The intersection point is:
   $$
   M = (2, 1, 0)
   $$

---

### Step 2: Analysis of Line 2 ($v_2 = (2, 1, 0)$)

1. **Parametric Equation of Line 2:**
   Using base point $P(0, 0, 1)$ and direction $v_2 = (2, 1, 0)$:
   $$
   \begin{cases}
   x(s) = 0 + 2s = 2s, \\
   y(s) = 0 + 1s = s, \\
   z(s) = 1 + 0s = 1.
   \end{cases}
   $$

2. **Test Relative Position:**
   Evaluate the dot product with normal $n = (0, 0, 1)$:
   $$
   v_2 \cdot n = (2)(0) + (1)(0) + (0)(1) = 0
   $$
   Because $v_2 \cdot n = 0$, Line 2 is parallel to the plane.

3. **Check for Intersection:**
   Substitute $z(s) = 1$ into the plane equation $z = 0$:
   $$
   1 = 0 \quad (\text{Contradiction!})
   $$
   The equation has no solutions.
   Therefore, **Line 2 is strictly parallel to the plane $z = 0$ with no intersection points** ($L_2 \cap \Pi = \emptyset$).

---

### Step 3: Recognizing Parallelism Without Solving Equations

One can recognize the parallelism of Line 2 immediately by structural inspection of the coordinates:

1. **Definition of the Plane:**
   The plane $z = 0$ is characterized by having its $z$-coordinate fixed at zero.
2. **Direction Vector Property:**
   The third component of a direction vector $v = (v_x, v_y, v_z)$ represents the rate of change of height $\frac{dz}{dt} = v_z$. For Line 2, $v_z = 0$. This indicates that traversing along Line 2 produces zero vertical displacement.
3. **Height Invariance:**
   Because Line 2 starts at point $P$ with height $z = 1$ and has $v_z = 0$, every single point on Line 2 remains permanently at height $z = 1$. It is completely contained in the parallel plane $z = 1$.
4. **Immediate Deduction:**
   Since $z = 1$ and $z = 0$ are distinct parallel horizontal planes with a constant vertical separation distance of $1$ unit, Line 2 can never reach height $z = 0$. Parallelism is thus established by inspection of the zero in the $z$-coordinate of $v_2$.

---

## 4. Verification and Consistency Checks

1. **Distance Verification for Line 2:**
   Because Line 2 is parallel to $\Pi: z = 0$, every point on Line 2 is at a constant distance from the plane:
   $$
   d(L_2, \Pi) = |z_P - 0| = |1 - 0| = 1 > 0
   $$
   The constant positive distance confirms that no intersection point exists.

2. **Consistency of Intersection Point $M(2, 1, 0)$:**
   - On Line 1 at $t = 1$: $(0, 0, 1) + 1(2, 1, -1) = (2, 1, 0) \quad (\checkmark)$
   - In plane $z = 0$: $z$-coordinate is $0 \quad (\checkmark)$

3. **Angle Comparison:**
   - For Line 1: $\sin \alpha_1 = \frac{|v_1 \cdot n|}{\|v_1\| \|n\|} = \frac{|-1|}{\sqrt{4 + 1 + 1}\sqrt{1}} = \frac{1}{\sqrt{6}} > 0 \implies \alpha_1 \approx 24.09^\circ$ (inclined).
   - For Line 2: $\sin \alpha_2 = \frac{|v_2 \cdot n|}{\|v_2\| \|n\|} = \frac{0}{\sqrt{5}\cdot 1} = 0 \implies \alpha_2 = 0^\circ$ (strictly parallel).
