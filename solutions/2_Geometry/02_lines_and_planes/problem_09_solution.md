# Solution to Exercise 9: Distances

## 1. Problem Statement

1. Compute the Euclidean distance from point $P = (2, 3)$ to the line in $\mathbb{R}^2$ given by:
   $$
   3x + 4y - 10 = 0
   $$
2. Compute the Euclidean distance from point $Q = (2, -1, 3)$ to the plane in $\mathbb{R}^3$ given by:
   $$
   2x - 2y + z - 4 = 0
   $$
3. Compare the two distance formulas and explain their common mathematical foundation rooted in the normal direction.

---

## 2. Theoretical Background and Concepts

1. **Distance from a Point to a Hyperplane in $\mathbb{R}^n$:**
   In Euclidean space $\mathbb{R}^n$, an affine hyperplane $\mathcal{H}$ is defined by:
   $$
   n \cdot X + D = 0
   $$
   where $n \ne \mathbf{0}$ is a normal vector perpendicular to $\mathcal{H}$.
   The Euclidean distance from an arbitrary point $P_0$ to $\mathcal{H}$ is obtained by orthogonally projecting the displacement vector from any point $X_0 \in \mathcal{H}$ to $P_0$ onto the unit normal vector $\hat{n} = \frac{n}{\|n\|}$:
   $$
   d(P_0, \mathcal{H}) = |\overrightarrow{X_0 P_0} \cdot \hat{n}| = \frac{|n \cdot P_0 + D|}{\|n\|}
   $$

2. **Explicit Formulas:**
   - **In $\mathbb{R}^2$ (Point to Line $Ax + By + C = 0$):**
     $$
     d(P, L) = \frac{|A x_0 + B y_0 + C|}{\sqrt{A^2 + B^2}}
     $$
   - **In $\mathbb{R}^3$ (Point to Plane $Ax + By + Cz + D = 0$):**
     $$
     d(Q, \Pi) = \frac{|A x_0 + B y_0 + Cz_0 + D|}{\sqrt{A^2 + B^2 + C^2}}
     $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Distance from Point $P(2, 3)$ to Line $3x + 4y - 10 = 0$

1. **Identify the parameters:**
   - Point coordinates: $(x_0, y_0) = (2, 3)$
   - Line coefficients: $A = 3$, $B = 4$, $C = -10$

2. **Compute the numerator (absolute residual):**
   $$
   |A x_0 + B y_0 + C| = |3(2) + 4(3) - 10| = |6 + 12 - 10| = |8| = 8
   $$

3. **Compute the denominator (normal vector norm):**
   $$
   \|n\| = \sqrt{A^2 + B^2} = \sqrt{3^2 + 4^2} = \sqrt{9 + 16} = \sqrt{25} = 5
   $$

4. **Calculate distance:**
   $$
   d(P, L) = \frac{8}{5} = 1.6
   $$

---

### Step 2: Distance from Point $Q(2, -1, 3)$ to Plane $2x - 2y + z - 4 = 0$

1. **Identify the parameters:**
   - Point coordinates: $(x_0, y_0, z_0) = (2, -1, 3)$
   - Plane coefficients: $A = 2$, $B = -2$, $C = 1$, $D = -4$

2. **Compute the numerator (absolute residual):**
   $$
   |A x_0 + B y_0 + Cz_0 + D| = |2(2) - 2(-1) + 1(3) - 4| = |4 + 2 + 3 - 4| = |5| = 5
   $$

3. **Compute the denominator (normal vector norm):**
   $$
   \|n\| = \sqrt{A^2 + B^2 + C^2} = \sqrt{2^2 + (-2)^2 + 1^2} = \sqrt{4 + 4 + 1} = \sqrt{9} = 3
   $$

4. **Calculate distance:**
   $$
   d(Q, \Pi) = \frac{5}{3} \approx 1.6667
   $$

---

### Step 3: Comparison and Connection with the Normal Direction

1. **Structural Analogy:**
   The two formulas are instances of the exact same master formula in dimensions $n = 2$ and $n = 3$:
   $$
   d = \frac{|f(P)|}{\|\nabla f\|}
   $$
   where $f(X) = n \cdot X + D = 0$ is the affine equation defining the geometric object, and $\nabla f = n$ is its constant gradient (the normal vector).

2. **Geometric Role of the Normal:**
   - The shortest path from an external point to a flat surface (line in 2D, plane in 3D) is along the perpendicular line dropped onto that surface.
   - The numerator evaluates the signed algebraic distance scaled by $\|n\|$, measuring how much $P$ violates the surface equation.
   - The denominator $\|n\|$ acts as a normalizing factor that converts the algebraic residual into physical Euclidean length units by dividing by the length of the normal vector.

---

## 4. Verification and Consistency Checks

1. **Verification of Distance in $\mathbb{R}^2$ via Closest Point:**
   - Line normal through $P(2, 3)$: $(x, y) = (2 + 3t, 3 + 4t)$.
   - Substitute into $3x + 4y - 10 = 0$:
     $$
     3(2 + 3t) + 4(3 + 4t) - 10 = 0 \implies 6 + 9t + 12 + 16t - 10 = 0 \implies 25t + 8 = 0 \implies t = -\frac{8}{25}
     $$
   - Displacement vector:
     $$
     \Delta = t n = -\frac{8}{25} \begin{pmatrix} 3 \\ 4 \end{pmatrix} \implies \|\Delta\| = \left|-\frac{8}{25}\right| \sqrt{3^2 + 4^2} = \frac{8}{25} \times 5 = \frac{8}{5} = 1.6 \quad (\checkmark)
     $$

2. **Verification of Distance in $\mathbb{R}^3$ via Closest Point:**
   - Line normal through $Q(2, -1, 3)$: $(x, y, z) = (2 + 2t, -1 - 2t, 3 + t)$.
   - Substitute into $2x - 2y + z - 4 = 0$:
     $$
     2(2 + 2t) - 2(-1 - 2t) + (3 + t) - 4 = 0 \implies 4 + 4t + 2 + 4t + 3 + t - 4 = 0 \implies 9t + 5 = 0 \implies t = -\frac{5}{9}
     $$
   - Displacement vector:
     $$
     \Delta = t n = -\frac{5}{9} \begin{pmatrix} 2 \\ -2 \\ 1 \end{pmatrix} \implies \|\Delta\| = \left|-\frac{5}{9}\right| \sqrt{2^2 + (-2)^2 + 1^2} = \frac{5}{9} \times 3 = \frac{5}{3} \quad (\checkmark)
     $$
