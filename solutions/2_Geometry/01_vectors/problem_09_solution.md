# Solution to Exercise 9: Cross Product as a Perpendicular Direction

## 1. Problem Statement

Given the vectors in three-dimensional Euclidean space $\mathbb{R}^3$:
$$
u = (1, 2, 0), \qquad v = (0, 1, 3)
$$

1. Compute the cross product $u \times v$.
2. Verify by calculating dot products that $u \times v$ is orthogonal to both vector $u$ and vector $v$.
3. Compute the reverse cross product $v \times u$.
4. Compare the two results and explain the geometric consequences of reversing the order of arguments in the cross product.

---

## 2. Theoretical Background and Concepts

1. **Definition of the Cross Product (Vector Product):**
   For two vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$ in $\mathbb{R}^3$, the cross product $u \times v$ is defined as the formal determinant:
   $$
   u \times v = \det \begin{pmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ u_1 & u_2 & u_3 \\ v_1 & v_2 & v_3 \end{pmatrix} = \begin{pmatrix} u_2 v_3 - u_3 v_2 \\ -(u_1 v_3 - u_3 v_1) \\ u_1 v_2 - u_2 v_1 \end{pmatrix}
   $$

2. **Geometric Properties of the Cross Product:**
   - **Orthogonality:** The vector $u \times v$ is simultaneously perpendicular to both $u$ and $v$:
     $$
     (u \times v) \cdot u = 0, \qquad (u \times v) \cdot v = 0
     $$
   - **Anticommutativity:** Interchanging the rows in the defining determinant reverses its sign:
     $$
     v \times u = -(u \times v)
     $$
   - **Right-Hand Rule:** The ordered triplet $(u, v, u \times v)$ forms a right-handed coordinate frame. If the fingers of the right hand curl from $u$ to $v$, the thumb points along $u \times v$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Cross Product $u \times v$

Set up the determinant with unit vectors $\mathbf{i}, \mathbf{j}, \mathbf{k}$:
$$
u \times v = \det \begin{pmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 2 & 0 \\ 0 & 1 & 3 \end{pmatrix}
$$

Expand along the first row:
$$
u \times v = \mathbf{i} \det \begin{pmatrix} 2 & 0 \\ 1 & 3 \end{pmatrix} - \mathbf{j} \det \begin{pmatrix} 1 & 0 \\ 0 & 3 \end{pmatrix} + \mathbf{k} \det \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}
$$

Calculate the $2 \times 2$ determinants:
- $\mathbf{i}$-component: $(2)(3) - (0)(1) = 6 - 0 = 6$
- $\mathbf{j}$-component: $-[(1)(3) - (0)(0)] = -(3 - 0) = -3$
- $\mathbf{k}$-component: $(1)(1) - (2)(0) = 1 - 0 = 1$

Thus:
$$
u \times v = 6\mathbf{i} - 3\mathbf{j} + 1\mathbf{k} = (6, -3, 1)
$$

---

### Step 2: Verify Perpendicularity Using Dot Products

1. **Test orthogonality to $u = (1, 2, 0)$:**
   $$
   (u \times v) \cdot u = (6)(1) + (-3)(2) + (1)(0) = 6 - 6 + 0 = 0 \quad (\checkmark)
   $$
   Because the dot product is zero, $(u \times v) \perp u$.

2. **Test orthogonality to $v = (0, 1, 3)$:**
   $$
   (u \times v) \cdot v = (6)(0) + (-3)(1) + (1)(3) = 0 - 3 + 3 = 0 \quad (\checkmark)
   $$
   Because the dot product is zero, $(u \times v) \perp v$.

Both orthogonality conditions are satisfied.

---

### Step 3: Compute the Reverse Cross Product $v \times u$

Set up the determinant with $v$ in the second row and $u$ in the third row:
$$
v \times u = \det \begin{pmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 0 & 1 & 3 \\ 1 & 2 & 0 \end{pmatrix}
$$

Expand along the first row:
$$
v \times u = \mathbf{i} \det \begin{pmatrix} 1 & 3 \\ 2 & 0 \end{pmatrix} - \mathbf{j} \det \begin{pmatrix} 0 & 3 \\ 1 & 0 \end{pmatrix} + \mathbf{k} \det \begin{pmatrix} 0 & 1 \\ 1 & 2 \end{pmatrix}
$$

Calculate the $2 \times 2$ determinants:
- $\mathbf{i}$-component: $(1)(0) - (3)(2) = 0 - 6 = -6$
- $\mathbf{j}$-component: $-[(0)(0) - (3)(1)] = -[0 - 3] = 3$
- $\mathbf{k}$-component: $(0)(2) - (1)(1) = 0 - 1 = -1$

Thus:
$$
v \times u = -6\mathbf{i} + 3\mathbf{j} - 1\mathbf{k} = (-6, 3, -1)
$$

---

### Step 4: Comparison and Geometric Consequences

1. **Comparison:**
   Comparing $u \times v = (6, -3, 1)$ and $v \times u = (-6, 3, -1)$:
   $$
   v \times u = - (u \times v)
   $$
   The two vectors have the exact same magnitude:
   $$
   \|u \times v\| = \|v \times u\| = \sqrt{6^2 + (-3)^2 + 1^2} = \sqrt{36 + 9 + 1} = \sqrt{46}
   $$
   and lie along the exact same normal line perpendicular to the plane spanned by $u$ and $v$.

2. **Geometric Consequences of Reversing Argument Order:**
   - The cross product is **anticommutative**.
   - Reversing the operational order from $u \times v$ to $v \times u$ inverts the orientation: the resulting vector points in the directly opposite direction ($180^\circ$ reversal).
   - By the right-hand rule, curling the fingers from $u$ to $v$ directs the thumb along $(6, -3, 1)$, whereas curling from $v$ to $u$ directs the thumb in the opposite direction along $(-6, 3, -1)$.

---

## 4. Verification and Consistency Checks

1. **Orthogonality of $v \times u$:**
   $$
   (v \times u) \cdot u = (-6)(1) + (3)(2) + (-1)(0) = -6 + 6 + 0 = 0 \quad (\checkmark)
   $$
   $$
   (v \times u) \cdot v = (-6)(0) + (3)(1) + (-1)(3) = 0 + 3 - 3 = 0 \quad (\checkmark)
   $$

2. **Lagrange's Identity Check:**
   Lagrange's identity states $\|u \times v\|^2 = \|u\|^2 \|v\|^2 - (u \cdot v)^2$:
   - $\|u\|^2 = 1^2 + 2^2 + 0^2 = 5$
   - $\|v\|^2 = 0^2 + 1^2 + 3^2 = 10$
   - $u \cdot v = 1(0) + 2(1) + 0(3) = 2 \implies (u \cdot v)^2 = 4$
   - RHS: $\|u\|^2 \|v\|^2 - (u \cdot v)^2 = (5)(10) - 4 = 50 - 4 = 46$
   - LHS: $\|u \times v\|^2 = 6^2 + (-3)^2 + 1^2 = 36 + 9 + 1 = 46$
   $$
   \|u \times v\|^2 = 46 = \|u\|^2 \|v\|^2 - (u \cdot v)^2 \quad (\checkmark)
   $$
