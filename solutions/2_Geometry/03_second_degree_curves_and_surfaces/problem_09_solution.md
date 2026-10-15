# Solution to Exercise 9: Ellipsoid and Its Cross-Sections

## 1. Problem Statement

Given the canonical equation of the ellipsoid in $\mathbb{R}^3$:
$$
\frac{x^2}{9} + \frac{y^2}{4} + \frac{z^2}{16} = 1
$$

1. Determine the lengths of the three semiaxes and the corresponding full axis lengths.
2. Describe the geometry of the equatorial horizontal cross-section obtained by slicing with the plane $z = 0$.
3. Analyze how the horizontal cross-sections $z = c$ change as the parameter $c$ varies within the interval $|c| < 4$.
4. State the geometric behavior at the boundary values $c = \pm 4$ and for $|c| > 4$.

---

## 2. Theoretical Background and Concepts

1. **Canonical Form of a Triaxial Ellipsoid:**
   An ellipsoid centered at the origin whose principal axes coincide with the Cartesian coordinate axes has the equation:
   $$
   \frac{x^2}{a^2} + \frac{y^2}{b^2} + \frac{z^2}{c_0^2} = 1
   $$
   where $a, b, c_0 > 0$ denote the lengths of the semiaxes along the $x$-, $y$-, and $z$-axes, respectively.

2. **The Method of Slicing (Planar Cross-Sections):**
   To visualize and rigorously understand a 3D surface, one intersects it with a family of parallel planes. Slicing with horizontal planes $z = c$ yields:
   $$
   \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1 - \frac{c^2}{c_0^2}
   $$
   - If $1 - \frac{c^2}{c_0^2} > 0$ (i.e., $|c| < c_0$): The cross-section is an **ellipse** in the plane $z = c$.
   - If $1 - \frac{c^2}{c_0^2} = 0$ (i.e., $|c| = c_0$): The cross-section degenerates into a **single point** (the poles).
   - If $1 - \frac{c^2}{c_0^2} < 0$ (i.e., $|c| > c_0$): The cross-section is the **empty set** $\emptyset$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify Semiaxis Lengths

Comparing the given equation:
$$
\frac{x^2}{9} + \frac{y^2}{4} + \frac{z^2}{16} = 1 \iff \frac{x^2}{3^2} + \frac{y^2}{2^2} + \frac{z^2}{4^2} = 1
$$
with standard form:
- **Semiaxis along the $x$-axis:** $a = \sqrt{9} = 3$ (Full axis length: $2a = 6$)
- **Semiaxis along the $y$-axis:** $b = \sqrt{4} = 2$ (Full axis length: $2b = 4$)
- **Semiaxis along the $z$-axis:** $c_0 = \sqrt{16} = 4$ (Full axis length: $2c_0 = 8$)

The ellipsoid is triaxial, with the longest principal axis aligned vertically along the $z$-axis ($c_0 = 4 > a = 3 > b = 2$).

---

### Step 2: Describe the Cross-Section by the Plane $z = 0$

Substitute $z = 0$ into the equation:
$$
\frac{x^2}{9} + \frac{y^2}{4} + \frac{0^2}{16} = 1 \implies \frac{x^2}{9} + \frac{y^2}{4} = 1
$$

In the plane $z = 0$ (the $xy$-plane), this is the **equatorial ellipse**:
- Center: $(0, 0, 0)$
- Major semiaxis along $x$: $a = 3$ (vertices at $(\pm 3, 0, 0)$)
- Minor semiaxis along $y$: $b = 2$ (vertices at $(0, \pm 2, 0)$)
- This cross-section represents the maximum horizontal footprint of the ellipsoid.

---

### Step 3: Analyze the Family of Horizontal Cross-Sections $z = c$ for $|c| < 4$

Substitute $z = c$ where $|c| < 4$:
$$
\frac{x^2}{9} + \frac{y^2}{4} + \frac{c^2}{16} = 1 \implies \frac{x^2}{9} + \frac{y^2}{4} = 1 - \frac{c^2}{16}
$$

Let $k(c) = 1 - \frac{c^2}{16}$. Since $|c| < 4$, $0 < k(c) \le 1$.
Divide both sides by $k(c)$:
$$
\frac{x^2}{9\left(1 - \frac{c^2}{16}\right)} + \frac{y^2}{4\left(1 - \frac{c^2}{16}\right)} = 1
$$

Writing as standard ellipse semiaxes:
$$
\frac{x^2}{a(c)^2} + \frac{y^2}{b(c)^2} = 1
$$
where:
$$
a(c) = 3\sqrt{1 - \frac{c^2}{16}}, \qquad b(c) = 2\sqrt{1 - \frac{c^2}{16}}
$$

**Properties of the Slices:**
1. **Geometric Similarity:**
   For every height $c \in (-4, 4)$, the ratio of the semiaxes remains strictly constant:
   $$
   \frac{a(c)}{b(c)} = \frac{3\sqrt{1 - c^2/16}}{2\sqrt{1 - c^2/16}} = \frac{3}{2} = 1.5
   $$
   All horizontal cross-sections are **mutually similar ellipses** with the exact same eccentricity $\varepsilon = \frac{\sqrt{a(c)^2 - b(c)^2}}{a(c)} = \frac{\sqrt{9 - 4}}{3} = \frac{\sqrt{5}}{3}$.
2. **Monotonic Shrinking:**
   As $|c|$ increases from $0$ towards $4$, the scaling factor $\sqrt{1 - c^2/16}$ decreases continuously from $1$ to $0$. The cross-sectional ellipses shrink smoothly as one moves upwards or downwards from the equator.

---

### Step 4: Behavior at the Boundary and Beyond

1. **At $c = \pm 4$:**
   $$
   \frac{x^2}{9} + \frac{y^2}{4} = 1 - \frac{(\pm 4)^2}{16} = 1 - 1 = 0 \implies \frac{x^2}{9} + \frac{y^2}{4} = 0
   $$
   Since both terms are non-negative, the only real solution is $x = 0$ and $y = 0$.
   The cross-section degenerates into a **single point**:
   - North pole: $(0, 0, 4)$
   - South pole: $(0, 0, -4)$
   The planes $z = 4$ and $z = -4$ are tangent planes to the ellipsoid.

2. **For $|c| > 4$:**
   $$
   \frac{x^2}{9} + \frac{y^2}{4} = 1 - \frac{c^2}{16} < 0
   $$
   Because a sum of real squares cannot be negative, there are no real points. The cross-section is the **empty set** $\emptyset$.

---

## 4. Verification and Consistency Checks

1. **Volume Consistency Check:**
   The volume of a canonical ellipsoid is $V = \frac{4}{3}\pi a b c_0$:
   $$
   V = \frac{4}{3}\pi (3)(2)(4) = 32\pi \approx 100.53
   $$
   Integrating the area of cross-sections $A(c) = \pi a(c) b(c) = \pi (3)(2)\left(1 - \frac{c^2}{16}\right) = 6\pi\left(1 - \frac{c^2}{16}\right)$:
   $$
   V = \int_{-4}^{4} 6\pi\left(1 - \frac{c^2}{16}\right) dc = 12\pi \left[ c - \frac{c^3}{48} \right]_0^4 = 12\pi \left( 4 - \frac{64}{48} \right) = 12\pi \left( 4 - \frac{4}{3} \right) = 12\pi \left(\frac{8}{3}\right) = 32\pi \quad (\checkmark)
   $$
   Integration confirms the cross-sectional area distribution.

2. **Cross-Section Check at $c = 2$ ($z = 2$):**
   - $k(2) = 1 - \frac{2^2}{16} = 1 - \frac{4}{16} = \frac{3}{4} = 0.75$.
   - $a(2) = 3\sqrt{3/4} = \frac{3\sqrt{3}}{2} \approx 2.598$.
   - $b(2) = 2\sqrt{3/4} = \sqrt{3} \approx 1.732$.
   - Test point on the slice: $(x, y, z) = \left(\frac{3\sqrt{3}}{2}, 0, 2\right)$:
     $$
     \frac{(3\sqrt{3}/2)^2}{9} + 0 + \frac{2^2}{16} = \frac{27/4}{9} + \frac{4}{16} = \frac{3}{4} + \frac{1}{4} = 1 \quad (\checkmark)
     $$
