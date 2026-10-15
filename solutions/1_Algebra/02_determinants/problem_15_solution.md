# Solution to Exercise 15: Combining Determinant Properties

## 1. Problem Statement

Let $A$ and $B$ be invertible $2 \times 2$ matrices with determinants:
$$
\det A = -2, \qquad \det B = 3
$$

Without finding the individual entries of the matrices:
1. Compute the value of $\det\left(B^{-1} A^T B\right)$.
2. State all determinant properties used, in the order of their application.
3. Explain why the factors involving matrix $B$ cancel out.

---

## 2. Theoretical Background and Concepts

1. **Multiplicative Property:**
   For any square matrices of the same size:
   $$
   \det(M_1 M_2 \cdots M_k) = \det(M_1) \det(M_2) \cdots \det(M_k)
   $$

2. **Inverse Matrix Property:**
   If a matrix $M$ is invertible ($\det M \ne 0$), then:
   $$
   \det(M^{-1}) = \frac{1}{\det M} = (\det M)^{-1}
   $$

3. **Transpose Property:**
   Transposition does not affect the determinant:
   $$
   \det(M^T) = \det(M)
   $$

4. **Similarity Invariance:**
   Two matrices $M$ and $M'$ are **similar** if there exists an invertible matrix $P$ such that $M' = P^{-1} M P$. Similarity corresponds geometrically to representing the exact same linear operator with respect to different coordinate bases. A fundamental theorem of linear algebra establishes that **the determinant is a similarity invariant**:
   $$
   \det(P^{-1} M P) = \det(M)
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Apply the Multiplicative Property

Consider the composite product of three matrices: $B^{-1}$, $A^T$, and $B$.
Applying the multiplicative property of determinants:
$$
\det\left(B^{-1} A^T B\right) = \det\left(B^{-1}\right) \cdot \det\left(A^T\right) \cdot \det(B)
$$
*(Property 1: The determinant of a product is the product of the determinants)*.

---

### Step 2: Apply the Inverse Property to $B^{-1}$

Since $B$ is invertible and $\det B = 3 \ne 0$:
$$
\det\left(B^{-1}\right) = \frac{1}{\det B}
$$
*(Property 2: The determinant of an inverse matrix is the reciprocal of the determinant)*.

Substituting this into the expression:
$$
\det\left(B^{-1} A^T B\right) = \frac{1}{\det B} \cdot \det\left(A^T\right) \cdot \det(B)
$$

---

### Step 3: Apply the Transpose Property to $A^T$

Transposition preserves the determinant:
$$
\det\left(A^T\right) = \det A
$$
*(Property 3: The determinant of the transpose equals the determinant of the original matrix)*.

Substituting this into the expression:
$$
\det\left(B^{-1} A^T B\right) = \frac{1}{\det B} \cdot \det A \cdot \det B
$$

---

### Step 4: Simplify Using Commutativity of Real Numbers

Because $\det A$ and $\det B$ are real numbers, multiplication in $\mathbb{R}$ is commutative and associative. We group the factors involving $B$:
$$
\det\left(B^{-1} A^T B\right) = \left( \frac{1}{\det B} \cdot \det B \right) \cdot \det A = 1 \cdot \det A = \det A
$$

Now substitute the given value $\det A = -2$:
$$
\det\left(B^{-1} A^T B\right) = -2
$$

---

### Step 5: Summary of Properties Used (In Order)

1. **Product Property:** $\det(XYZ) = \det(X) \det(Y) \det(Z)$.
2. **Inverse Property:** $\det(B^{-1}) = \frac{1}{\det B}$.
3. **Transpose Property:** $\det(A^T) = \det A$.
4. **Scalar Field Commutativity:** $\frac{1}{\det B} \cdot \det B = 1$.

---

### Step 6: Explanation of Why Matrix $B$ Cancels Out

- The expression $B^{-1} (A^T) B$ represents a **similarity transformation** (conjugation) of the matrix $A^T$ by the invertible matrix $B$.
- Geometrically, matrix $B$ acts as a change-of-basis matrix. The matrix $B^{-1} A^T B$ describes the exact same geometric transformation as $A^T$, merely observed in the new coordinate frame defined by the columns of $B$.
- Since the determinant measures the intrinsic volume scaling factor of a linear operator, its value is an invariant geometric property of the operator itself, completely independent of the coordinate system chosen to write its matrix.
- Algebraically, changing basis scales the coordinate volume by $\det B$, and changing back scales it by $\frac{1}{\det B}$, which cancel each other out identically:
  $$
  \det(B^{-1})\det(B) = \det(B^{-1}B) = \det(I) = 1
  $$

---

## 4. Verification and Consistency Checks

1. **Concrete Matrix Example:**
   Construct simple matrices satisfying the given determinants:
   - Let $A = \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix} \implies \det A = (-2)(1) - 0 = -2$.
   - Let $B = \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} \implies \det B = (3)(1) - 0 = 3$.
   Then:
   - $A^T = \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix}$.
   - $B^{-1} = \begin{pmatrix} 1/3 & 0 \\ 0 & 1 \end{pmatrix}$.
   Compute the product directly:
   $$
   B^{-1} A^T B = \begin{pmatrix} 1/3 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} -2/3 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix}
   $$
   Computing the determinant of this explicit matrix:
   $$
   \det\begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix} = (-2)(1) - 0 = -2 \quad \checkmark
   $$

2. **Non-Diagonal Test Case:**
   Let $B = \begin{pmatrix} 1 & 1 \\ 0 & 3 \end{pmatrix} \implies \det B = 3$.
   $B^{-1} = \frac{1}{3} \begin{pmatrix} 3 & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & -1/3 \\ 0 & 1/3 \end{pmatrix}$.
   Then:
   $$
   \det(B^{-1} A^T B) = \det(B^{-1})\det(A^T)\det(B) = \left(\frac{1}{3}\right)(-2)(3) = -2 \quad \checkmark
   $$
   The result is universally $-2$.

