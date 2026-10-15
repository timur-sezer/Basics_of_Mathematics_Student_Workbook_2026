# Solution to Exercise 10: Triangle Area from Vectors

## 1. Problem Statement

Given the three points in $\mathbb{R}^3$ forming a triangle:
$$
A = (0, 0, 0), \qquad B = (2, 1, 0), \qquad C = (1, 3, 2)
$$

1. Construct the edge vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$.
2. Compute the cross product $\overrightarrow{AB} \times \overrightarrow{AC}$ and use its magnitude to determine the area of the parallelogram spanned by these vectors.
3. Compute the area of the triangle $\triangle ABC$.
4. Explain clearly why the factor $\frac{1}{2}$ appears in the triangle area formula.

---

## 2. Theoretical Background and Concepts

1. **Geometric Interpretation of the Cross Product Magnitude:**
   The magnitude of the cross product of two vectors $u, v \in \mathbb{R}^3$ is given by:
   $$
   \|u \times v\| = \|u\| \, \|v\| \sin \theta
   $$
   where $\theta \in [0, \pi]$ is the angle between $u$ and $v$.
   - Geometrically, if $u$ is chosen as the base of a parallelogram, its length is $b = \|u\|$.
   - The corresponding altitude (height) perpendicular to the base is $h = \|v\| \sin \theta$.
   - Consequently, the product $\|u \times v\| = b \cdot h$ equals the **area of the parallelogram** spanned by $u$ and $v$.

2. **Area of a Triangle:**
   Any triangle $\triangle ABC$ sharing vertex $A$ is half of the parallelogram formed by vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$:
   $$
   \operatorname{Area}(\triangle ABC) = \frac{1}{2} \|\overrightarrow{AB} \times \overrightarrow{AC}\|
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Construct Vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$

Subtract the coordinates of vertex $A(0, 0, 0)$ from $B(2, 1, 0)$ and $C(1, 3, 2)$:
$$
\overrightarrow{AB} = B - A = \begin{pmatrix} 2 - 0 \\ 1 - 0 \\ 0 - 0 \end{pmatrix} = \begin{pmatrix} 2 \\ 1 \\ 0 \end{pmatrix}
$$
$$
\overrightarrow{AC} = C - A = \begin{pmatrix} 1 - 0 \\ 3 - 0 \\ 2 - 0 \end{pmatrix} = \begin{pmatrix} 1 \\ 3 \\ 2 \end{pmatrix}
$$

In row notation:
$$
\overrightarrow{AB} = (2, 1, 0), \qquad \overrightarrow{AC} = (1, 3, 2)
$$

---

### Step 2: Compute Cross Product and Parallelogram Area

Set up the determinant:
$$
\overrightarrow{AB} \times \overrightarrow{AC} = \det \begin{pmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 2 & 1 & 0 \\ 1 & 3 & 2 \end{pmatrix}
$$

Expand along the top row:
$$
\overrightarrow{AB} \times \overrightarrow{AC} = \mathbf{i} \det \begin{pmatrix} 1 & 0 \\ 3 & 2 \end{pmatrix} - \mathbf{j} \det \begin{pmatrix} 2 & 0 \\ 1 & 2 \end{pmatrix} + \mathbf{k} \det \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix}
$$

Evaluate each component:
- $\mathbf{i}$-component: $(1)(2) - (0)(3) = 2 - 0 = 2$
- $\mathbf{j}$-component: $-[(2)(2) - (0)(1)] = -(4 - 0) = -4$
- $\mathbf{k}$-component: $(2)(3) - (1)(1) = 6 - 1 = 5$

Thus, the cross product vector is:
$$
\overrightarrow{AB} \times \overrightarrow{AC} = (2, -4, 5)
$$

**Area of the Parallelogram:**
Compute the Euclidean norm of this cross product:
$$
\operatorname{Area}_{\text{parallelogram}} = \|\overrightarrow{AB} \times \overrightarrow{AC}\| = \sqrt{2^2 + (-4)^2 + 5^2} = \sqrt{4 + 16 + 25} = \sqrt{45} = 3\sqrt{5}
$$
Numerically:
$$
\operatorname{Area}_{\text{parallelogram}} = 3\sqrt{5} \approx 6.7082
$$

---

### Step 3: Compute the Area of Triangle $\triangle ABC$

Multiply the parallelogram area by $\frac{1}{2}$:
$$
\operatorname{Area}(\triangle ABC) = \frac{1}{2} \|\overrightarrow{AB} \times \overrightarrow{AC}\| = \frac{\sqrt{45}}{2} = \frac{3\sqrt{5}}{2} \approx 3.3541
$$

---

### Step 4: Geometric Explanation of the Factor $\frac{1}{2}$

1. **Parallelogram Bisection:**
   - Consider the parallelogram defined by vertices $A$, $B$, $D$, and $C$, where $\overrightarrow{AD} = \overrightarrow{AB} + \overrightarrow{AC}$.
   - The line segment $BC$ is a diagonal of this parallelogram.
   - Any diagonal of a parallelogram divides it into two congruent triangles ($\triangle ABC \cong \triangle DCB$).
2. **Equivalence of Areas:**
   - Because the two triangles are geometrically congruent, they have identical areas.
   - The total area of the parallelogram is the sum of the areas of the two triangles:
     $$
     \operatorname{Area}_{\text{parallelogram}} = \operatorname{Area}(\triangle ABC) + \operatorname{Area}(\triangle DCB) = 2 \cdot \operatorname{Area}(\triangle ABC)
     $$
   - Solving for the triangle's area yields:
     $$
     \operatorname{Area}(\triangle ABC) = \frac{1}{2} \operatorname{Area}_{\text{parallelogram}}
     $$
   - This exact halving of the base $\times$ height product is the fundamental reason the scalar factor $\frac{1}{2}$ is required.

---

## 4. Verification and Consistency Checks

1. **Orthogonality Check for Normal Vector $(2, -4, 5)$:**
   - $(2, -4, 5) \cdot \overrightarrow{AB} = (2)(2) + (-4)(1) + (5)(0) = 4 - 4 + 0 = 0 \quad (\checkmark)$
   - $(2, -4, 5) \cdot \overrightarrow{AC} = (2)(1) + (-4)(3) + (5)(2) = 2 - 12 + 10 = 0 \quad (\checkmark)$

2. **Lagrange's Identity and Hero's Alternative Check:**
   - $\|\overrightarrow{AB}\|^2 = 2^2 + 1^2 + 0^2 = 5$
   - $\|\overrightarrow{AC}\|^2 = 1^2 + 3^2 + 2^2 = 14$
   - $\overrightarrow{AB} \cdot \overrightarrow{AC} = 2(1) + 1(3) + 0(2) = 5$
   - $\|\overrightarrow{AB} \times \overrightarrow{AC}\|^2 = \|\overrightarrow{AB}\|^2 \|\overrightarrow{AC}\|^2 - (\overrightarrow{AB} \cdot \overrightarrow{AC})^2 = (5)(14) - 5^2 = 70 - 25 = 45$
   - Taking the square root gives $\sqrt{45} = 3\sqrt{5}$, and dividing by $2$ confirms $\frac{3\sqrt{5}}{2} \quad (\checkmark)$.
