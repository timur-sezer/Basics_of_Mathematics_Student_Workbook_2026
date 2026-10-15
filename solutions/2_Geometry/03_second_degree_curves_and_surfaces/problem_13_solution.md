# Solution to Exercise 13: Intersection of a Sphere and a Plane

## 1. Problem Statement

Given the sphere $S$ centered at the origin:
$$
S: x^2 + y^2 + z^2 = 25
$$
and the horizontal plane $\Pi$:
$$
\Pi: z = 3
$$

1. Find the Cartesian equation of the curve formed by the intersection $S \cap \Pi$ and calculate its radius.
2. Analyze the general intersection between the sphere and a horizontal plane $z = c$ as the parameter $c \in \mathbb{R}$ varies, identifying all qualitatively distinct geometric cases.

---

## 2. Theoretical Background and Concepts

1. **Intersection of a Sphere with a Plane:**
   In three dimensions, the intersection of a sphere of radius $R$ centered at $S_0$ with a plane $\Pi$ depends strictly on the Euclidean distance $d = d(S_0, \Pi)$ from the sphere's center to the plane:
   - **Case 1: $d < R$ (Secant Plane)**
     The plane cuts through the sphere. The intersection is a **circle** of radius:
     $$
     r = \sqrt{R^2 - d^2}
     $$
     The center of this intersection circle is the orthogonal projection of $S_0$ onto $\Pi$.
   - **Case 2: $d = R$ (Tangent Plane)**
     The plane touches the sphere at **exactly one point** (the point of tangency).
   - **Case 3: $d > R$ (Disjoint Plane)**
     The plane lies entirely outside the sphere. The intersection is the **empty set** $\emptyset$.

2. **Pythagorean Relation for Spherical Slices:**
   For a sphere centered at the origin, the distance to the horizontal plane $z = c$ is simply $d = |c|$. In the plane $z = c$, the radius $r$ of the cross-section, the height $c$, and the sphere's radius $R$ form a right-angled triangle with hypotenuse $R$:
   $$
   r^2 + c^2 = R^2 \implies r = \sqrt{R^2 - c^2}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Intersection with the Specific Plane $z = 3$

1. **Substitute $z = 3$ into the sphere's equation:**
   $$
   x^2 + y^2 + 3^2 = 25
   $$
   Evaluate the square:
   $$
   x^2 + y^2 + 9 = 25
   $$
   Subtract $9$ from both sides:
   $$
   x^2 + y^2 = 25 - 9 = 16
   $$

2. **Characterize the Intersection Curve:**
   The intersection curve is described in space by the system:
   $$
   \begin{cases}
   x^2 + y^2 = 16, \\
   z = 3.
   \end{cases}
   $$
   - **Geometric Nature:** A **circle** lying in the horizontal plane $z = 3$.
   - **Center of the Circle:** $C_3 = (0, 0, 3)$.
   - **Radius of the Circle:**
     $$
     r = \sqrt{16} = 4
     $$

---

### Step 2: General Analysis of the Intersection for $z = c$

Substitute an arbitrary height $z = c$ ($c \in \mathbb{R}$) into the sphere equation:
$$
x^2 + y^2 + c^2 = 25 \implies x^2 + y^2 = 25 - c^2
$$

The behavior of the solution set in the plane $z = c$ is governed by the sign of $25 - c^2$:

#### Case A: $|c| < 5$ (i.e., $-5 < c < 5$)
- The term $25 - c^2 > 0$ is strictly positive.
- The intersection is a **circle** lying in the plane $z = c$ with:
  - Center: $(0, 0, c)$
  - Radius:
    $$
    r(c) = \sqrt{25 - c^2}
    $$
- **Variation with $c$:**
  - The maximum radius occurs at the equator ($c = 0$), where $r(0) = \sqrt{25} = 5 = R$ (a great circle).
  - As $|c|$ increases towards $5$, the radius $r(c)$ strictly decreases towards zero.

#### Case B: $|c| = 5$ (i.e., $c = 5$ or $c = -5$)
- The term $25 - c^2 = 25 - 25 = 0$.
- The equation becomes:
  $$
  x^2 + y^2 = 0 \implies x = 0, \quad y = 0
  $$
- The plane is **tangent to the sphere**, and the intersection consists of a **single point**:
  - For $c = +5$: the North Pole $(0, 0, 5)$.
  - For $c = -5$: the South Pole $(0, 0, -5)$.

#### Case C: $|c| > 5$ (i.e., $c > 5$ or $c < -5$)
- The term $25 - c^2 < 0$ is negative.
- The equation $x^2 + y^2 = 25 - c^2 < 0$ has no real solutions because $x^2 + y^2 \ge 0$ for all $(x, y) \in \mathbb{R}^2$.
- The intersection is the **empty set** $\emptyset$. The plane does not intersect the sphere.

---

## 4. Verification and Consistency Checks

1. **Pythagorean Theorem Check for Point on the Circle:**
   Choose a point on the circle $z = 3$, for instance $(4, 0, 3)$:
   - Distance from origin to $(4, 0, 3)$:
     $$
     d = \sqrt{4^2 + 0^2 + 3^2} = \sqrt{16 + 0 + 9} = \sqrt{25} = 5
     $$
   Since $d = R = 5$, the point lies exactly on the sphere surface ($\checkmark$).

2. **Summary Matrix of Parametric Slices:**

| Parameter Range | Algebraic Expression | Geometric Result | Center of Locus | Radius $r(c)$ |
| :--- | :--- | :--- | :--- | :--- |
| **$c = 0$** | $x^2 + y^2 = 25$ | Equatorial Great Circle | $(0, 0, 0)$ | $r = 5$ (Maximum) |
| **$|c| < 5$** (e.g. $c=3$) | $x^2 + y^2 = 25 - c^2 > 0$ | Small Circle | $(0, 0, c)$ | $r = \sqrt{25 - c^2}$ |
| **$|c| = 5$** | $x^2 + y^2 = 0$ | Tangency Point (Poles) | $(0, 0, \pm 5)$ | $r = 0$ (Degenerate) |
| **$|c| > 5$** | $x^2 + y^2 = 25 - c^2 < 0$ | Empty Set $\emptyset$ | None | Undefined |
