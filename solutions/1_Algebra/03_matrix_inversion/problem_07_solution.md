# Solution to Exercise 7: Inverse of a Product

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix}
$$

1. Compute the product $AB$, and then find its inverse $(AB)^{-1}$.
2. Compute the individual inverses $A^{-1}$ and $B^{-1}$, and find the product $B^{-1} A^{-1}$.
3. Confirm that $(AB)^{-1} = B^{-1} A^{-1}$.
4. Explain the meaning of the reversed order of factors in the inverse of a product.

---

## 2. Theoretical Background and Concepts

1. **The Reversal Rule for Inverses:**
   For any two invertible matrices $A$ and $B$ of the same size, their product $AB$ is invertible, and its inverse is given by the **reversal rule**:
   $$
   (AB)^{-1} = B^{-1} A^{-1}
   $$

2. **Algebraic Derivation:**
   To verify that a matrix $X$ is the inverse of $AB$, we test the identity $(AB)X = I$:
   $$
   (AB)(B^{-1} A^{-1}) = A (B B^{-1}) A^{-1} = A (I) A^{-1} = A A^{-1} = I
   $$
   Similarly, on the left:
   $$
   (B^{-1} A^{-1})(AB) = B^{-1} (A^{-1} A) B = B^{-1} (I) B = B^{-1} B = I
   $$
   Because matrix multiplication is generally noncommutative ($BA \ne AB$), attempting the unreversed order $A^{-1} B^{-1}$ fails to cancel:
   $$
   (AB)(A^{-1} B^{-1}) = A (B A^{-1}) B^{-1} \ne I
   $$

3. **The "Socks and Shoes" Principle:**
   If you put on your socks (operation $A$) and then put on your shoes (operation $B$), to return your feet to their original state you must first take off your shoes ($B^{-1}$) and only then take off your socks ($A^{-1}$). The last operation applied must be the first operation undone.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $AB$ and $(AB)^{-1}$

1. **Compute $AB$:**
   $$
   AB = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix} = \begin{pmatrix} 1(2) + 1(0) & 1(0) + 1(3) \\ 0(2) + 1(0) & 0(0) + 1(3) \end{pmatrix} = \begin{pmatrix} 2 & 3 \\ 0 & 3 \end{pmatrix}
   $$

2. **Compute $(AB)^{-1}$:**
   - Determinant: $\det(AB) = (2)(3) - (3)(0) = 6$.
   - Inversion formula:
     $$
     (AB)^{-1} = \frac{1}{6} \begin{pmatrix} 3 & -3 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} \frac{3}{6} & -\frac{3}{6} \\ 0 & \frac{2}{6} \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3} \end{pmatrix}
     $$

---

### Step 2: Compute $A^{-1}$, $B^{-1}$, and $B^{-1} A^{-1}$

1. **Compute $A^{-1}$:**
   - For $A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$, $\det A = 1(1) - 0 = 1$.
   $$
   A^{-1} = \frac{1}{1} \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix}
   $$

2. **Compute $B^{-1}$:**
   - For diagonal matrix $B = \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix}$, inverting diagonal entries gives:
   $$
   B^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & \frac{1}{3} \end{pmatrix}
   $$

3. **Compute $B^{-1} A^{-1}$:**
   $$
   B^{-1} A^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & \frac{1}{3} \end{pmatrix} \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} \frac{1}{2}(1) + 0(0) & \frac{1}{2}(-1) + 0(1) \\ 0(1) + \frac{1}{3}(0) & 0(-1) + \frac{1}{3}(1) \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3} \end{pmatrix}
   $$

---

### Step 3: Comparison and Explanation of the Reversed Order

1. **Comparison:**
   $$
   (AB)^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3} \end{pmatrix} = B^{-1} A^{-1}
   $$
   Both expressions produce identical matrices.

2. **Explanation of the Reversed Order:**
   - When the composite operation $AB$ acts on a vector $x$, matrix $B$ acts first, followed by matrix $A$: $(AB)x = A(Bx)$.
   - To reverse this process, we must first peel off the outer transformation $A$ by applying $A^{-1}$, yielding $A^{-1}(A(Bx)) = Bx$.
   - Only then can we peel off the inner transformation $B$ by applying $B^{-1}$, arriving back at $B^{-1}(Bx) = x$.
   - Consequently, the composition that undoes $AB$ is $B^{-1} \circ A^{-1}$. Reversing the order of factors is necessary because matrix multiplication is noncommutative.

---

## 4. Verification and Consistency Checks

1. **Multiplication Check of the Unreversed Product ($A^{-1} B^{-1}$):**
   Compute the unreversed order:
   $$
   A^{-1} B^{-1} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & \frac{1}{3} \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{3} \\ 0 & \frac{1}{3} \end{pmatrix}
   $$
   Notice:
   $$
   A^{-1} B^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{3} \\ 0 & \frac{1}{3} \end{pmatrix} \ne \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3} \end{pmatrix} = (AB)^{-1}
   $$
   This proves that the unreversed order $A^{-1} B^{-1}$ is genuinely different and incorrect.

2. **Identity Verification:**
   $$
   (AB)(B^{-1} A^{-1}) = \begin{pmatrix} 2 & 3 \\ 0 & 3 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3} \end{pmatrix} = \begin{pmatrix} 2(1/2) + 3(0) & 2(-1/2) + 3(1/3) \\ 0(1/2) + 3(0) & 0(-1/2) + 3(1/3) \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I \quad \checkmark
   $$
