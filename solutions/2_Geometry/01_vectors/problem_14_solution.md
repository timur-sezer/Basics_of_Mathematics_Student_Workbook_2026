# Solution to Exercise 14: Closest Point on a Line

## 1. Problem Statement

Given the point $P = (4, 1)$ in $\mathbb{R}^2$ and the straight line $L$ passing through the origin $(0, 0)$ with direction vector:
$$
v = (1, 2)
$$

1. Using vector orthogonal projection, find the coordinates of the closest point $Q$ on the line $L$ to the point $P$.
2. Compute the Euclidean distance $d(P, L)$ from point $P$ to the line $L$.
3. Verify that the displacement vector $\overrightarrow{QP}$ is strictly perpendicular to the direction vector $v$ of the line.

---

## 2. Theoretical Background and Concepts

1. **Parametric Equation of a Line Through the Origin:**
   The line $L$ consists of all points whose position vectors are scalar multiples of the direction vector $v$:
   $$
   L = \{ t v \mid t \in \mathbb{R} \}
   $$

2. **Orthogonal Projection as the Minimum Distance Problem:**
   Let $p = \overrightarrow{OP} = (4, 1)$ be the position vector of point $P$. The point $Q \in L$ that minimizes the Euclidean distance $\|p - q\|$ is the **orthogonal projection** of $p$ onto the direction vector $v$:
   $$
   q = \operatorname{proj}_v p = \left(\frac{p \cdot v}{\|v\|^2}\right) v
   $$

3. **Distance from a Point to a Line:**
   The shortest distance from $P$ to $L$ is the length of the perpendicular error vector connecting $Q$ to $P$:
   $$
   d(P, L) = \|\overrightarrow{QP}\| = \|p - q\|
   $$
   By the projection theorem, this vector must be perpendicular to $v$:
   $$
   \overrightarrow{QP} \cdot v = 0
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Find the Closest Point $Q$ on Line $L$

1. **Compute the dot product $p \cdot v$:**
   $$
   p \cdot v = (4)(1) + (1)(2) = 4 + 2 = 6
   $$

2. **Compute the squared norm $\|v\|^2$:**
   $$
   \|v\|^2 = 1^2 + 2^2 = 1 + 4 = 5
   $$

3. **Compute the projection parameter $t^*$:**
   $$
   t^* = \frac{p \cdot v}{\|v\|^2} = \frac{6}{5} = 1.2
   $$

4. **Compute the position vector $q$ of point $Q$:**
   $$
   q = t^* v = \frac{6}{5} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} \frac{6}{5} \\ \frac{12}{5} \end{pmatrix} = \begin{pmatrix} 1.2 \\ 2.4 \end{pmatrix}
   $$

Thus, the closest point on the line $L$ is:
$$
Q = \left(\frac{6}{5}, \frac{12}{5}\right) = (1.2, 2.4)
$$

---

### Step 2: Compute the Distance from $P$ to the Line $L$

1. **Construct the error displacement vector $\overrightarrow{QP}$:**
   $$
   \overrightarrow{QP} = p - q = \begin{pmatrix} 4 \\ 1 \end{pmatrix} - \begin{pmatrix} \frac{6}{5} \\ \frac{12}{5} \end{pmatrix}
   $$
   Express $p$ with a common denominator of $5$:
   $$
   \overrightarrow{QP} = \begin{pmatrix} \frac{20}{5} - \frac{6}{5} \\ \frac{5}{5} - \frac{12}{5} \end{pmatrix} = \begin{pmatrix} \frac{14}{5} \\ -\frac{7}{5} \end{pmatrix} = \begin{pmatrix} 2.8 \\ -1.4 \end{pmatrix}
   $$

2. **Compute the Euclidean norm of $\overrightarrow{QP}$:**
   $$
   d(P, L) = \|\overrightarrow{QP}\| = \sqrt{\left(\frac{14}{5}\right)^2 + \left(-\frac{7}{5}\right)^2} = \sqrt{\frac{196}{25} + \frac{49}{25}} = \sqrt{\frac{245}{25}}
   $$
   Simplify the radical:
   $$
   \sqrt{\frac{245}{25}} = \frac{\sqrt{49 \times 5}}{5} = \frac{7\sqrt{5}}{5} = \frac{7}{\sqrt{5}}
   $$
   Numerically:
   $$
   d(P, L) = \frac{7\sqrt{5}}{5} \approx 3.1305
   $$

---

### Step 3: Verify Perpendicularity of $\overrightarrow{QP}$ to $v$

Calculate the dot product of $\overrightarrow{QP} = \left(\frac{14}{5}, -\frac{7}{5}\right)$ and $v = (1, 2)$:
$$
\overrightarrow{QP} \cdot v = \left(\frac{14}{5}\right)(1) + \left(-\frac{7}{5}\right)(2) = \frac{14 - 14}{5} = \frac{0}{5} = 0 \quad (\checkmark)
$$

The dot product is identically zero, rigorously verifying that the displacement vector is perpendicular to the direction of the line.

---

## 4. Verification and Consistency Checks

1. **Standard Point-Line Distance Formula Check:**
   - The line $L$ passes through $(0, 0)$ with direction $(1, 2)$, so its slope is $m = \frac{2}{1} = 2$.
   - General Cartesian form: $y = 2x \implies 2x - y = 0$.
   - Distance from point $(x_0, y_0) = (4, 1)$ to line $Ax + By + C = 0$:
     $$
     d = \frac{|A x_0 + B y_0 + C|}{\sqrt{A^2 + B^2}} = \frac{|2(4) - 1(1) + 0|}{\sqrt{2^2 + (-1)^2}} = \frac{|8 - 1|}{\sqrt{4 + 1}} = \frac{7}{\sqrt{5}} = \frac{7\sqrt{5}}{5} \quad (\checkmark)
     $$
   The standard analytic geometry formula yields the exact same distance.

2. **Pythagorean Theorem Check on Triangle $OPQ$:**
   - $\|p\|^2 = 4^2 + 1^2 = 17$
   - $\|q\|^2 = \left(\frac{6}{5}\right)^2 + \left(\frac{12}{5}\right)^2 = \frac{36 + 144}{25} = \frac{180}{25} = \frac{36}{5} = 7.2$
   - $\|\overrightarrow{QP}\|^2 = \frac{245}{25} = \frac{49}{5} = 9.8$
   Check:
   $$
   \|q\|^2 + \|\overrightarrow{QP}\|^2 = 7.2 + 9.8 = 17.0 = \|p\|^2 \quad (\checkmark)
   $$
   The Pythagorean relation $\|q\|^2 + \|\overrightarrow{QP}\|^2 = \|p\|^2$ holds.
