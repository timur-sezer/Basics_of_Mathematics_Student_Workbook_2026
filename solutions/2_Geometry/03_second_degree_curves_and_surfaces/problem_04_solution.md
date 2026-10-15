# Solution to Exercise 4: Parabola

## 1. Problem Statement

Given the canonical equation of the parabola in $\mathbb{R}^2$:
$$
y^2 = 12x
$$

1. Identify the vertex $V$, the axis of symmetry, and the opening direction of the parabola.
2. Find the coordinates of the points on the parabola corresponding to $x = 3$.
3. Determine the focal parameter $p$, the coordinates of the focus $F$, and the equation of the directrix line.

---

## 2. Theoretical Background and Concepts

1. **Canonical Form of a Parabola Opening Horizontally:**
   The standard canonical equation of a parabola with vertex at the origin and horizontal axis of symmetry is:
   $$
   y^2 = 2px
   $$
   where $p > 0$ is the focal parameter (the distance between the focus and the directrix line).

2. **Geometric Properties:**
   - **Vertex:** $V = (0, 0)$.
   - **Axis of Symmetry:** The line $y = 0$ ($x$-axis), because $(-y)^2 = y^2$.
   - **Opening Direction:** Since $p > 0$ and $y^2 \ge 0$, we must have $x = \frac{y^2}{2p} \ge 0$. The curve exists only in the right half-plane ($x \ge 0$), opening to the right.
   - **Focus:** $F = \left(\frac{p}{2}, 0\right)$.
   - **Directrix:** The vertical line $x = -\frac{p}{2}$.
   - **Latus Rectum:** The focal chord perpendicular to the axis of symmetry through $F$ has length $2p$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Vertex, Axis of Symmetry, and Opening Direction

Comparing $y^2 = 12x$ with $y^2 = 2px$:
- $2p = 12 \implies p = 6$
- **Vertex:** The extreme point where $x = 0$ and $y = 0$ is:
  $$
  V = (0, 0)
  $$
- **Axis of Symmetry:**
  Replacing $y$ with $-y$ yields $(-y)^2 = y^2 = 12x$, which leaves the equation unchanged. Thus, the curve is symmetric with respect to the **$x$-axis ($y = 0$)**.
- **Opening Direction:**
  Solving for $x$:
  $$
  x = \frac{y^2}{12}
  $$
  Since $y^2 \ge 0$ for all $y \in \mathbb{R}$, $x \ge 0$ for all real points on the curve. Therefore, the parabola opens towards the **positive $x$-direction (to the right)**.

---

### Step 2: Compute the Points Corresponding to $x = 3$

Substitute $x = 3$ into the equation $y^2 = 12x$:
$$
y^2 = 12(3) = 36
$$
Taking the square root:
$$
y = \pm \sqrt{36} = \pm 6
$$

Thus, the two points on the parabola at $x = 3$ are:
$$
P_1 = (3, 6), \qquad P_2 = (3, -6)
$$

---

### Step 3: Determine the Focus and Directrix

Using the focal parameter $p = 6$:
- Half-parameter distance: $\frac{p}{2} = \frac{6}{2} = 3$.
- **Focus $F$:** Located $\frac{p}{2}$ units along the axis of symmetry from the vertex inside the curve:
  $$
  F = \left(\frac{p}{2}, 0\right) = (3, 0)
  $$
  *(Notice that the points $P_1(3, 6)$ and $P_2(3, -6)$ lie on the vertical line through the focus $x = 3$, meaning the segment $P_1 P_2$ is the latus rectum, with full length $6 - (-6) = 12 = 2p$.)*
- **Directrix Line:** Located $\frac{p}{2}$ units on the opposite side of the vertex:
  $$
  x = -\frac{p}{2} \implies x = -3
  $$

---

### Step 4: Required Geometric Sketch of the Parabola

Below is the sketch of the right-opening parabola $y^2 = 12x$ plotted using the vertex and calculated characteristic points:

```
              y
              ^
            6 |                       * P_1(3, 6)
              |                     .
            4 |                   .
              |                 .
            2 |               .
              |             .
  ------------+-----------+-----------+----------> x
       Directrix|       V(0, 0)     F(3, 0)
         x = -3 | [Axis of Symmetry: y = 0]
           -2 |             .
              |               .
           -4 |                 .
              |                   .
           -6 |                       * P_2(3, -6)
              |
```

*Geometric Features Labeled on the Sketch:*
- **Vertex:** $V(0, 0)$ at the origin.
- **Axis of Symmetry:** The line $y = 0$ ($x$-axis).
- **Plotted Points:** $P_1(3, 6)$ and $P_2(3, -6)$ forming the vertical latus rectum chord through the focus $F(3, 0)$.
- **Directrix:** The vertical line $x = -3$, equidistant from the vertex as the focus.
- **Opening:** The curve strictly opens towards the right ($x \ge 0$) and is symmetric with respect to $y = 0$.

---

## 4. Verification and Consistency Checks

1. **Equidistance Definition Check (Focus vs. Directrix):**
   A parabola is the locus of all points whose distance to the focus equals their distance to the directrix ($d(P, F) = d(P, \text{dir})$).
   Test this geometric definition on point $P_1(3, 6)$:
   - Distance from $P_1(3, 6)$ to focus $F(3, 0)$:
     $$
     d(P_1, F) = \sqrt{(3 - 3)^2 + (6 - 0)^2} = \sqrt{0 + 36} = 6
     $$
   - Distance from $P_1(3, 6)$ to directrix $x = -3$:
     $$
     d(P_1, \text{dir}) = |x_P - (-3)| = |3 - (-3)| = |3 + 3| = 6
     $$
   $$
   d(P_1, F) = d(P_1, \text{dir}) = 6 \quad (\checkmark)
   $$
   The focus-directrix equidistance property holds.

2. **Vertex Equidistance Check:**
   - Distance from $V(0, 0)$ to $F(3, 0)$: $d(V, F) = 3$.
   - Distance from $V(0, 0)$ to line $x = -3$: $d(V, \text{dir}) = 3$.
   Both distances equal $\frac{p}{2} = 3 \quad (\checkmark)$.
