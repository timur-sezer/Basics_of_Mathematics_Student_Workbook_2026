# Solution to Exercise 8: Determinant of a Product

## 1. Problem Statement

Let $A$ and $B$ be square matrices of the same size such that:
$$
\det A = 3, \qquad \det B = -5
$$

1. Compute $\det(AB)$.
2. Compute $\det(BA)$.
3. Determine whether $\det(A^{-1}B)$ exists, and if so, compute its value.
4. Explain why $\det(AB) = \det(BA)$ even though matrix multiplication is noncommutative ($AB \ne BA$ in general).

---

## 2. Theoretical Background and Concepts

1. **Multiplicative Property of Determinants:**
   For any square matrices $M$ and $N$ of identical dimensions:
   $$
   \det(MN) = \det(M) \det(N)
   $$

2. **Determinant of an Inverse Matrix:**
   A matrix $M$ is invertible if and only if $\det(M) \ne 0$.
   Since $M M^{-1} = I$ and $\det(I) = 1$:
   $$
   \det(M M^{-1}) = \det(M) \det(M^{-1}) = 1 \implies \det(M^{-1}) = \frac{1}{\det M}
   $$

3. **Commutativity of the Underlying Field:**
   While matrix multiplication in $M_n(\mathbb{R})$ is noncommutative, the values produced by the determinant function are scalars belonging to $\mathbb{R}$. Multiplication of real numbers is commutative: for any $x, y \in \mathbb{R}$, $xy = yx$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $\det(AB)$

Using the multiplicative property of determinants:
$$
\det(AB) = \det A \cdot \det B
$$

Substituting the given values $\det A = 3$ and $\det B = -5$:
$$
\det(AB) = 3 \cdot (-5) = -15
$$

---

### Step 2: Compute $\det(BA)$

Using the multiplicative property:
$$
\det(BA) = \det B \cdot \det A
$$

Substituting the given values:
$$
\det(BA) = (-5) \cdot 3 = -15
$$

---

### Step 3: Existence and Computation of $\det(A^{-1}B)$

1. **Existence:**
   Matrix $A$ is invertible if and only if $\det A \ne 0$.
   Since $\det A = 3 \ne 0$, the inverse matrix $A^{-1}$ exists.
   Consequently, the product $A^{-1}B$ is well-defined and its determinant exists.

2. **Calculation:**
   First, find the determinant of the inverse matrix $A^{-1}$:
   $$
   \det(A^{-1}) = \frac{1}{\det A} = \frac{1}{3}
   $$
   Now apply the product rule to $A^{-1}B$:
   $$
   \det(A^{-1}B) = \det(A^{-1}) \cdot \det B = \frac{1}{3} \cdot (-5) = -\frac{5}{3}
   $$

---

### Step 4: Explanation of Why $\det(AB) = \det(BA)$

Even though matrix multiplication does not commute ($AB \ne BA$):
1. The determinant function $\det: M_n(\mathbb{R}) \to \mathbb{R}$ maps matrix objects into the real numbers.
2. In the real number field, scalar multiplication is commutative:
   $$
   \det(AB) = \det(A)\det(B) = \det(B)\det(A) = \det(BA)
   $$
3. Geometrically, the determinant measures the factor by which oriented volumes are scaled. Transforming space by $B$ and then by $A$ multiplies volumes by $(-5) \times 3 = -15$. Reversing the order to $A$ followed by $B$ multiplies volumes by $3 \times (-5) = -15$. While individual vectors may land in completely different positions, the total volume scaling and orientation reversal are identical.

---

## 4. Verification and Consistency Checks

1. **Similarity Invariance Check:**
   If $A$ and $B$ are invertible, $AB$ and $BA$ are similar matrices:
   $$
   BA = A^{-1} (AB) A
   $$
   Since similar matrices represent the same linear transformation in different coordinate bases, they share the exact same determinant:
   $$
   \det(BA) = \det(A^{-1}(AB)A) = \det(A^{-1})\det(AB)\det(A) = \frac{1}{\det A} \det(AB) \det A = \det(AB) \quad \checkmark
   $$

2. **Inverse Product Consistency:**
   Using the fact that $\det(A \cdot (A^{-1}B)) = \det(B)$:
   $$
   \det(A) \cdot \det(A^{-1}B) = 3 \cdot \left(-\frac{5}{3}\right) = -5 = \det B \quad \checkmark
   $$
