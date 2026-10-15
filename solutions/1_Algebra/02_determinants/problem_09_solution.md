# Solution to Exercise 9: Area and the Determinant

## 1. Problem Statement

Given the two vectors in $\mathbb{R}^2$:
$$
u = \begin{pmatrix} 3 \\ 1 \end{pmatrix}, \qquad v = \begin{pmatrix} 1 \\ 4 \end{pmatrix}
$$
which span a parallelogram in the plane.

1. Compute the area of the parallelogram using a determinant.
2. Reverse the order of the vectors and compute the resulting determinant.
3. Explain what changes in the determinant and what does not change in the area of the parallelogram.

---

## 2. Theoretical Background and Concepts

1. **Geometric Interpretation of $2 \times 2$ Determinants:**
   Let $u = \begin{pmatrix} u_1 \\ u_2 \end{pmatrix}$ and $v = \begin{pmatrix} v_1 \\ v_2 \end{pmatrix}$ be two vectors in the Cartesian plane. The determinant of the matrix formed by placing these vectors as columns:
   $$
   \det(u, v) = \det\begin{pmatrix} u_1 & v_1 \\ u_2 & v_2 \end{pmatrix} = u_1 v_2 - u_2 v_1
   $$
   represents the **signed area** of the parallelogram spanned by $u$ and $v$.

2. **Signed Area and Orientation:**
   - The sign of the determinant indicates the **orientation** (handedness) of the ordered pair $(u, v)$:
     - $\det(u, v) > 0$: The shortest rotation from $u$ to $v$ is **counterclockwise** (right-handed / positively oriented).
     - $\det(u, v) < 0$: The shortest rotation from $u$ to $v$ is **clockwise** (left-handed / negatively oriented).
     - $\det(u, v) = 0$: The vectors are collinear (degenerate parallelogram of area zero).

3. **Geometric (Absolute) Area:**
   Geometric area is a non-negative physical quantity, defined as the absolute value of the determinant:
   $$
   \operatorname{Area}(u, v) = |\det(u, v)|
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute Area with Order $(u, v)$

Form the matrix $M$ using $u$ as the first column and $v$ as the second column:
$$
M = \begin{pmatrix} u & v \end{pmatrix} = \begin{pmatrix} 3 & 1 \\ 1 & 4 \end{pmatrix}
$$

Compute the determinant:
$$
\det M = (3)(4) - (1)(1) = 12 - 1 = 11
$$

The area of the parallelogram is the absolute value:
$$
\operatorname{Area} = |\det M| = |11| = 11
$$

---

### Step 2: Compute Determinant with Reversed Order $(v, u)$

Form the matrix $M'$ using $v$ as the first column and $u$ as the second column:
$$
M' = \begin{pmatrix} v & u \end{pmatrix} = \begin{pmatrix} 1 & 3 \\ 4 & 1 \end{pmatrix}
$$

Compute the determinant:
$$
\det M' = (1)(1) - (3)(4) = 1 - 12 = -11
$$

---

### Step 3: Explanation of What Changes and What Remains Invariant

1. **What changes in the determinant:**
   - **The sign reverses** from $+11$ to $-11$:
     $$
     \det(v, u) = -\det(u, v)
     $$
   - This occurs because swapping two columns of a matrix alternates the sign of the determinant.
   - Geometrically, this sign change corresponds to a **reversal of orientation**: moving from $u$ to $v$ turns counterclockwise, whereas moving from $v$ to $u$ turns clockwise.

2. **What does not change in the area:**
   - **The numerical area remains completely unchanged**:
     $$
     \operatorname{Area} = |\det(v, u)| = |-11| = 11
     $$
   - The physical shape, side lengths ($\|u\| = \sqrt{3^2+1^2} = \sqrt{10}$, $\|v\| = \sqrt{1^2+4^2} = \sqrt{17}$), and internal angles of the parallelogram are entirely identical regardless of which spanning vector is listed first.

---

## 4. Verification and Consistency Checks

1. **Cross-Product Magnitude Check:**
   Embed the vectors in $\mathbb{R}^3$ as $\mathbf{u} = (3, 1, 0)$ and $\mathbf{v} = (1, 4, 0)$:
   $$
   \mathbf{u} \times \mathbf{v} = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 3 & 1 & 0 \\ 1 & 4 & 0 \end{vmatrix} = \mathbf{k} (3 \cdot 4 - 1 \cdot 1) = 11 \mathbf{k}
   $$
   The area is the magnitude of the cross product:
   $$
   \|\mathbf{u} \times \mathbf{v}\| = \|11 \mathbf{k}\| = 11 \quad \checkmark
   $$

2. **Base $\times$ Height Check:**
   - Take the base along $u$: $b = \|u\| = \sqrt{3^2 + 1^2} = \sqrt{10}$.
   - The unit normal to $u$ is $n = \frac{1}{\sqrt{10}} \begin{pmatrix} -1 \\ 3 \end{pmatrix}$.
   - The height $h$ is the projection of $v$ onto the normal:
     $$
     h = |v \cdot n| = \frac{|1(-1) + 4(3)|}{\sqrt{10}} = \frac{|-1 + 12|}{\sqrt{10}} = \frac{11}{\sqrt{10}}
     $$
   - The area is:
     $$
     \operatorname{Area} = b \cdot h = \sqrt{10} \cdot \frac{11}{\sqrt{10}} = 11 \quad \checkmark
     $$

