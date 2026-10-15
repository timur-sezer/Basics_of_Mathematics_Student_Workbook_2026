# Solution to Exercise 6: Projection and Perpendicular Component

## 1. Problem Statement

Given the vectors in $\mathbb{R}^2$:
$$
u = (4, 2), \qquad v = (1, 1)
$$

1. Find the orthogonal projection of vector $u$ onto the direction of vector $v$, denoted by $\operatorname{proj}_v u$.
2. Compute the perpendicular residual vector:
   $$
   r = u - \operatorname{proj}_v u
   $$
3. Verify by calculation that $r$ is orthogonal to $v$ ($r \cdot v = 0$).
4. Provide a geometric interpretation of this decomposition.

---

## 2. Theoretical Background and Concepts

1. **Orthogonal Projection Formula:**
   The orthogonal projection of a vector $u$ onto a non-zero vector $v$ is the vector parallel to $v$ whose tip marks the foot of the perpendicular dropped from the tip of $u$ to the line spanned by $v$:
   $$
   \operatorname{proj}_v u = \left(\frac{u \cdot v}{\|v\|^2}\right) v
   $$
   The scalar $\frac{u \cdot v}{\|v\|}$ is the signed scalar component (shadow length), and dividing by $\|v\|$ again gives the scaling coefficient for $v$.

2. **Orthogonal Decomposition Theorem:**
   Any vector $u$ can be uniquely written as the sum of two orthogonal components:
   $$
   u = u_{\parallel} + u_{\perp}
   $$
   where $u_{\parallel} = \operatorname{proj}_v u$ is parallel to $v$, and $u_{\perp} = r = u - \operatorname{proj}_v u$ is perpendicular to $v$.
   The residual vector $r$ represents the error or difference vector between $u$ and its best one-dimensional approximation in the direction of $v$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Orthogonal Projection $\operatorname{proj}_v u$

1. **Compute the dot product $u \cdot v$:**
   $$
   u \cdot v = (4)(1) + (2)(1) = 4 + 2 = 6
   $$

2. **Compute the squared norm $\|v\|^2$:**
   $$
   \|v\|^2 = 1^2 + 1^2 = 1 + 1 = 2
   $$

3. **Evaluate the projection vector:**
   $$
   \operatorname{proj}_v u = \left(\frac{u \cdot v}{\|v\|^2}\right) v = \left(\frac{6}{2}\right) \begin{pmatrix} 1 \\ 1 \end{pmatrix} = 3 \begin{pmatrix} 1 \\ 1 \end{pmatrix} = \begin{pmatrix} 3 \\ 3 \end{pmatrix}
   $$

In row notation:
$$
\operatorname{proj}_v u = (3, 3)
$$

---

### Step 2: Compute the Perpendicular Component $r$

Subtract $\operatorname{proj}_v u$ from $u$:
$$
r = u - \operatorname{proj}_v u = \begin{pmatrix} 4 \\ 2 \end{pmatrix} - \begin{pmatrix} 3 \\ 3 \end{pmatrix} = \begin{pmatrix} 4 - 3 \\ 2 - 3 \end{pmatrix} = \begin{pmatrix} 1 \\ -1 \end{pmatrix}
$$

In row notation:
$$
r = (1, -1)
$$

---

### Step 3: Verify the Orthogonality Condition $r \cdot v = 0$

Compute the dot product of $r = (1, -1)$ and $v = (1, 1)$:
$$
r \cdot v = (1)(1) + (-1)(1) = 1 - 1 = 0 \quad (\checkmark)
$$

The calculation yields $0$, confirming that $r$ is strictly perpendicular to $v$.

---

### Step 4: Geometric Interpretation

1. **Right Triangle Decomposition:**
   The three vectors $u_{\parallel} = (3, 3)$, $r = (1, -1)$, and $u = (4, 2)$ form a right-angled vector triangle:
   - The hypotenuse is the original vector $u$.
   - The adjacent leg along the line $y = x$ (spanned by $v$) is $u_{\parallel} = (3, 3)$.
   - The opposite leg, perpendicular to the line $y = x$, is $r = (1, -1)$.
2. **Minimal Distance:**
   The line spanned by $v = (1, 1)$ is the line $y = x$. The point $(3, 3)$ is the unique point on this line closest to the point $(4, 2)$. The length of $r$, $\|r\| = \sqrt{1^2 + (-1)^2} = \sqrt{2}$, represents the shortest Euclidean distance from $(4, 2)$ to the line $y = x$.

---

## 4. Verification and Consistency Checks

1. **Reconstruction Check ($u = u_{\parallel} + r$):**
   $$
   u_{\parallel} + r = \begin{pmatrix} 3 \\ 3 \end{pmatrix} + \begin{pmatrix} 1 \\ -1 \end{pmatrix} = \begin{pmatrix} 3 + 1 \\ 3 - 1 \end{pmatrix} = \begin{pmatrix} 4 \\ 2 \end{pmatrix} = u \quad (\checkmark)
   $$

2. **Pythagorean Theorem Check:**
   In an orthogonal decomposition, the norms must satisfy $\|u\|^2 = \|u_{\parallel}\|^2 + \|r\|^2$:
   - $\|u\|^2 = 4^2 + 2^2 = 16 + 4 = 20$
   - $\|u_{\parallel}\|^2 = 3^2 + 3^2 = 9 + 9 = 18$
   - $\|r\|^2 = 1^2 + (-1)^2 = 1 + 1 = 2$
   $$
   \|u_{\parallel}\|^2 + \|r\|^2 = 18 + 2 = 20 = \|u\|^2 \quad (\checkmark)
   $$

3. **Slope Product Check:**
   - Direction line slope: $m_v = \frac{1}{1} = 1$.
   - Residual line slope: $m_r = \frac{-1}{1} = -1$.
   - $m_v \cdot m_r = (1)(-1) = -1$, confirming perpendicularity in $\mathbb{R}^2$.
