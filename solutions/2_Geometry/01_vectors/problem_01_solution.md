# Solution to Exercise 1: Vector Operations and Their Meaning

## 1. Problem Statement

Given the vectors in $\mathbb{R}^3$:
$$
u = (2, -1, 3), \qquad v = (-1, 4, 2)
$$

1. Compute the following vector linear combinations:
   $$
   u + v, \qquad u - v, \qquad 3u - 2v
   $$
2. Verify the identity $(u + v) - v = u$ by substituting the computed vectors.
3. Provide a clear geometric interpretation of vector addition.

---

## 2. Theoretical Background and Concepts

1. **Componentwise Operations on Vectors:**
   For any vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$ in $\mathbb{R}^3$ and scalars $\alpha, \beta \in \mathbb{R}$:
   - **Vector Addition:** $u + v = (u_1 + v_1, u_2 + v_2, u_3 + v_3)$
   - **Vector Subtraction:** $u - v = (u_1 - v_1, u_2 - v_2, u_3 - v_3)$
   - **Scalar Multiplication:** $\alpha u = (\alpha u_1, \alpha u_2, \alpha u_3)$
   - **Linear Combination:** $\alpha u + \beta v = (\alpha u_1 + \beta v_1, \alpha u_2 + \beta v_2, \alpha u_3 + \beta v_3)$

2. **Group Properties of Vector Spaces:**
   The set $\mathbb{R}^3$ with vector addition forms an abelian group:
   - Vector addition is commutative ($u + v = v + u$) and associative ($(u + v) + w = u + (v + w)$).
   - The zero vector $\mathbf{0} = (0, 0, 0)$ is the additive identity: $u + \mathbf{0} = u$.
   - Every vector has an additive inverse $-v$ such that $v + (-v) = \mathbf{0}$.
   - Thus, $(u + v) - v = (u + v) + (-v) = u + (v + (-v)) = u + \mathbf{0} = u$.

3. **Geometric Meaning of Vector Addition:**
   - **Displacement Concatenation (Triangle Rule / Head-to-Tail):** A vector represents a translation or displacement. If $u$ translates from point $O$ to point $P$, and $v$ translates from point $P$ to point $Q$, the sum $u + v$ represents the direct, net displacement from origin $O$ to terminal point $Q$.
   - **Parallelogram Law:** If $u$ and $v$ share a common initial point, they define adjacent sides of a parallelogram. The sum $u + v$ is the directed main diagonal emanating from that shared initial vertex.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $u + v$

Add the corresponding components:
$$
u + v = \begin{pmatrix} 2 \\ -1 \\ 3 \end{pmatrix} + \begin{pmatrix} -1 \\ 4 \\ 2 \end{pmatrix} = \begin{pmatrix} 2 + (-1) \\ -1 + 4 \\ 3 + 2 \end{pmatrix} = \begin{pmatrix} 1 \\ 3 \\ 5 \end{pmatrix}
$$

In row notation:
$$
u + v = (1, 3, 5)
$$

---

### Step 2: Compute $u - v$

Subtract the corresponding components of $v$ from $u$:
$$
u - v = \begin{pmatrix} 2 \\ -1 \\ 3 \end{pmatrix} - \begin{pmatrix} -1 \\ 4 \\ 2 \end{pmatrix} = \begin{pmatrix} 2 - (-1) \\ -1 - 4 \\ 3 - 2 \end{pmatrix} = \begin{pmatrix} 3 \\ -5 \\ 1 \end{pmatrix}
$$

In row notation:
$$
u - v = (3, -5, 1)
$$

---

### Step 3: Compute $3u - 2v$

1. Compute $3u$:
   $$
   3u = 3 \begin{pmatrix} 2 \\ -1 \\ 3 \end{pmatrix} = \begin{pmatrix} 6 \\ -3 \\ 9 \end{pmatrix}
   $$

2. Compute $2v$:
   $$
   2v = 2 \begin{pmatrix} -1 \\ 4 \\ 2 \end{pmatrix} = \begin{pmatrix} -2 \\ 8 \\ 4 \end{pmatrix}
   $$

3. Subtract $2v$ from $3u$:
   $$
   3u - 2v = \begin{pmatrix} 6 \\ -3 \\ 9 \end{pmatrix} - \begin{pmatrix} -2 \\ 8 \\ 4 \end{pmatrix} = \begin{pmatrix} 6 - (-2) \\ -3 - 8 \\ 9 - 4 \end{pmatrix} = \begin{pmatrix} 8 \\ -11 \\ 5 \end{pmatrix}
   $$

In row notation:
$$
3u - 2v = (8, -11, 5)
$$

---

### Step 4: Verification of the Identity $(u + v) - v = u$

Substitute the computed sum $u + v = (1, 3, 5)$ and the given vector $v = (-1, 4, 2)$:
$$
(u + v) - v = \begin{pmatrix} 1 \\ 3 \\ 5 \end{pmatrix} - \begin{pmatrix} -1 \\ 4 \\ 2 \end{pmatrix} = \begin{pmatrix} 1 - (-1) \\ 3 - 4 \\ 5 - 2 \end{pmatrix} = \begin{pmatrix} 2 \\ -1 \\ 3 \end{pmatrix}
$$

Comparing with the initial vector:
$$
\begin{pmatrix} 2 \\ -1 \\ 3 \end{pmatrix} = u \quad (\checkmark)
$$
The algebraic inverse property is explicitly verified.

---

### Step 5: Geometric Interpretation

1. **Triangle Rule (Chaining of Displacements):**
   - Place the initial point (tail) of $u$ at the origin $(0, 0, 0)$. The vector terminates at point $P(2, -1, 3)$.
   - Place the tail of $v$ at point $P$. Displacing by $v = (-1, 4, 2)$ from $P$ terminates at $Q(2 - 1, -1 + 4, 3 + 2) = Q(1, 3, 5)$.
   - The vector $u + v$ connects the origin $(0, 0, 0)$ directly to $Q(1, 3, 5)$, proving that vector addition models consecutive spatial displacements.
2. **Reversibility:**
   Subtracting $v$ from $u + v$ geometrically corresponds to traversing backwards along the displacement $v$ from $Q$ back to $P$, restoring the position vector $u$.

---

## 4. Verification and Consistency Checks

1. **Linearity Check with Dual Operations:**
   Compute $3u - 2v$ by factoring through $u - v$:
   $$
   3u - 2v = u + 2(u - v) = \begin{pmatrix} 2 \\ -1 \\ 3 \end{pmatrix} + 2 \begin{pmatrix} 3 \\ -5 \\ 1 \end{pmatrix} = \begin{pmatrix} 2 + 6 \\ -1 - 10 \\ 3 + 2 \end{pmatrix} = \begin{pmatrix} 8 \\ -11 \\ 5 \end{pmatrix} \quad (\checkmark)
   $$
   The alternative grouping yields the exact same vector.

2. **Additive Consistency Check:**
   $$
   (u - v) + v = \begin{pmatrix} 3 \\ -5 \\ 1 \end{pmatrix} + \begin{pmatrix} -1 \\ 4 \\ 2 \end{pmatrix} = \begin{pmatrix} 2 \\ -1 \\ 3 \end{pmatrix} = u \quad (\checkmark)
   $$
