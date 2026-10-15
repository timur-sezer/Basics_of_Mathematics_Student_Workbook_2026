# Solution to Exercise 3: Vector Normalization

## 1. Problem Statement

Given the two-dimensional vector:
$$
v = (3, 4)
$$

1. Find the unit vector $e$ pointing in the same direction and with the same orientation as $v$.
2. Verify that $\|e\| = 1$.
3. Reconstruct the original vector $v$ in the factorized form $v = \|v\|e$.
4. Explain clearly what changes during vector normalization and what geometric properties remain unchanged.

---

## 2. Theoretical Background and Concepts

1. **Definition of Vector Normalization:**
   Normalization is the operation of dividing a non-zero vector $v$ by its Euclidean norm (length), yielding a dimensionless unit vector $e$:
   $$
   e = \frac{v}{\|v\|} = \frac{1}{\|v\|} v
   $$

2. **Properties of Scalar Multiplication:**
   For any vector $v \in \mathbb{R}^n$ and scalar $c \in \mathbb{R}$:
   $$
   \|c v\| = |c| \, \|v\|
   $$
   Setting $c = \frac{1}{\|v\|}$ (where $\|v\| > 0$):
   $$
   \|e\| = \left\| \frac{1}{\|v\|} v \right\| = \left| \frac{1}{\|v\|} \right| \|v\| = \frac{\|v\|}{\|v\|} = 1
   $$
   This mathematically guarantees that the normalized vector $e$ always has unit length.

3. **Separation of Magnitude and Direction (Non-Zero Vectors):**
   Every **non-zero vector** $v \ne \mathbf{0}$ has a unique canonical decomposition into magnitude and direction:
   $$
   v = \underbrace{\|v\|}_{\text{Magnitude (Scalar } > 0)} \times \underbrace{e}_{\text{Direction \& Orientation (Unit Vector, } \|e\|=1)}
   $$
   *Important Qualification for the Zero Vector:* The zero vector $\mathbf{0}$ has length $\|\mathbf{0}\| = 0$, has no defined geometric direction, and cannot be normalized (division by zero). While $\mathbf{0} = 0 \cdot e$ holds formally for *any* unit vector $e$, the unit factor $e$ is not uniquely determined. Thus, unique decomposition into a direction unit vector applies strictly to non-zero vectors.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Euclidean Norm of $v$

Calculate the length of $v = (3, 4)$:
$$
\|v\| = \sqrt{v_x^2 + v_y^2} = \sqrt{3^2 + 4^2} = \sqrt{9 + 16} = \sqrt{25} = 5
$$

---

### Step 2: Construct the Unit Vector $e$

Multiply $v$ by the reciprocal of its norm $\frac{1}{\|v\|} = \frac{1}{5}$:
$$
e = \frac{1}{5} \begin{pmatrix} 3 \\ 4 \end{pmatrix} = \begin{pmatrix} \frac{3}{5} \\ \frac{4}{5} \end{pmatrix} = \begin{pmatrix} 0.6 \\ 0.8 \end{pmatrix}
$$

In row notation:
$$
e = \left(\frac{3}{5}, \frac{4}{5}\right)
$$

---

### Step 3: Verify that $\|e\| = 1$

Calculate the norm of $e$:
$$
\|e\| = \sqrt{\left(\frac{3}{5}\right)^2 + \left(\frac{4}{5}\right)^2} = \sqrt{\frac{9}{25} + \frac{16}{25}} = \sqrt{\frac{9 + 16}{25}} = \sqrt{\frac{25}{25}} = \sqrt{1} = 1
$$

The norm is verified to be identically $1$.

---

### Step 4: Reconstruct $v$ in the Form $v = \|v\|e$

Multiply the unit vector $e$ by the scalar magnitude $\|v\| = 5$:
$$
\|v\|e = 5 \begin{pmatrix} \frac{3}{5} \\ \frac{4}{5} \end{pmatrix} = \begin{pmatrix} 5 \cdot \frac{3}{5} \\ 5 \cdot \frac{4}{5} \end{pmatrix} = \begin{pmatrix} 3 \\ 4 \end{pmatrix} = v \quad (\checkmark)
$$

The vector $v$ is recovered.

---

### Step 5: What Changes and What Remains Unchanged

1. **What Changes:**
   - **Magnitude / Length:** The Euclidean length changes from its original value of $\|v\| = 5$ to the normalized value $\|e\| = 1$. The scale factor applied is $\lambda = \frac{1}{5} = 0.2$.

2. **What Remains Unchanged:**
   - **Direction (Line of Action):** Both $v$ and $e$ lie on the exact same straight line passing through the origin in $\mathbb{R}^2$, described by the slope equation:
     $$
     m = \frac{v_y}{v_x} = \frac{4}{3} = \frac{e_y}{e_x} = \frac{4/5}{3/5} = \frac{4}{3}
     $$
   - **Orientation / Sense:** Because the scaling factor $\frac{1}{\|v\|} = \frac{1}{5} > 0$ is strictly positive, the vector continues to point into the first quadrant along the direction angle:
     $$
     \theta = \arctan\left(\frac{4}{3}\right) \approx 53.13^\circ \approx 0.9273 \text{ rad}
     $$
     Orientation would only flip if the scalar were negative.

---

## 4. Verification and Consistency Checks

1. **Direction Cosines / Polar Angle Check:**
   Every 2D unit vector can be parameterized as $(\cos \theta, \sin \theta)$:
   $$
   \cos \theta = \frac{3}{5} = 0.6, \qquad \sin \theta = \frac{4}{5} = 0.8
   $$
   Check trigonometric identity:
   $$
   \cos^2 \theta + \sin^2 \theta = 0.6^2 + 0.8^2 = 0.36 + 0.64 = 1.00 \quad (\checkmark)
   $$

2. **Collinearity Cross Product Check in $\mathbb{R}^2$:**
   Compute the 2D cross product (determinant) between $v$ and $e$:
   $$
   v_x e_y - v_y e_x = 3\left(\frac{4}{5}\right) - 4\left(\frac{3}{5}\right) = \frac{12}{5} - \frac{12}{5} = 0 \quad (\checkmark)
   $$
   The zero determinant proves that $v$ and $e$ are parallel.
