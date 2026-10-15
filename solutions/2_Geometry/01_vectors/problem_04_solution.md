# Solution to Exercise 4: Dot Product and Perpendicularity

## 1. Problem Statement

Given the vectors in $\mathbb{R}^3$:
$$
u = (1, 2, -1), \qquad v = (2, -1, 3)
$$

1. Compute the dot product $u \cdot v$ and determine whether $u$ and $v$ are perpendicular.
2. Given the parameterized vector $w = (2, -1, a)$, find the real value of $a$ such that $w$ is perpendicular to $u$.
3. Substitute the calculated value of $a$ and verify that the perpendicularity condition holds.

---

## 2. Theoretical Background and Concepts

1. **Definition of the Dot Product (Inner Product):**
   In Euclidean space $\mathbb{R}^3$, the dot product of two vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$ is defined algebraically as:
   $$
   u \cdot v = u_1 v_1 + u_2 v_2 + u_3 v_3
   $$

2. **Geometric Formula and Orthogonality Criterion:**
   The dot product is related to the angle $\theta \in [0, \pi]$ between non-zero vectors by:
   $$
   u \cdot v = \|u\| \, \|v\| \cos \theta
   $$
   - Since $\|u\| > 0$ and $\|v\| > 0$, we have:
     $$
     u \cdot v = 0 \iff \cos \theta = 0 \iff \theta = \frac{\pi}{2} \text{ rad } (90^\circ)
     $$
   - Two non-zero vectors are **perpendicular (orthogonal)** if and only if their dot product equals zero:
     $$
     u \perp v \iff u \cdot v = 0
     $$
   - If $u \cdot v > 0$, the angle is acute ($\theta < 90^\circ$).
   - If $u \cdot v < 0$, the angle is obtuse ($\theta > 90^\circ$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $u \cdot v$ and Test Perpendicularity

Evaluate the sum of products of corresponding components:
$$
u \cdot v = (1)(2) + (2)(-1) + (-1)(3)
$$
$$
u \cdot v = 2 - 2 - 3 = -3
$$

**Conclusion on Perpendicularity:**
Since $u \cdot v = -3 \ne 0$, vectors $u$ and $v$ are **not perpendicular**. Furthermore, because $u \cdot v < 0$, the angle between $u$ and $v$ is obtuse ($\theta > 90^\circ$).

---

### Step 2: Determine $a$ such that $w \perp u$

We are given $w = (2, -1, a)$. The condition for $w$ to be perpendicular to $u = (1, 2, -1)$ is:
$$
u \cdot w = 0
$$

Substitute the components of $u$ and $w$:
$$
(1)(2) + (2)(-1) + (-1)(a) = 0
$$
Simplify the linear equation:
$$
2 - 2 - a = 0 \implies -a = 0 \implies a = 0
$$

Thus, the required value of the parameter is:
$$
a = 0
$$
and the corresponding vector is:
$$
w = (2, -1, 0)
$$

---

### Step 3: Verification of the Orthogonality of $w$ and $u$

Substitute $w = (2, -1, 0)$ back into the dot product with $u = (1, 2, -1)$:
$$
u \cdot w = (1)(2) + (2)(-1) + (-1)(0) = 2 - 2 + 0 = 0 \quad (\checkmark)
$$

Because $u \cdot w = 0$, the vector $w = (2, -1, 0)$ is perpendicular to $u$.

---

## 4. Verification and Consistency Checks

1. **Pythagorean Theorem Check for $u \perp w$:**
   If $u \perp w$, the vector triangle formed by $u, w$ and their sum $u + w$ must satisfy the Pythagorean theorem:
   $$
   \|u + w\|^2 = \|u\|^2 + \|w\|^2
   $$
   - $\|u\|^2 = 1^2 + 2^2 + (-1)^2 = 1 + 4 + 1 = 6$
   - $\|w\|^2 = 2^2 + (-1)^2 + 0^2 = 4 + 1 + 0 = 5$
   - $u + w = (1 + 2, 2 - 1, -1 + 0) = (3, 1, -1)$
   - $\|u + w\|^2 = 3^2 + 1^2 + (-1)^2 = 9 + 1 + 1 = 11$
   Check:
   $$
   \|u\|^2 + \|w\|^2 = 6 + 5 = 11 = \|u + w\|^2 \quad (\checkmark)
   $$
   The Pythagorean theorem holds, confirming that $\theta = 90^\circ$.

2. **Angle Calculation for $u$ and $v$:**
   - $\|u\| = \sqrt{6}$
   - $\|v\| = \sqrt{2^2 + (-1)^2 + 3^2} = \sqrt{4 + 1 + 9} = \sqrt{14}$
   - $\cos \theta = \frac{u \cdot v}{\|u\|\|v\|} = \frac{-3}{\sqrt{6}\sqrt{14}} = \frac{-3}{\sqrt{84}} = \frac{-3}{2\sqrt{21}} \approx -0.3273$
   - $\theta = \arccos(-0.3273) \approx 109.11^\circ > 90^\circ$ (confirms obtuse angle).
