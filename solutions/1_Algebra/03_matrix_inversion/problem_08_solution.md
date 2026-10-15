# Solution to Exercise 8: Inverse of a Transformation

## 1. Problem Statement

The matrix:
$$
S = \begin{pmatrix} 2 & 0 \\ 0 & \frac{1}{2} \end{pmatrix}
$$
describes a linear scaling (squeeze mapping) of the Cartesian plane.

1. Find the inverse matrix $S^{-1}$.
2. Explain geometrically what the original transformation $S$ and its inverse transformation $S^{-1}$ do to the plane.
3. Test and verify the sequential action of the pair $S$ and $S^{-1}$ on a simple test vector.

---

## 2. Theoretical Background and Concepts

1. **Inversion of Diagonal Scaling Matrices:**
   A diagonal matrix $D = \operatorname{diag}(d_1, d_2, \dots, d_n)$ scales the coordinate axes independently by the factors $d_i$.
   If all $d_i \ne 0$, its inverse is simply:
   $$
   D^{-1} = \operatorname{diag}\left(\frac{1}{d_1}, \frac{1}{d_2}, \dots, \frac{1}{d_n}\right)
   $$

2. **Geometric Role of the Inverse:**
   A linear transformation $T_S(v) = Sv$ maps an input geometric figure to an output figure.
   The inverse transformation $T_S^{-1}(w) = S^{-1}w$ reverses this mapping, returning every point in the transformed space back to its original pre-image position:
   $$
   S^{-1}(S v) = I v = v
   $$

3. **Area Preservation (Squeeze Mapping):**
   Since $\det S = 2 \cdot \frac{1}{2} = 1$, the transformation preserves areas. Such anisotropic scalings with unit determinant are known as **squeeze mappings** (hyperbolic rotations).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Find the Inverse Matrix $S^{-1}$

Matrix $S$ is diagonal:
$$
S = \begin{pmatrix} 2 & 0 \\ 0 & \frac{1}{2} \end{pmatrix}
$$

1. **Determinant:**
   $$
   \det S = (2)\left(\frac{1}{2}\right) - (0)(0) = 1 \ne 0
   $$

2. **Inverting the diagonal entries:**
   - First diagonal entry: $\frac{1}{2}$
   - Second diagonal entry: $\frac{1}{1/2} = 2$

Thus:
$$
S^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix}
$$

---

### Step 2: Geometric Interpretation

1. **Action of $S$:**
   $$
   S \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 2x \\ \frac{1}{2}y \end{pmatrix}
   $$
   - The horizontal coordinate $x$ is stretched by a factor of $2$ (doubling width).
   - The vertical coordinate $y$ is compressed by a factor of $\frac{1}{2}$ (halving height).
   - A unit square with corners at $(0,0), (1,0), (1,1), (0,1)$ is deformed into a rectangle of width $2$ and height $1/2$, preserving the total area of $1$.

2. **Action of $S^{-1}$:**
   $$
   S^{-1} \begin{pmatrix} u \\ v \end{pmatrix} = \begin{pmatrix} \frac{1}{2}u \\ 2v \end{pmatrix}
   $$
   - The horizontal coordinate $u$ is compressed by a factor of $\frac{1}{2}$ (undoing the horizontal stretch).
   - The vertical coordinate $v$ is stretched by a factor of $2$ (undoing the vertical compression).
   - The deformed rectangle of width $2$ and height $1/2$ is mapped back into the original unit square.

---

### Step 3: Test on a Concrete Vector

Choose the simple test vector:
$$
v = \begin{pmatrix} 2 \\ 4 \end{pmatrix}
$$

1. **Apply the forward transformation $S$:**
   $$
   w = S v = \begin{pmatrix} 2 & 0 \\ 0 & \frac{1}{2} \end{pmatrix} \begin{pmatrix} 2 \\ 4 \end{pmatrix} = \begin{pmatrix} 2(2) + 0(4) \\ 0(2) + \frac{1}{2}(4) \end{pmatrix} = \begin{pmatrix} 4 \\ 2 \end{pmatrix}
   $$
   *(The vector $(2, 4)$ has been stretched horizontally to $4$ and compressed vertically to $2$)*.

2. **Apply the inverse transformation $S^{-1}$ to $w$:**
   $$
   S^{-1} w = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 4 \\ 2 \end{pmatrix} = \begin{pmatrix} \frac{1}{2}(4) + 0(2) \\ 0(4) + 2(2) \end{pmatrix} = \begin{pmatrix} 2 \\ 4 \end{pmatrix} = v
   $$

The composed action $S^{-1}(Sv)$ restores the initial vector $v$ with perfect accuracy.

---

## 4. Verification and Consistency Checks

1. **Algebraic Matrix Product Check:**
   $$
   S S^{-1} = \begin{pmatrix} 2 & 0 \\ 0 & \frac{1}{2} \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 2 \cdot \frac{1}{2} & 0 \\ 0 & \frac{1}{2} \cdot 2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I \quad \checkmark
   $$
   $$
   S^{-1} S = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & \frac{1}{2} \end{pmatrix} = \begin{pmatrix} \frac{1}{2} \cdot 2 & 0 \\ 0 & 2 \cdot \frac{1}{2} \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I \quad \checkmark
   $$

2. **Determinant Multiplicative Check:**
   - $\det(S) = 2 \cdot \frac{1}{2} = 1$.
   - $\det(S^{-1}) = \frac{1}{2} \cdot 2 = 1$.
   - $\det(S)\det(S^{-1}) = 1 \cdot 1 = 1 = \det(I) \quad \checkmark$.
