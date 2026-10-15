# Solution to Exercise 15: Comparing Directions Using the Cosine of the Angle

## 1. Problem Statement

Given three vectors in $\mathbb{R}^3$:
$$
a = (1, 2, 1), \qquad b = (2, 4, 2), \qquad c = (2, 0, 3)
$$

1. For each of the three distinct pairs of vectors ($(a, b)$, $(a, c)$, and $(b, c)$), compute the normalized inner product:
   $$
   \cos \theta = \frac{u \cdot v}{\|u\| \, \|v\|}
   $$
2. Determine the corresponding angles between each pair and order the pairs in order of strictly increasing angle.
3. Explain why the value for the pair $(a, b)$ is exactly $1$, even though $a$ and $b$ have different lengths.

---

## 2. Theoretical Background and Concepts

1. **Cosine Formula and Normalized Inner Product:**
   For any two non-zero vectors $u, v \in \mathbb{R}^n$, Cauchy–Schwarz inequality guarantees:
   $$
   -1 \le \frac{u \cdot v}{\|u\| \, \|v\|} \le 1
   $$
   The angle $\theta \in [0, \pi]$ between them is defined by:
   $$
   \cos \theta = \frac{u \cdot v}{\|u\| \, \|v\|} = \left(\frac{u}{\|u\|}\right) \cdot \left(\frac{v}{\|v\|}\right)
   $$
   The normalized inner product corresponds geometrically to the dot product of the respective **unit direction vectors** $\hat{u}$ and $\hat{v}$.

2. **Invariance Under Positive Scalar Scaling:**
   Let $v = \lambda u$ for some positive scalar $\lambda > 0$. Then:
   $$
   \frac{u \cdot (\lambda u)}{\|u\| \, \|\lambda u\|} = \frac{\lambda (u \cdot u)}{\|u\| (\lambda \|u\|)} = \frac{\lambda \|u\|^2}{\lambda \|u\|^2} = 1
   $$
   The angle is $\theta = \arccos(1) = 0$. Thus, multiplying a vector by a positive constant modifies its magnitude, but leaves its spatial direction and angle with any other vector completely invariant.

3. **Angle Ordering:**
   Since the cosine function is strictly decreasing on the interval $[0, \pi]$:
   $$
   \theta_1 < \theta_2 \iff \cos \theta_1 > \cos \theta_2
   $$
   A larger cosine value corresponds to a smaller angle between the vectors.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute Vector Norms

1. **Norm of $a = (1, 2, 1)$:**
   $$
   \|a\| = \sqrt{1^2 + 2^2 + 1^2} = \sqrt{1 + 4 + 1} = \sqrt{6}
   $$

2. **Norm of $b = (2, 4, 2)$:**
   $$
   \|b\| = \sqrt{2^2 + 4^2 + 2^2} = \sqrt{4 + 16 + 4} = \sqrt{24} = 2\sqrt{6}
   $$

3. **Norm of $c = (2, 0, 3)$:**
   $$
   \|c\| = \sqrt{2^2 + 0^2 + 3^2} = \sqrt{4 + 0 + 9} = \sqrt{13}
   $$

---

### Step 2: Compute $\cos \theta$ for Each Pair

#### Pair 1: $(a, b)$
- Dot product:
  $$
  a \cdot b = (1)(2) + (2)(4) + (1)(2) = 2 + 8 + 2 = 12
  $$
- Product of norms:
  $$
  \|a\| \, \|b\| = \sqrt{6} \cdot 2\sqrt{6} = 2 \cdot 6 = 12
  $$
- Normalized value:
  $$
  \cos \theta_{ab} = \frac{a \cdot b}{\|a\| \, \|b\|} = \frac{12}{12} = 1
  $$
- Angle:
  $$
  \theta_{ab} = \arccos(1) = 0 \text{ rad} = 0^\circ
  $$

---

#### Pair 2: $(a, c)$
- Dot product:
  $$
  a \cdot c = (1)(2) + (2)(0) + (1)(3) = 2 + 0 + 3 = 5
  $$
- Product of norms:
  $$
  \|a\| \, \|c\| = \sqrt{6} \cdot \sqrt{13} = \sqrt{78}
  $$
- Normalized value:
  $$
  \cos \theta_{ac} = \frac{a \cdot c}{\|a\| \, \|c\|} = \frac{5}{\sqrt{78}} \approx \frac{5}{8.83176} \approx 0.5661
  $$
- Angle:
  $$
  \theta_{ac} = \arccos\left(\frac{5}{\sqrt{78}}\right) \approx 0.9691 \text{ rad} \approx 55.52^\circ
  $$

---

#### Pair 3: $(b, c)$
- Dot product:
  $$
  b \cdot c = (2)(2) + (4)(0) + (2)(3) = 4 + 0 + 6 = 10
  $$
- Product of norms:
  $$
  \|b\| \, \|c\| = 2\sqrt{6} \cdot \sqrt{13} = 2\sqrt{78}
  $$
- Normalized value:
  $$
  \cos \theta_{bc} = \frac{b \cdot c}{\|b\| \, \|c\|} = \frac{10}{2\sqrt{78}} = \frac{5}{\sqrt{78}} \approx 0.5661
  $$
- Angle:
  $$
  \theta_{bc} = \arccos\left(\frac{5}{\sqrt{78}}\right) \approx 0.9691 \text{ rad} \approx 55.52^\circ
  $$

---

### Step 3: Order Pairs by Increasing Angle

Comparing the angles:
1. $\theta_{ab} = 0^\circ$ ($\cos \theta = 1.0$)
2. $\theta_{ac} = \theta_{bc} \approx 55.52^\circ$ ($\cos \theta = \frac{5}{\sqrt{78}} \approx 0.5661$)

**Ordered sequence of pairs (from smallest angle to largest angle):**
$$
\text{Pair } (a, b) \quad [0^\circ] \quad < \quad \text{Pairs } (a, c) \text{ and } (b, c) \quad [55.52^\circ \text{ tied}]
$$

---

### Step 4: Why $\cos \theta_{ab} = 1$ Despite Different Lengths

1. **Collinearity and Orientation:**
   Observe the relationship between vectors $a$ and $b$:
   $$
   b = \begin{pmatrix} 2 \\ 4 \\ 2 \end{pmatrix} = 2 \begin{pmatrix} 1 \\ 2 \\ 1 \end{pmatrix} = 2a
   $$
   Vector $b$ is a strictly positive scalar multiple ($k = +2 > 0$) of vector $a$.
2. **Separation of Geometry from Scale:**
   - The formula $\frac{u \cdot v}{\|u\|\|v\|} = \left(\frac{u}{\|u\|}\right) \cdot \left(\frac{v}{\|v\|}\right)$ first divides each vector by its length, projecting both vectors onto the unit sphere $S^2$.
   - The unit direction vector of $a$ is $\hat{a} = \frac{1}{\sqrt{6}}(1, 2, 1)$.
   - The unit direction vector of $b$ is $\hat{b} = \frac{1}{2\sqrt{6}}(2, 4, 2) = \frac{1}{\sqrt{6}}(1, 2, 1) = \hat{a}$.
   - Because $a$ and $b$ point in the exact same spatial direction, their unit vectors are identical ($\hat{a} = \hat{b}$).
   - The dot product of any unit vector with itself is identically $1$:
     $$
     \hat{a} \cdot \hat{b} = \hat{a} \cdot \hat{a} = \|\hat{a}\|^2 = 1
     $$
   - Vector length indicates how far one travels, whereas the angle indicates in which direction one points. The cosine formula isolates direction and is completely invariant under positive magnitude scaling.

---

## 4. Verification and Consistency Checks

1. **Cross Product Parallelism Check for $(a, b)$:**
   For non-zero vectors, a vanishing cross product $\|a \times b\| = 0$ indicates collinearity, meaning the angle is either $\theta = 0^\circ$ (same direction) or $\theta = 180^\circ$ (opposite direction):
   $$
   a \times b = \det \begin{pmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 2 & 1 \\ 2 & 4 & 2 \end{pmatrix} = \begin{pmatrix} (2)(2) - (1)(4) \\ -((1)(2) - (1)(2)) \\ (1)(4) - (2)(2) \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}
   $$
   The zero cross product establishes parallelism. To distinguish identical orientation ($\theta = 0^\circ$) from opposite orientation ($\theta = 180^\circ$), we observe that $b = +2a$ with a strictly positive proportionality factor $k = +2 > 0$ (and correspondingly $a \cdot b = 12 > 0$). This confirms conclusively that $\theta_{ab} = 0^\circ$.

2. **Geometric Equivalence of Angles with $c$:**
   Because $b = 2a$, the ray from the origin through $b$ is identical to the ray through $a$. Therefore, the geometric angle between ray $a$ and vector $c$ must be identical to the angle between ray $b$ and vector $c$:
   $$
   \theta_{ac} = \theta_{bc} = \arccos\left(\frac{5}{\sqrt{78}}\right) \approx 55.52^\circ \quad (\checkmark)
   $$
