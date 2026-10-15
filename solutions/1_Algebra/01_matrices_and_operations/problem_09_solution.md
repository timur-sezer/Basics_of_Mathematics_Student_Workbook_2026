# Solution to Exercise 9: Composing Transformations

## 1. Problem Statement

Given the transformation matrices:
$$
S = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix}, \qquad R = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}
$$
where $S$ represents a nonuniform scaling (horizontal stretch by a factor of $2$) and $R$ represents a $90^\circ$ counterclockwise rotation.

For the vector:
$$
x = \begin{pmatrix} 1 \\ 2 \end{pmatrix}
$$

1. Compute $RSx$.
2. Compute $SRx$.
3. Compare the results and explain geometrically why the order of these transformations matters.

---

## 2. Theoretical Background and Concepts

1. **Composition of Linear Transformations:**
   Let $T_S(v) = Sv$ and $T_R(v) = Rv$ be linear transformations on $\mathbb{R}^2$.
   - The composition $(T_R \circ T_S)(x)$ applies $T_S$ first and then $T_R$, represented by the matrix product $(RS)x = R(Sx)$.
   - The composition $(T_S \circ T_R)(x)$ applies $T_R$ first and then $T_S$, represented by the matrix product $(SR)x = S(Rx)$.

2. **Geometric Actions:**
   - **Nonuniform scaling $S$:** Maps $\begin{pmatrix} u \\ v \end{pmatrix} \mapsto \begin{pmatrix} 2u \\ v \end{pmatrix}$, doubling the horizontal coordinate while preserving the vertical coordinate.
   - **Rotation $R$ by $90^\circ$:** Maps $\begin{pmatrix} u \\ v \end{pmatrix} \mapsto \begin{pmatrix} -v \\ u \end{pmatrix}$, swinging the positive $x$-axis to the positive $y$-axis and the positive $y$-axis to the negative $x$-axis.

3. **Geometric Noncommutativity:**
   Scaling is directional (it acts along the fixed coordinate axes). When a rotation is performed first, it reorients the object relative to those fixed axes. Consequently, stretching along the $x$-axis afterwards acts on components that originally pointed along the $y$-axis.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $RSx$ (Scale first, then Rotate)

1. **First transformation: $Sx$**
   $$
   Sx = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} 2(1) + 0(2) \\ 0(1) + 1(2) \end{pmatrix} = \begin{pmatrix} 2 \\ 2 \end{pmatrix}
   $$
   *(The horizontal coordinate was doubled from $1$ to $2$, while the vertical coordinate remained $2$)*.

2. **Second transformation: $R(Sx)$**
   $$
   RSx = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 2 \\ 2 \end{pmatrix} = \begin{pmatrix} 0(2) + (-1)(2) \\ 1(2) + 0(2) \end{pmatrix} = \begin{pmatrix} -2 \\ 2 \end{pmatrix}
   $$

Thus:
$$
RSx = \begin{pmatrix} -2 \\ 2 \end{pmatrix}
$$

---

### Step 2: Compute $SRx$ (Rotate first, then Scale)

1. **First transformation: $Rx$**
   $$
   Rx = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} 0(1) + (-1)(2) \\ 1(1) + 0(2) \end{pmatrix} = \begin{pmatrix} -2 \\ 1 \end{pmatrix}
   $$
   *(The vector $(1, 2)$ was rotated $90^\circ$ counterclockwise into $(-2, 1)$)*.

2. **Second transformation: $S(Rx)$**
   $$
   SRx = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -2 \\ 1 \end{pmatrix} = \begin{pmatrix} 2(-2) + 0(1) \\ 0(-2) + 1(1) \end{pmatrix} = \begin{pmatrix} -4 \\ 1 \end{pmatrix}
   $$

Thus:
$$
SRx = \begin{pmatrix} -4 \\ 1 \end{pmatrix}
$$

---

### Step 3: Comparison and Geometric Explanation

Comparing the two outputs:
$$
RSx = \begin{pmatrix} -2 \\ 2 \end{pmatrix} \ne \begin{pmatrix} -4 \\ 1 \end{pmatrix} = SRx
$$

**Geometric Explanation:**
- In the sequence $RSx$, the initial vector $\begin{pmatrix} 1 \\ 2 \end{pmatrix}$ has its horizontal component stretched first ($1 \to 2$). Then the rotation turns this stretched horizontal component into the vertical component ($y = 2$), while sending the unstretched vertical component $2$ to the negative horizontal direction ($x = -2$). The result is $\begin{pmatrix} -2 \\ 2 \end{pmatrix}$.
- In the sequence $SRx$, the rotation occurs first, sending the original vertical component $2$ to become the new horizontal component $-2$. When the horizontal stretch $S$ is applied second, it doubles this new horizontal component (stretching $-2$ to $-4$). The original horizontal component $1$, having been rotated into the vertical direction, receives no scaling at all. The result is $\begin{pmatrix} -4 \\ 1 \end{pmatrix}$.
- Because the scaling transformation $S$ is anisotropic (nonuniform, acting exclusively along the horizontal axis), rotating before vs. after fundamentally alters which physical direction of the original vector gets scaled. Hence, the order of composition strictly matters.

---

## 4. Verification and Consistency Checks

1. **Matrix Product Verification:**
   Compute the composed transformation matrices directly:
   - Composed matrix $RS$:
     $$
     RS = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 0 & -1 \\ 2 & 0 \end{pmatrix}
     $$
     Applying to $x$:
     $$
     (RS)x = \begin{pmatrix} 0 & -1 \\ 2 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} -2 \\ 2 \end{pmatrix} \quad \checkmark
     $$
   - Composed matrix $SR$:
     $$
     SR = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & -2 \\ 1 & 0 \end{pmatrix}
     $$
     Applying to $x$:
     $$
     (SR)x = \begin{pmatrix} 0 & -2 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} -4 \\ 1 \end{pmatrix} \quad \checkmark
     $$
   Associativity of matrix multiplication $(R(Sx) = (RS)x)$ confirms both calculations.

2. **Area / Determinant Invariance Check:**
   - $\det(S) = 2 \cdot 1 - 0 = 2$ (doubles areas).
   - $\det(R) = 0 - (-1)(1) = 1$ (preserves areas).
   - $\det(RS) = \det(SR) = 2 \cdot 1 = 2$.
   Both transformations scale area by $2$, confirming consistency with geometric transformation theory.

