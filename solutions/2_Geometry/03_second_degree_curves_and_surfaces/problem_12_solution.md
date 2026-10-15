# Solution to Exercise 12: Recognizing a Surface from Cross-Sections

## 1. Problem Statement

A certain second-degree surface in three-dimensional space $\mathbb{R}^3$ possesses the following geometric properties:
1. The horizontal cross-section by the plane $z = 0$ is a **single point**.
2. For all $z > 0$, the horizontal cross-sections by planes $z = \text{const}$ are **circles with strictly increasing radius**.
3. All vertical cross-sections passing through the vertical coordinate axis $Oz$ are **parabolas**.

**Task:**
Propose a simple algebraic equation for such a surface, identify its geometric name, and justify mathematically how each of the three stated conditions is satisfied by the chosen equation.

---

## 2. Theoretical Background and Concepts

1. **Reconstruction of a Surface from Its Cross-Sections:**
   Let a surface have circular horizontal cross-sections centered on the $z$-axis.
   In cylindrical coordinates $(\rho, \theta, z)$ with $\rho = \sqrt{x^2 + y^2}$:
   - Circular cross-sections imply rotational symmetry about the $z$-axis; hence the equation cannot depend on the azimuthal angle $\theta$.
   - The general equation of a surface of revolution around the $z$-axis has the form:
     $$
     x^2 + y^2 = f(z) \iff \rho = \sqrt{f(z)}
     $$
     where $f(z) \ge 0$ defines the square of the radius at height $z$.

2. **Parabolic Vertical Meridian Profiles:**
   A vertical plane passing through the $z$-axis has the form $y = k x$ (or $x = 0$).
   In any such plane, the distance from the $z$-axis is $\rho = \sqrt{x^2 + y^2}$.
   If the intersection curve is a parabola opening along the $z$-axis with vertex at the origin:
   $$
   z = a \rho^2 = a (x^2 + y^2) \quad \text{with } a > 0
   $$
   Equivalently:
   $$
   \rho^2 = f(z) = \frac{z}{a}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Propose the Surface Equation

We propose the simplest canonical equation with scaling factor $a = 1$:
$$
z = x^2 + y^2
$$
*(More generally, $z = a(x^2 + y^2)$ for any fixed real parameter $a > 0$.)*

**Name of the Surface:**
This surface is a **circular paraboloid of revolution** (an elliptic paraboloid with rotational symmetry).

---

### Step 2: Verification of Property 1 (Cross-Section $z = 0$ is a Single Point)

Substitute $z = 0$ into the proposed equation $z = x^2 + y^2$:
$$
0 = x^2 + y^2 \iff x^2 + y^2 = 0
$$

Since $x, y \in \mathbb{R}$, both $x^2 \ge 0$ and $y^2 \ge 0$.
The sum of two non-negative real numbers can equal zero if and only if both numbers are individually zero:
$$
x^2 = 0 \implies x = 0, \qquad y^2 = 0 \implies y = 0
$$
Combining with $z = 0$, the intersection of the surface with the plane $z = 0$ consists solely of the origin:
$$
(x, y, z) = (0, 0, 0)
$$
This confirms that the cross-section $z = 0$ is a **single point** (the vertex/apex of the surface).

---

### Step 3: Verification of Property 2 (Circles of Increasing Radius for $z > 0$)

Consider a horizontal plane at arbitrary height $z = c$ where $c > 0$.
Substitute $z = c$:
$$
x^2 + y^2 = c
$$

Since $c > 0$, we can express $c$ as $(\sqrt{c})^2$:
$$
x^2 + y^2 = (\sqrt{c})^2
$$
1. **Geometric Shape:**
   In the plane $z = c$, this equation defines a **circle** centered at the point $(0, 0, c)$ on the $z$-axis.
2. **Radius Analysis:**
   The radius of the circular cross-section at height $c$ is:
   $$
   R(c) = \sqrt{c}
   $$
   Since the square root function is strictly monotonically increasing for $c > 0$:
   $$
   c_2 > c_1 > 0 \implies R(c_2) = \sqrt{c_2} > \sqrt{c_1} = R(c_1)
   $$
   As height $z = c$ increases, the radius of the circular cross-section strictly increases, satisfying Property 2.

---

### Step 4: Verification of Property 3 (Vertical Cross-Sections Through $Oz$ are Parabolas)

A plane passes through the vertical axis $Oz$ if and only if its equation has the form:
$$
\Pi_\alpha: y = (\tan \alpha) x \quad \text{or} \quad x = 0
$$
where $\alpha \in [0, \pi)$ is the angle the plane makes with the $xz$-plane.

1. **Test for $\alpha = 0$ (the $xz$-plane, $y = 0$):**
   $$
   z = x^2 + 0^2 \implies z = x^2
   $$
   This is a standard parabola opening upwards with vertex at $(0, 0, 0)$.

2. **Test for $\alpha = \frac{\pi}{2}$ (the $yz$-plane, $x = 0$):**
   $$
   z = 0^2 + y^2 \implies z = y^2
   $$
   This is a standard parabola opening upwards with vertex at $(0, 0, 0)$.

3. **General Meridian Plane at Angle $\alpha$:**
   In the plane $\Pi_\alpha$, let $\rho$ denote the radial coordinate distance from the $z$-axis, so $x = \rho \cos \alpha$ and $y = \rho \sin \alpha$.
   Substitute into the surface equation:
   $$
   z = (\rho \cos \alpha)^2 + (\rho \sin \alpha)^2 = \rho^2 (\cos^2 \alpha + \sin^2 \alpha) = \rho^2 \cdot 1
   $$
   $$
   z = \rho^2
   $$
   In the 2D coordinate system $(\rho, z)$ of every meridian plane through the $z$-axis, the intersection curve is the exact same standard parabola $z = \rho^2$. Property 3 is satisfied.

---

## 4. Verification and Consistency Checks

1. **Uniqueness Check (Elimination of Other Candidate Surfaces):**
   - **Circular Cone ($z = \sqrt{x^2 + y^2} \iff z^2 = x^2 + y^2$):**
     Has point cross-section at $z = 0$ and circular cross-sections for $z > 0$, but its vertical slices are straight lines ($z = \pm x$), not parabolas. (Violates Property 3).
   - **Hemisphere ($z = \sqrt{R^2 - x^2 - y^2}$):**
     Has circular slices, but its vertical slices are semicircles, not parabolas. (Violates Property 3).
   - **Circular Paraboloid ($z = x^2 + y^2$):**
     Uniquely satisfies all three geometric conditions.

2. **Quantitative Value Check:**
   - At $z = 1$: Circle of radius $R(1) = \sqrt{1} = 1$.
   - At $z = 4$: Circle of radius $R(4) = \sqrt{4} = 2$.
   - At $z = 9$: Circle of radius $R(9) = \sqrt{9} = 3$.
   In each vertical plane, the points $(1, 0, 1), (2, 0, 4), (3, 0, 9)$ lie on the parabola $z = x^2$.
