# Solution to Exercise 13: Undoing a Composite Transformation

## 1. Problem Statement

Given the transformation matrices:
$$
S = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix}, \qquad H = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}
$$
representing a nonuniform scaling and a horizontal shear, respectively.
Let $T = HS$ denote their composition.

1. Find $T^{-1}$ in two different ways:
   - **Method 1:** First compute the matrix product $T = HS$, then compute its inverse directly.
   - **Method 2:** Use the algebraic product formula $(HS)^{-1} = S^{-1} H^{-1}$.
2. Compare the results from both methods.
3. Compute the unreversed product $H^{-1} S^{-1}$ and verify that the incorrect order yields a different matrix.
4. Explain the conceptual rule: *"when undoing a composition of operations, we undo them from the end."*

---

## 2. Theoretical Background and Concepts

1. **Reversal of Composition Order for Inverses:**
   Let $f$ and $g$ be two invertible transformations. In the composite transformation $(g \circ f)(x) = g(f(x))$, function $f$ acts first and $g$ acts second.
   To undo this composition and recover $x$, the outer operation $g$ must be undone first via $g^{-1}$, and the inner operation $f$ must be undone second via $f^{-1}$:
   $$
   (g \circ f)^{-1} = f^{-1} \circ g^{-1}
   $$
   In matrix algebra, with $T = HS$:
   $$
   T^{-1} = (HS)^{-1} = S^{-1} H^{-1}
   $$

2. **Elementary Matrix Inversion:**
   - Diagonal scaling: $S = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \implies S^{-1} = \begin{pmatrix} 1/2 & 0 \\ 0 & 1 \end{pmatrix}$.
   - Horizontal shear: $H = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \implies H^{-1} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix}$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Method 1 — Compute $T$ and Invert Directly

1. **Compute $T = HS$:**
   $$
   T = HS = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(2) + 1(0) & 1(0) + 1(1) \\ 0(2) + 1(0) & 0(0) + 1(1) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 1 \end{pmatrix}
   $$

2. **Compute $T^{-1}$:**
   - Determinant: $\det T = (2)(1) - (1)(0) = 2$.
   - Apply $2 \times 2$ inversion formula:
     $$
     T^{-1} = \frac{1}{2} \begin{pmatrix} 1 & -1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & 1 \end{pmatrix}
     $$

---

### Step 2: Method 2 — Use $(HS)^{-1} = S^{-1} H^{-1}$

1. **Find individual inverses:**
   $$
   S^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 1 \end{pmatrix}, \qquad H^{-1} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix}
   $$

2. **Compute the product $S^{-1} H^{-1}$:**
   $$
   S^{-1} H^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} \frac{1}{2}(1) + 0(0) & \frac{1}{2}(-1) + 0(1) \\ 0(1) + 1(0) & 0(-1) + 1(1) \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & 1 \end{pmatrix}
   $$

---

### Step 3: Comparison

Both methods yield the exact same matrix:
$$
T^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & 1 \end{pmatrix} = S^{-1} H^{-1}
$$

---

### Step 4: Compute the Incorrect Order $H^{-1} S^{-1}$

Multiply the inverses in the unreversed order:
$$
H^{-1} S^{-1} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1\left(\frac{1}{2}\right) + (-1)(0) & 1(0) + (-1)(1) \\ 0\left(\frac{1}{2}\right) + 1(0) & 0(0) + 1(1) \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -1 \\ 0 & 1 \end{pmatrix}
$$

Comparing the two:
$$
H^{-1} S^{-1} = \begin{pmatrix} \frac{1}{2} & -1 \\ 0 & 1 \end{pmatrix} \ne \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & 1 \end{pmatrix} = T^{-1}
$$
The unreversed product fails to produce the inverse matrix ($-\frac{1}{2} \ne -1$).

---

### Step 5: Explanation of the Rule

*"When undoing a composition of operations, we undo them from the end."*

- **Operational Pipeline:**
  In $T = HS$, a vector $x$ first undergoes scaling by $S$, producing an intermediate vector $u = Sx$. Then $u$ undergoes shear by $H$, producing the output $y = Hu = H(Sx)$.
- **Reversal Pipeline:**
  At the end of the forward process, the last transformation active is $H$. To begin retracing our steps, we must first reverse the shear by applying $H^{-1}$, which recovers the intermediate vector $u = H^{-1}y$.
  Only after the shear has been eliminated can we reverse the scaling by applying $S^{-1}$ to $u$, recovering the original vector $x = S^{-1}u = S^{-1}H^{-1}y$.
- If we mistakenly attempted $H^{-1}S^{-1}$, we would be applying the scaling-undoer $S^{-1}$ directly to the sheared output $y$, which alters the vector along the wrong coordinate proportions before the shear is removed.

---

## 4. Verification and Consistency Checks

1. **Test with Forward Composition ($T \cdot T^{-1} = I$):**
   $$
   T \cdot T^{-1} = \begin{pmatrix} 2 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 2(1/2) + 1(0) & 2(-1/2) + 1(1) \\ 0(1/2) + 1(0) & 0(-1/2) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I \quad \checkmark
   $$

2. **Failure Check for Incorrect Order:**
   Multiply $T$ by $H^{-1}S^{-1}$:
   $$
   T (H^{-1}S^{-1}) = \begin{pmatrix} 2 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 2(1/2) + 1(0) & 2(-1) + 1(1) \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} \ne I
   $$
   This explicitly confirms that $H^{-1}S^{-1}$ does not invert $T$.
