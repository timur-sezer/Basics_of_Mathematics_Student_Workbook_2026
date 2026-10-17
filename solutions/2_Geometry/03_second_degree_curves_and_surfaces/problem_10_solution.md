# Solution to Exercise 10: Paraboloids

## 1. Problem Statement

Compare the two fundamental types of paraboloids in $\mathbb{R}^3$:
$$
\text{Surface 1: } z = x^2 + y^2, \qquad \text{Surface 2: } z = x^2 - y^2
$$

1. For each surface, describe and classify the planar cross-sections obtained by slicing with:
   - The coordinate plane $x = 0$,
   - The coordinate plane $y = 0$,
   - Horizontal planes $z = c$ for various values of $c$ ($c > 0$, $c = 0$, and $c < 0$).
2. Based on these cross-sections, identify the specific geometric type of each paraboloid.
3. Compare the qualitative shapes and topography of the two surfaces.

---

## 2. Theoretical Background and Concepts

1. **Classification of Paraboloids:**
   Paraboloids are non-central quadric surfaces characterized by having exactly one variable appear to the first power while the remaining two variables appear quadratically:
   - **Elliptic (Circular) Paraboloid:** $z = \frac{x^2}{a^2} + \frac{y^2}{b^2}$. Both quadratic terms have the same sign. All vertical cross-sections are parabolas opening in the same direction, and horizontal slices are ellipses (or circles when $a = b$).
   - **Hyperbolic Paraboloid:** $z = \frac{x^2}{a^2} - \frac{y^2}{b^2}$. The quadratic terms have opposite signs. Vertical cross-sections in orthogonal directions are parabolas opening in opposite directions, while horizontal slices are hyperbolas (degenerating to a pair of intersecting lines at $z = 0$). It is a classic doubly-ruled saddle surface.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Cross-Sectional Analysis of Surface 1 ($z = x^2 + y^2$)

1. **Cross-Section by $x = 0$ (the $yz$-plane):**
   $$
   z = 0^2 + y^2 \implies z = y^2
   $$
   This is a **standard parabola** in the $yz$-plane with vertex at the origin $(0, 0, 0)$, symmetric about the $z$-axis, and opening upwards towards positive $z$.

2. **Cross-Section by $y = 0$ (the $xz$-plane):**
   $$
   z = x^2 + 0^2 \implies z = x^2
   $$
   This is a **standard parabola** in the $xz$-plane with vertex at $(0, 0, 0)$, symmetric about the $z$-axis, and opening upwards towards positive $z$.

3. **Horizontal Cross-Sections $z = c$:**
   $$
   x^2 + y^2 = c
   $$
   - **Case $c > 0$:**
     $x^2 + y^2 = c = (\sqrt{c})^2$ is a **circle** of radius $r = \sqrt{c}$ centered on the $z$-axis at $(0, 0, c)$. As height $z = c$ increases, the radius expands proportional to $\sqrt{c}$.
   - **Case $c = 0$:**
     $x^2 + y^2 = 0 \implies (x, y) = (0, 0)$. The cross-section is the **single point** $(0, 0, 0)$, which is the global minimum (vertex) of the surface.
   - **Case $c < 0$:**
     $x^2 + y^2 = c < 0$. Since a sum of real squares cannot be negative, there are no real points (**empty set** $\emptyset$). The surface does not exist below the $xy$-plane.

**Geometric Identification:**
Surface 1 is a **circular paraboloid of revolution** (an elliptic paraboloid with rotational symmetry about the $z$-axis). Its shape resembles an open, rotationally symmetric bowl.

---

### Step 2: Cross-Sectional Analysis of Surface 2 ($z = x^2 - y^2$)

1. **Cross-Section by $x = 0$ (the $yz$-plane):**
   $$
   z = 0^2 - y^2 \implies z = -y^2
   $$
   This is a **parabola** in the $yz$-plane with vertex at $(0, 0, 0)$, but it **opens downwards** towards negative $z$.

2. **Cross-Section by $y = 0$ (the $xz$-plane):**
   $$
   z = x^2 - 0^2 \implies z = x^2
   $$
   This is a **parabola** in the $xz$-plane with vertex at $(0, 0, 0)$, and it **opens upwards** towards positive $z$.

3. **Horizontal Cross-Sections $z = c$:**
   $$
   x^2 - y^2 = c
   $$
   - **Case $c > 0$:**
     $\frac{x^2}{c} - \frac{y^2}{c} = 1$ is an **equilateral hyperbola** with real axis along the $x$-direction, vertices at $(\pm\sqrt{c}, 0, c)$, and asymptotes $y = \pm x$.
   - **Case $c = 0$:**
     $x^2 - y^2 = 0 \iff (x - y)(x + y) = 0$.
     This is a **pair of straight lines** $y = x$ and $y = -x$ intersecting at the origin in the plane $z = 0$.
   - **Case $c < 0$:**
     Multiply by $-1$: $y^2 - x^2 = -c > 0$, or $\frac{y^2}{|c|} - \frac{x^2}{|c|} = 1$.
     This is an **equilateral hyperbola** whose transverse axis has rotated by $90^\circ$ to lie along the $y$-direction, with vertices at $(0, \pm\sqrt{|c|}, c)$ and asymptotes $y = \pm x$.

**Geometric Identification:**
Surface 2 is a **hyperbolic paraboloid** (commonly called a **saddle surface**).

---

### Step 4: Required Qualitative Sketches of Both Surfaces

#### 1. Circular Paraboloid (Bowl): $z = x^2 + y^2$
```
                    z
                    ^
                    |      .---.  z = c (Circular Trace)
                \   |   / (     )
                 \  |  /   '---'
                  \ | /
                   \|/
  ------------------+------------------> y
                   /|  Origin (0,0,0)
                  / |  [Local & Global Min]
                 v
                 x
```
*Labels:* Vertical axis of rotational symmetry $z$; upward-opening parabolic vertical traces $z = x^2$ ($y=0$) and $z = y^2$ ($x=0$); horizontal circular level slices $x^2 + y^2 = c$ ($c > 0$); vertex at $(0, 0, 0)$.

#### 2. Hyperbolic Paraboloid (Saddle): $z = x^2 - y^2$
```
                         z
                         ^   Trace in plane y = 0: z = x^2 (bends UPWARD)
                \        |        /
                 \       |       /
                  \      |      /
   ----------------\-----+-----/------------------> y (axis)
                  .   (0,0,0)   .
                /     [Origin]    \
              /       [Saddle]      \
            /            |            \  Trace in plane x = 0: z = -y^2 (bends DOWNWARD)
          v
          x (axis)
```
*Labels:* Coordinate axes $x, y, z$ meeting at the origin $(0, 0, 0)$; upward-opening parabolic trace $z = x^2$ in the vertical plane $y = 0$ ($xz$-plane); downward-opening parabolic trace $z = -y^2$ in the vertical plane $x = 0$ ($yz$-plane); common vertex at $(0, 0, 0)$ serving as a saddle point (min in $x$, max in $y$).

---

## 4. Verification and Consistency Checks

1. **Rotational Symmetry of Surface 1:**
   In cylindrical coordinates $x = r \cos \theta, y = r \sin \theta, z = z$:
   $$
   z = r^2 \cos^2 \theta + r^2 \sin^2 \theta = r^2
   $$
   The absence of the angular variable $\theta$ rigorously confirms that Surface 1 is invariant under any rotation about the $z$-axis.

2. **Doubly-Ruled Geometry of Surface 2:**
   Every point on $z = x^2 - y^2$ can be generated by straight lines lying entirely on the surface. Factoring the algebraic form $z = (x - y)(x + y)$ reveals **two distinct families of straight lines (rulings)**:
   - **First Ruling Family ($\mathcal{L}_1$ for parameter $u \in \mathbb{R}$):**
     $$
     \mathcal{L}_1(u): \begin{cases} x - y = u \\ z = u(x + y) \end{cases} \implies z = (x - y)(x + y) = u(x + y) \quad (\checkmark)
     $$
   - **Second Ruling Family ($\mathcal{L}_2$ for parameter $v \in \mathbb{R}$):**
     $$
     \mathcal{L}_2(v): \begin{cases} x + y = v \\ z = v(x - y) \end{cases} \implies z = (x + y)(x - y) = v(x - y) \quad (\checkmark)
     $$
   Through every point $(x_0, y_0, z_0)$ on the hyperbolic paraboloid, there pass exactly two straight lines lying entirely within the surface (one from family $\mathcal{L}_1$ with $u = x_0 - y_0$, and one from family $\mathcal{L}_2$ with $v = x_0 + y_0$), rigorously confirming that it is a **doubly-ruled surface**.
