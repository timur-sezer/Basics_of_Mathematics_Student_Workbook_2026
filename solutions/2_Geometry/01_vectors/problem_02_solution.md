# Solution to Exercise 2: Distance as the Length of a Vector

## 1. Problem Statement

Given the two points in three-dimensional Euclidean space $\mathbb{R}^3$:
$$
A = (1, 2, 3), \qquad B = (4, -2, 6)
$$

1. Construct the displacement vector $\overrightarrow{AB}$.
2. Compute the Euclidean length (norm) of the vector $\|\overrightarrow{AB}\|$.
3. Compute the distance $d(A, B)$ between points $A$ and $B$ using the coordinate distance formula.
4. Explain why both calculations yield the exact same numerical result from a conceptual perspective.

---

## 2. Theoretical Background and Concepts

1. **Displacement Vector Connecting Two Points:**
   In an affine-Euclidean space, the directed segment from point $A(x_A, y_A, z_A)$ to point $B(x_B, y_B, z_B)$ is given by the difference between their respective position vectors $\mathbf{r}_B$ and $\mathbf{r}_A$:
   $$
   \overrightarrow{AB} = \mathbf{r}_B - \mathbf{r}_A = (x_B - x_A, y_B - y_A, z_B - z_A)
   $$

2. **Euclidean Norm (Length of a Vector):**
   For any vector $\mathbf{v} = (v_1, v_2, v_3) \in \mathbb{R}^3$, its Euclidean norm is defined as the square root of the dot product with itself:
   $$
   \|\mathbf{v}\| = \sqrt{\mathbf{v} \cdot \mathbf{v}} = \sqrt{v_1^2 + v_2^2 + v_3^2}
   $$

3. **Euclidean Distance Metric:**
   The standard distance metric $d(A, B)$ on $\mathbb{R}^3$ is derived from the Pythagorean theorem applied across the three mutually perpendicular coordinate axes:
   $$
   d(A, B) = \sqrt{(x_B - x_A)^2 + (y_B - y_A)^2 + (z_B - z_A)^2}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Construct the Vector $\overrightarrow{AB}$

Subtract the coordinates of initial point $A$ from terminal point $B$:
$$
\overrightarrow{AB} = B - A = \begin{pmatrix} 4 - 1 \\ -2 - 2 \\ 6 - 3 \end{pmatrix} = \begin{pmatrix} 3 \\ -4 \\ 3 \end{pmatrix}
$$

In row notation:
$$
\overrightarrow{AB} = (3, -4, 3)
$$

---

### Step 2: Compute the Length of $\overrightarrow{AB}$

Apply the Euclidean norm definition:
$$
\|\overrightarrow{AB}\| = \sqrt{v_x^2 + v_y^2 + v_z^2}
$$
Substitute the components $(3, -4, 3)$:
$$
\|\overrightarrow{AB}\| = \sqrt{3^2 + (-4)^2 + 3^2} = \sqrt{9 + 16 + 9} = \sqrt{34}
$$

Approximating to four decimal places:
$$
\|\overrightarrow{AB}\| = \sqrt{34} \approx 5.8310
$$

---

### Step 3: Compute Distance Using the Coordinate Formula

Substitute the coordinates of points $A(1, 2, 3)$ and $B(4, -2, 6)$ directly into the distance formula:
$$
d(A, B) = \sqrt{(x_B - x_A)^2 + (y_B - y_A)^2 + (z_B - z_A)^2}
$$
$$
d(A, B) = \sqrt{(4 - 1)^2 + (-2 - 2)^2 + (6 - 3)^2} = \sqrt{3^2 + (-4)^2 + 3^2}
$$
$$
d(A, B) = \sqrt{9 + 16 + 9} = \sqrt{34} \approx 5.8310
$$

---

### Step 4: Conceptual Explanation of Why the Results Agree

The two calculations produce the exact same mathematical value because **the Euclidean distance formula is by definition the norm of the difference vector**:

1. **Identification of Metric and Norm:**
   In Euclidean space $\mathbb{R}^n$, the metric $d: \mathbb{R}^n \times \mathbb{R}^n \to \mathbb{R}$ is translation-invariant and induced directly by the norm:
   $$
   d(A, B) := \|\mathbf{r}_B - \mathbf{r}_A\|
   $$
2. **Translation to the Origin:**
   The displacement vector $\overrightarrow{AB} = (3, -4, 3)$ translates the geometric segment joining $A$ and $B$ so that its initial point is positioned at the coordinate origin $(0, 0, 0)$. Because Euclidean distance is invariant under rigid translations, the distance from $A$ to $B$ equals the distance from the origin $(0, 0, 0)$ to the point $(3, -4, 3)$.
3. **Application of the 3D Pythagorean Theorem:**
   Both formulas compute the length of the spatial diagonal of a rectangular cuboid with side lengths $|\Delta x| = 3$, $|\Delta y| = 4$, and $|\Delta z| = 3$. Hence, they are two expressions of the exact same geometric property.

---

## 4. Verification and Consistency Checks

1. **Symmetry Property Check ($d(A, B) = d(B, A)$):**
   Construct $\overrightarrow{BA} = A - B$:
   $$
   \overrightarrow{BA} = \begin{pmatrix} 1 - 4 \\ 2 - (-2) \\ 3 - 6 \end{pmatrix} = \begin{pmatrix} -3 \\ 4 \\ -3 \end{pmatrix}
   $$
   Compute its norm:
   $$
   \|\overrightarrow{BA}\| = \sqrt{(-3)^2 + 4^2 + (-3)^2} = \sqrt{9 + 16 + 9} = \sqrt{34}
   $$
   Since $\|\overrightarrow{BA}\| = \|-\overrightarrow{AB}\| = |-1| \cdot \|\overrightarrow{AB}\| = \sqrt{34}$, symmetry is verified.

2. **Pythagorean Step-by-Step Plane Projection Check:**
   - In the $xy$-plane, the projected length is $\ell_{xy} = \sqrt{3^2 + (-4)^2} = \sqrt{9 + 16} = \sqrt{25} = 5$.
   - Combining with the $z$-displacement: $\ell = \sqrt{\ell_{xy}^2 + (\Delta z)^2} = \sqrt{5^2 + 3^2} = \sqrt{25 + 9} = \sqrt{34} \quad (\checkmark)$.
