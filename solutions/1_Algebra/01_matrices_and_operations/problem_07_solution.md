# Solution to Exercise 7: Identity Matrix, Zero Matrix, and Powers

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}
$$

1. Compute the products and sums:
   $$
   AI, \qquad IA, \qquad A + 0, \qquad A^2, \qquad A^3
   $$
   where $I$ is the $2 \times 2$ identity matrix and $0$ is the $2 \times 2$ zero matrix.
2. Explain the roles of the matrices $I$ and $0$ in matrix algebra.
3. Describe the pattern observed in successive powers of $A$.

---

## 2. Theoretical Background and Concepts

1. **Identity Matrix ($I$):**
   The identity matrix of size $n \times n$ has ones on the main diagonal and zeros elsewhere:
   $$
   I_2 = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}
   $$
   It acts as the **multiplicative identity**: for any square matrix $M$, $MI = IM = M$.

2. **Zero Matrix ($0$):**
   The zero matrix of size $m \times n$ consists entirely of zero entries:
   $$
   0_2 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}
   $$
   It acts as the **additive identity**: for any matrix $M$ of matching size, $M + 0 = 0 + M = M$.

3. **Matrix Powers:**
   For a square matrix $A$, positive integer powers are defined inductively by $A^1 = A$ and $A^{k+1} = A^k A$.

4. **Binomial Decomposition of Jordan Blocks:**
   The matrix $A$ can be decomposed as $A = 2I + N$, where $N = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$.
   Because the scalar matrix $2I$ commutes with any matrix, the binomial theorem applies:
   $$
   A^n = (2I + N)^n = \sum_{k=0}^n \binom{n}{k} (2I)^{n-k} N^k
   $$
   Since $N^2 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}$, all terms with $k \ge 2$ vanish, leaving:
   $$
   A^n = 2^n I + n 2^{n-1} N = \begin{pmatrix} 2^n & n 2^{n-1} \\ 0 & 2^n \end{pmatrix}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $AI$, $IA$, and $A + 0$

Let $I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$ and $0 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}$.

- **Product $AI$:**
  $$
  AI = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 2(1) + 1(0) & 2(0) + 1(1) \\ 0(1) + 2(0) & 0(0) + 2(1) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A
  $$

- **Product $IA$:**
  $$
  IA = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 1(2) + 0(0) & 1(1) + 0(2) \\ 0(2) + 1(0) & 0(1) + 1(2) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A
  $$

- **Sum $A + 0$:**
  $$
  A + 0 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} + \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 2 + 0 & 1 + 0 \\ 0 + 0 & 2 + 0 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A
  $$

### Step 2: Compute $A^2$

Multiply $A$ by $A$:
$$
A^2 = A \cdot A = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}
$$

Computing each entry:
- Entry $(1, 1)$: $2(2) + 1(0) = 4 + 0 = 4$
- Entry $(1, 2)$: $2(1) + 1(2) = 2 + 2 = 4$
- Entry $(2, 1)$: $0(2) + 2(0) = 0 + 0 = 0$
- Entry $(2, 2)$: $0(1) + 2(2) = 0 + 4 = 4$

$$
A^2 = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix}
$$

### Step 3: Compute $A^3$

Multiply $A^2$ by $A$:
$$
A^3 = A^2 \cdot A = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}
$$

Computing each entry:
- Entry $(1, 1)$: $4(2) + 4(0) = 8 + 0 = 8$
- Entry $(1, 2)$: $4(1) + 4(2) = 4 + 8 = 12$
- Entry $(2, 1)$: $0(2) + 4(0) = 0 + 0 = 0$
- Entry $(2, 2)$: $0(1) + 4(2) = 0 + 8 = 8$

$$
A^3 = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix}
$$

### Step 4: Roles of $I$ and $0$

1. **Role of $I$ (Multiplicative Identity):**
   The identity matrix $I$ behaves analogously to the number $1$ in real numbers. It leaves every vector unchanged under linear transformation ($Ix = x$) and leaves every matrix unchanged under multiplication ($AI = IA = A$).
2. **Role of $0$ (Additive Identity):**
   The zero matrix $0$ behaves analogously to the number $0$ in real numbers. Adding $0$ to any matrix does not change it ($A + 0 = A$). Under multiplication, it annihilates any matrix: $A \cdot 0 = 0 \cdot A = 0$.

### Step 5: Description of the Pattern in Successive Powers of $A$

Examining $A^1$, $A^2$, $A^3$:
- $A^1 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 2^1 & 1 \cdot 2^0 \\ 0 & 2^1 \end{pmatrix}$
- $A^2 = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} = \begin{pmatrix} 2^2 & 2 \cdot 2^1 \\ 0 & 2^2 \end{pmatrix}$
- $A^3 = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix} = \begin{pmatrix} 2^3 & 3 \cdot 2^2 \\ 0 & 2^3 \end{pmatrix}$

**Observed Pattern:**
For any positive integer $n \ge 1$:
1. The diagonal entries are always powers of $2$: $a_{11}^{(n)} = a_{22}^{(n)} = 2^n$.
2. The bottom-left entry remains zero: $a_{21}^{(n)} = 0$ (preserving upper-triangular structure).
3. The top-right entry grows as $a_{12}^{(n)} = n \cdot 2^{n-1}$.

Therefore, the general formula for the $n$-th power is:
$$
A^n = \begin{pmatrix} 2^n & n 2^{n-1} \\ 0 & 2^n \end{pmatrix}
$$

---

## 4. Verification and Consistency Checks

1. **Check for $A^4$ via General Formula vs. Direct Multiplication:**
   - From formula:
     $$
     A^4 = \begin{pmatrix} 2^4 & 4 \cdot 2^3 \\ 0 & 2^4 \end{pmatrix} = \begin{pmatrix} 16 & 32 \\ 0 & 16 \end{pmatrix}
     $$
   - From direct multiplication $A^3 \cdot A$:
     $$
     \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 16 + 0 & 8 + 24 \\ 0 + 0 & 0 + 16 \end{pmatrix} = \begin{pmatrix} 16 & 32 \\ 0 & 16 \end{pmatrix}
     $$
   Both match identically.

2. **Determinant Power Property:**
   - $\det(A) = 2 \cdot 2 - 1 \cdot 0 = 4$.
   - $\det(A^2) = 4 \cdot 4 - 4 \cdot 0 = 16 = (\det A)^2 = 4^2$.
   - $\det(A^3) = 8 \cdot 8 - 12 \cdot 0 = 64 = (\det A)^3 = 4^3$.
   This confirms numerical correctness.
