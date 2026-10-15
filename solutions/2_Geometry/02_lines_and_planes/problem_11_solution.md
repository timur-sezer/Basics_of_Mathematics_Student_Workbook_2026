# Solution to Exercise 11: Plane Containing a Line and a Point

## 1. Problem Statement

Given the line $L$ in $\mathbb{R}^3$:
$$
L: (x, y, z) = (1, 0, 2) + t(1, 1, -1), \quad t \in \mathbb{R}
$$
and the external point:
$$
P = (0, 2, 1)
$$

1. Verify that point $P$ does not lie on line $L$, ensuring that $L$ and $P$ uniquely determine a plane.
2. Find the Cartesian equation of the plane $\Pi$ containing both the line $L$ and the point $P$.
3. Check that the entire line $L$ and the point $P$ lie in the resulting plane.

---

## 2. Theoretical Background and Concepts

1. **Uniqueness of a Plane Determined by a Line and an External Point:**
   A straight line $L$ and a point $P \notin L$ uniquely define a 2-dimensional affine plane $\Pi$ in $\mathbb{R}^3$.
   To find the plane:
   - Identify the line's base point $P_0$ and direction vector $v$.
   - Form a second directional vector $u = \overrightarrow{P_0 P} = P - P_0$ connecting the line's base point to the external point.
   - The vectors $v$ and $u$ are non-collinear and lie entirely in the plane $\Pi$.

2. **Normal Vector Construction via Cross Product:**
   The normal vector $n$ to the plane is given by the cross product:
   $$
   n = v \times u
   $$
   The plane equation is then defined by $n \cdot (X - P) = 0$ or $n \cdot (X - P_0) = 0$.

3. **Inclusion of a Line in a Plane:**
   A line $L(t) = P_0 + t v$ lies entirely in plane $\Pi$ if and only if:
   - Base point $P_0 \in \Pi$, and
   - Direction vector $v \perp n$ ($v \cdot n = 0$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Verify That Point $P$ Does Not Lie on Line $L$

Base point of line $L$ is $P_0(1, 0, 2)$ with direction vector $v = (1, 1, -1)$.
Test if there exists a scalar $t$ such that:
$$
\begin{pmatrix} 1 + t \\ t \\ 2 - t \end{pmatrix} = \begin{pmatrix} 0 \\ 2 \\ 1 \end{pmatrix}
$$
- From $x$-coordinate: $1 + t = 0 \implies t = -1$.
- From $y$-coordinate: $t = 2$.
- Comparing the values: $-1 \ne 2$ (Contradiction).

Since no single parameter value $t$ satisfies the system, **point $P(0, 2, 1)$ does not lie on line $L$**. Thus, $L$ and $P$ uniquely determine a plane.

---

### Step 2: Construct Two Non-Collinear Vectors in the Plane

1. **Direction vector of the line:**
   $$
   v = \begin{pmatrix} 1 \\ 1 \\ -1 \end{pmatrix}
   $$

2. **Connecting vector from $P_0(1, 0, 2)$ to $P(0, 2, 1)$:**
   $$
   u = \overrightarrow{P_0 P} = P - P_0 = \begin{pmatrix} 0 - 1 \\ 2 - 0 \\ 1 - 2 \end{pmatrix} = \begin{pmatrix} -1 \\ 2 \\ -1 \end{pmatrix}
   $$

---

### Step 3: Compute the Normal Vector $n = v \times u$

Set up the determinant:
$$
n = v \times u = \det \begin{pmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 1 & -1 \\ -1 & 2 & -1 \end{pmatrix}
$$

Expand along the first row:
$$
n = \mathbf{i} \det \begin{pmatrix} 1 & -1 \\ 2 & -1 \end{pmatrix} - \mathbf{j} \det \begin{pmatrix} 1 & -1 \\ -1 & -1 \end{pmatrix} + \mathbf{k} \det \begin{pmatrix} 1 & 1 \\ -1 & 2 \end{pmatrix}
$$

Evaluate each component:
- $\mathbf{i}$-component: $(1)(-1) - (-1)(2) = -1 - (-2) = -1 + 2 = 1$
- $\mathbf{j}$-component: $-[(1)(-1) - (-1)(-1)] = -[-1 - 1] = -(-2) = 2$
- $\mathbf{k}$-component: $(1)(2) - (1)(-1) = 2 - (-1) = 2 + 1 = 3$

Thus, the normal vector is:
$$
n = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}
$$

---

### Step 4: Derive the Cartesian Equation of Plane $\Pi$

Using normal vector $n = (1, 2, 3)$ and base point $P_0(1, 0, 2)$:
$$
n \cdot (X - P_0) = 0
$$
$$
1(x - 1) + 2(y - 0) + 3(z - 2) = 0
$$
Distribute and simplify:
$$
x - 1 + 2y + 3z - 6 = 0 \implies x + 2y + 3z - 7 = 0
$$

The equation of the plane is:
$$
x + 2y + 3z = 7
$$

---

### Step 5: Verification of Point $P$ and Line $L$

1. **Verify Point $P(0, 2, 1)$:**
   Substitute $(x, y, z) = (0, 2, 1)$ into $x + 2y + 3z = 7$:
   $$
   \text{LHS} = 0 + 2(2) + 3(1) = 0 + 4 + 3 = 7 = \text{RHS} \quad (\checkmark)
   $$
   Point $P$ lies on the plane.

2. **Verify Entire Line $L$:**
   Substitute the parametric coordinates $(x(t), y(t), z(t)) = (1 + t, t, 2 - t)$ into the plane equation:
   $$
   \text{LHS} = (1 + t) + 2(t) + 3(2 - t)
   $$
   Expand:
   $$
   = 1 + t + 2t + 6 - 3t = (1 + 6) + (t + 2t - 3t) = 7 + 0t = 7
   $$
   $$
   \text{RHS} = 7 \quad (\checkmark)
   $$
   The equation holds identically for **all** $t \in \mathbb{R}$.
   Therefore, every point on line $L$ lies on plane $\Pi$.

---

## 4. Verification and Consistency Checks

1. **Orthogonality of the Normal Vector:**
   - $n \cdot v = (1)(1) + (2)(1) + (3)(-1) = 1 + 2 - 3 = 0 \quad (\checkmark)$
   - $n \cdot u = (1)(-1) + (2)(2) + (3)(-1) = -1 + 4 - 3 = 0 \quad (\checkmark)$
   Vector $n = (1, 2, 3)$ is perpendicular to both spanning vectors.

2. **Second Line Point Check:**
   Choose parameter value $t = 3$ on line $L$:
   $$
   P_L(3) = (1 + 3, 3, 2 - 3) = (4, 3, -1)
   $$
   Substitute into $x + 2y + 3z = 7$:
   $$
   4 + 2(3) + 3(-1) = 4 + 6 - 3 = 7 \quad (\checkmark)
   $$
   The check confirms that line $L$ is embedded in $\Pi$.
