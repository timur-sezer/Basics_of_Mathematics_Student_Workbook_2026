# Solution to Exercise 7: A Line Relative to a Plane

## 1. Problem Statement

Given the line $L$ and the plane $\Pi$ in $\mathbb{R}^3$:
$$
L: (x, y, z) = (1, 1, 0) + t(1, -1, 0), \quad t \in \mathbb{R}
$$
$$
\Pi: x + y + z = 2
$$

1. Determine whether the line intersects the plane at exactly one point, is parallel to the plane (with no points of intersection), or lies entirely within the plane.
2. Explain the fundamental geometric role of the dot product between the line's direction vector $v$ and the plane's normal vector $n$.

---

## 2. Theoretical Background and Concepts

1. **Relative Positions of a Line and a Plane in $\mathbb{R}^3$:**
   Consider a line $L: X(t) = P_0 + t v$ and a plane $\Pi: n \cdot X = d$.
   Substituting the parametric coordinates of $L$ into the plane equation produces a single linear equation in parameter $t$:
   $$
   n \cdot (P_0 + t v) = d \iff t (n \cdot v) = d - n \cdot P_0
   $$

2. **Classification via the Dot Product $n \cdot v$:**
   - **Case 1: $n \cdot v \ne 0$ (Transverse Intersection)**
     The line is not parallel to the plane. The equation has a unique solution $t^* = \frac{d - n \cdot P_0}{n \cdot v}$, meaning $L$ intersects $\Pi$ at **exactly one point**.
   - **Case 2: $n \cdot v = 0$ (Parallelism)**
     The direction vector $v$ is orthogonal to the normal vector $n$, meaning the line is parallel to the plane. The equation reduces to:
     $$
     0 \cdot t = d - n \cdot P_0
     $$
     - If $n \cdot P_0 \ne d$: The base point $P_0 \notin \Pi$. The equation becomes $0 = \text{non-zero}$ (contradiction). The line is **strictly parallel with no intersection points** ($L \cap \Pi = \emptyset$).
     - If $n \cdot P_0 = d$: The base point $P_0 \in \Pi$. The equation becomes $0 \cdot t = 0$ (tautology). The line **lies entirely within the plane** ($L \subset \Pi$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify Vectors $v$ and $n$

- From line $L: (x, y, z) = (1, 1, 0) + t(1, -1, 0)$:
  - Base point: $P_0 = (1, 1, 0)$
  - Direction vector: $v = (1, -1, 0)$
- From plane $\Pi: x + y + z = 2$:
  - Normal vector: $n = (1, 1, 1)$
  - Scalar constant: $d = 2$

---

### Step 2: Compute the Dot Product $v \cdot n$

Evaluate $v \cdot n$:
$$
v \cdot n = (1)(1) + (-1)(1) + (0)(1) = 1 - 1 + 0 = 0
$$

Because $v \cdot n = 0$, the line's direction vector $v$ is perpendicular to the normal vector $n$. This means the line $L$ **does not cross the plane transversely**; it is parallel to the plane.

---

### Step 3: Test Whether Base Point $P_0$ Lies on Plane $\Pi$

Substitute the coordinates of base point $P_0(1, 1, 0)$ into the plane equation $\Pi: x + y + z = 2$:
$$
\text{LHS} = 1 + 1 + 0 = 2
$$
$$
\text{RHS} = 2
$$
Since $\text{LHS} = \text{RHS} = 2$, point $P_0$ **lies on the plane $\Pi$**.

---

### Step 4: Full Algebraic Substitution and Conclusion

Substitute an arbitrary point $(x(t), y(t), z(t)) = (1 + t, 1 - t, 0)$ into $\Pi$:
$$
(1 + t) + (1 - t) + 0 = (1 + 1) + (t - t) + 0 = 2 + 0t = 2
$$
The equation $2 = 2$ holds identically for **all** $t \in \mathbb{R}$.

**Conclusion:**
Every point on the line $L$ satisfies the equation of the plane $\Pi$. Therefore, **the line $L$ lies entirely in the plane $\Pi$** ($L \subset \Pi$).

---

### Step 5: The Role of the Dot Product $v \cdot n$

The dot product $v \cdot n$ serves as a **universal discriminator** for the line-plane relationship:
1. **Geometric Angle Relation:**
   The angle $\alpha$ between a line and a plane satisfies $\sin \alpha = \frac{|v \cdot n|}{\|v\| \|n\|}$.
   - When $v \cdot n = 0 \iff \sin \alpha = 0 \iff \alpha = 0^\circ$, the line makes zero angle with the plane (it is parallel).
   - When $v \cdot n \ne 0 \iff \alpha > 0^\circ$, the line is inclined relative to the plane and penetrates through it.
2. **Algebraic Decoupling:**
   Evaluating $v \cdot n$ isolates the directional dependence before needing to calculate intersection coordinates, separating the orientation test ($v \cdot n = 0$) from the position test ($P_0 \in \Pi$).

---

## 4. Verification and Consistency Checks

1. **Second Point Test on Line $L$:**
   Choose parameter value $t = 5$:
   $$
   P(5) = (1 + 5, 1 - 5, 0) = (6, -4, 0)
   $$
   Substitute into plane $\Pi$:
   $$
   x + y + z = 6 + (-4) + 0 = 2 \quad (\checkmark)
   $$
   Point $P(5)$ lies on the plane.

2. **Negative Parameter Test on Line $L$:**
   Choose parameter value $t = -3$:
   $$
   P(-3) = (1 - 3, 1 - (-3), 0) = (-2, 4, 0)
   $$
   Substitute into plane $\Pi$:
   $$
   x + y + z = -2 + 4 + 0 = 2 \quad (\checkmark)
   $$
   Point $P(-3)$ also lies on the plane, confirming $L \subset \Pi$.
