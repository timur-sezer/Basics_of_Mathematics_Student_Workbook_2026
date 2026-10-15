# Solution to Exercise 5: Angle Between Vectors

## 1. Problem Statement

Given the vectors in $\mathbb{R}^3$:
$$
u = (1, 1, 0), \qquad v = (1, 0, 1)
$$

1. Use the sign of the dot product $u \cdot v$ to qualitatively predict the type of angle (acute, right, or obtuse) between $u$ and $v$.
2. Compute the exact angle $\theta$ between the vectors (in both radians and degrees).
3. Compare the calculated angle with the initial prediction to confirm consistency.

---

## 2. Theoretical Background and Concepts

1. **Dot Product and the Cosine Formula:**
   The angle $\theta \in [0, \pi]$ between two non-zero vectors $u, v \in \mathbb{R}^3$ satisfies:
   $$
   u \cdot v = \|u\| \, \|v\| \cos \theta \implies \cos \theta = \frac{u \cdot v}{\|u\| \, \|v\|}
   $$

2. **Qualitative Angle Classification by Dot Product Sign:**
   Because vector norms are strictly positive ($\|u\| > 0, \|v\| > 0$), the sign of $\cos \theta$ is identical to the sign of $u \cdot v$:
   - If $u \cdot v > 0 \implies \cos \theta > 0 \implies 0 \le \theta < \frac{\pi}{2}$ ($0^\circ \le \theta < 90^\circ$): **Acute angle**.
   - If $u \cdot v = 0 \implies \cos \theta = 0 \implies \theta = \frac{\pi}{2}$ ($90^\circ$): **Right angle (orthogonal)**.
   - If $u \cdot v < 0 \implies \cos \theta < 0 \implies \frac{\pi}{2} < \theta \le \pi$ ($90^\circ < \theta \le 180^\circ$): **Obtuse angle**.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $u \cdot v$ and Make Qualitative Prediction

Calculate the dot product of $u = (1, 1, 0)$ and $v = (1, 0, 1)$:
$$
u \cdot v = (1)(1) + (1)(0) + (0)(1) = 1 + 0 + 0 = 1
$$

**Qualitative Prediction:**
Since $u \cdot v = 1 > 0$, the cosine of the angle is positive ($\cos \theta > 0$). Therefore, the angle $\theta$ between $u$ and $v$ is predicted to be strictly **acute** ($0^\circ < \theta < 90^\circ$).

---

### Step 2: Compute Vector Lengths and Exact Angle

1. **Length of $u$:**
   $$
   \|u\| = \sqrt{1^2 + 1^2 + 0^2} = \sqrt{1 + 1 + 0} = \sqrt{2}
   $$

2. **Length of $v$:**
   $$
   \|v\| = \sqrt{1^2 + 0^2 + 1^2} = \sqrt{1 + 0 + 1} = \sqrt{2}
   $$

3. **Compute $\cos \theta$:**
   $$
   \cos \theta = \frac{u \cdot v}{\|u\| \, \|v\|} = \frac{1}{\sqrt{2} \cdot \sqrt{2}} = \frac{1}{2}
   $$

4. **Determine $\theta$:**
   Using the standard inverse cosine values:
   $$
   \theta = \arccos\left(\frac{1}{2}\right) = \frac{\pi}{3} \text{ radians}
   $$
   Converting to degrees:
   $$
   \theta = \frac{\pi}{3} \times \frac{180^\circ}{\pi} = 60^\circ
   $$

---

### Step 3: Comparison with Qualitative Prediction

- The exact computed angle is $\theta = 60^\circ$ ($\frac{\pi}{3}$ rad).
- Since $0^\circ < 60^\circ < 90^\circ$, the angle is indeed **acute**.
- The quantitative result $\theta = 60^\circ$ aligns with the qualitative prediction made from the positive sign of $u \cdot v = +1$.

---

## 4. Verification and Consistency Checks

1. **Law of Cosines Check:**
   Consider the triangle formed by $u, v$, and the difference vector $w = u - v$:
   $$
   w = u - v = (1 - 1, 1 - 0, 0 - 1) = (0, 1, -1)
   $$
   Calculate the side lengths squared:
   - $\|w\|^2 = 0^2 + 1^2 + (-1)^2 = 2$
   - $\|u\|^2 = 2$
   - $\|v\|^2 = 2$

   Notice that $\|u\| = \|v\| = \|w\| = \sqrt{2}$. All three side lengths are equal!
   The triangle formed by the origin and the heads of vectors $u$ and $v$ is an **equilateral triangle**. In any Euclidean equilateral triangle, all interior angles are identically $60^\circ$ ($\frac{\pi}{3}$ rad):
   $$
   \cos \theta = \frac{\|u\|^2 + \|v\|^2 - \|w\|^2}{2\|u\|\|v\|} = \frac{2 + 2 - 2}{2(\sqrt{2})(\sqrt{2})} = \frac{2}{4} = \frac{1}{2} \implies \theta = 60^\circ \quad (\checkmark)
   $$

2. **Cross Product Magnitude Check ($\sin \theta$):**
   Compute $u \times v$:
   $$
   u \times v = (1\cdot 1 - 0\cdot 0, 0\cdot 1 - 1\cdot 1, 1\cdot 0 - 1\cdot 1) = (1, -1, -1)
   $$
   $$
   \|u \times v\| = \sqrt{1^2 + (-1)^2 + (-1)^2} = \sqrt{3}
   $$
   Then:
   $$
   \sin \theta = \frac{\|u \times v\|}{\|u\|\|v\|} = \frac{\sqrt{3}}{\sqrt{2}\sqrt{2}} = \frac{\sqrt{3}}{2} \implies \theta = 60^\circ \quad (\checkmark)
   $$
