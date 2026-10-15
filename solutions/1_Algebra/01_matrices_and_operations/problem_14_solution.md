# Solution to Exercise 14: Rotation Matrices

## 1. Problem Statement

The matrix representing a counterclockwise rotation about the origin through an angle $\theta$ is:
$$
R(\theta) = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}
$$

1. Compute the matrix product $R(\alpha) R(\beta)$.
2. Use the angle-sum trigonometric identities for sine and cosine to prove that:
   $$
   R(\alpha) R(\beta) = R(\alpha + \beta)
   $$
3. Explain the result geometrically.

---

## 2. Theoretical Background and Concepts

1. **Rotation Matrices in $\mathbb{R}^2$:**
   A rotation of the Euclidean plane about the origin by an angle $\theta$ (measured counterclockwise) preserves distances and angles. It maps the standard basis vectors as follows:
   $$
   \mathbf{e}_1 = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \mapsto \begin{pmatrix} \cos\theta \\ \sin\theta \end{pmatrix}, \qquad \mathbf{e}_2 = \begin{pmatrix} 0 \\ 1 \end{pmatrix} \mapsto \begin{pmatrix} -\sin\theta \\ \cos\theta \end{pmatrix}
   $$
   Placing these transformed vectors as columns gives the standard rotation matrix $R(\theta)$.

2. **Trigonometric Angle-Sum Identities:**
   For any angles $\alpha$ and $\beta$:
   $$
   \cos(\alpha + \beta) = \cos\alpha \cos\beta - \sin\alpha \sin\beta
   $$
   $$
   \sin(\alpha + \beta) = \sin\alpha \cos\beta + \cos\alpha \sin\beta
   $$

3. **Group Structure of Rotations:**
   The set of all rotations forms the Special Orthogonal Group $SO(2)$. Matrix multiplication corresponds to composition of rotations. Since angle addition is commutative ($\alpha + \beta = \beta + \alpha$), two-dimensional rotation matrices commute: $R(\alpha)R(\beta) = R(\beta)R(\alpha)$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Multiply $R(\alpha)$ by $R(\beta)$

Write out both rotation matrices:
$$
R(\alpha) = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix}, \qquad R(\beta) = \begin{pmatrix} \cos\beta & -\sin\beta \\ \sin\beta & \cos\beta \end{pmatrix}
$$

Compute the product $R(\alpha) R(\beta)$:
$$
R(\alpha) R(\beta) = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix} \begin{pmatrix} \cos\beta & -\sin\beta \\ \sin\beta & \cos\beta \end{pmatrix}
$$

Compute each entry:
- **Entry $(1, 1)$:**
  $$
  (\cos\alpha)(\cos\beta) + (-\sin\alpha)(\sin\beta) = \cos\alpha \cos\beta - \sin\alpha \sin\beta
  $$
- **Entry $(1, 2)$:**
  $$
  (\cos\alpha)(-\sin\beta) + (-\sin\alpha)(\cos\beta) = -(\sin\alpha \cos\beta + \cos\alpha \sin\beta)
  $$
- **Entry $(2, 1)$:**
  $$
  (\sin\alpha)(\cos\beta) + (\cos\alpha)(\sin\beta) = \sin\alpha \cos\beta + \cos\alpha \sin\beta
  $$
- **Entry $(2, 2)$:**
  $$
  (\sin\alpha)(-\sin\beta) + (\cos\alpha)(\cos\beta) = \cos\alpha \cos\beta - \sin\alpha \sin\beta
  $$

Thus:
$$
R(\alpha) R(\beta) = \begin{pmatrix}
\cos\alpha \cos\beta - \sin\alpha \sin\beta & -(\sin\alpha \cos\beta + \cos\alpha \sin\beta) \\
\sin\alpha \cos\beta + \cos\alpha \sin\beta & \cos\alpha \cos\beta - \sin\alpha \sin\beta
\end{pmatrix}
$$

---

### Step 2: Apply the Angle-Sum Identities

Substitute the trigonometric identities:
1. Replace $\cos\alpha \cos\beta - \sin\alpha \sin\beta$ with $\cos(\alpha + \beta)$.
2. Replace $\sin\alpha \cos\beta + \cos\alpha \sin\beta$ with $\sin(\alpha + \beta)$.

The product matrix simplifies to:
$$
R(\alpha) R(\beta) = \begin{pmatrix} \cos(\alpha + \beta) & -\sin(\alpha + \beta) \\ \sin(\alpha + \beta) & \cos(\alpha + \beta) \end{pmatrix}
$$
By definition of the rotation matrix evaluated at angle $\alpha + \beta$, this is:
$$
R(\alpha) R(\beta) = R(\alpha + \beta)
$$
This establishes the required identity.

---

### Step 3: Geometric Explanation

- The matrix $R(\beta)$ rotates any point in the plane by angle $\beta$ counterclockwise around the origin.
- The matrix $R(\alpha)$ subsequently rotates that resulting point by an additional angle $\alpha$ counterclockwise around the origin.
- Since both transformations are rotations about the exact same fixed point (the origin), their composition results in a single net rotation through total angle $\alpha + \beta$.
- Moreover, because scalar angle addition is commutative ($\alpha + \beta = \beta + \alpha$):
  $$
  R(\alpha) R(\beta) = R(\alpha + \beta) = R(\beta + \alpha) = R(\beta) R(\alpha)
  $$
  This geometrically explains why $2D$ rotations commute with each other, in contrast to general matrix multiplication.

---

## 4. Verification and Consistency Checks

1. **Determinant Multiplicative Check:**
   - $\det(R(\theta)) = \cos^2\theta - (-\sin^2\theta) = \cos^2\theta + \sin^2\theta = 1$.
   - $\det(R(\alpha) R(\beta)) = \det(R(\alpha)) \cdot \det(R(\beta)) = 1 \cdot 1 = 1$.
   - $\det(R(\alpha + \beta)) = \cos^2(\alpha + \beta) + \sin^2(\alpha + \beta) = 1$.
   The determinant is consistently $1$, confirming that rotations preserve orientation and area.

2. **Inverse Rotation Check:**
   Choosing $\beta = -\alpha$:
   $$
   R(\alpha) R(-\alpha) = R(\alpha + (-\alpha)) = R(0) = \begin{pmatrix} \cos 0 & -\sin 0 \\ \sin 0 & \cos 0 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I
   $$
   Since $\cos(-\alpha) = \cos\alpha$ and $\sin(-\alpha) = -\sin\alpha$, we observe that $R(-\alpha) = R(\alpha)^T$.
   Thus $R(\alpha)^{-1} = R(\alpha)^T$, proving that $R(\alpha)$ is an orthogonal matrix.
