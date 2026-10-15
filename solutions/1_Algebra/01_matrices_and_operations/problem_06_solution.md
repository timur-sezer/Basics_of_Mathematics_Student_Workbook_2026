# Solution to Exercise 6: Transpose

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}
$$

1. Compute the transpose $A^T$.
2. Compute the transpose $B^T$.
3. Compute the product $AB$.
4. Verify in this example the identity:
   $$
   (AB)^T = B^T A^T
   $$

---

## 2. Theoretical Background and Concepts

1. **Definition of Matrix Transposition:**
   The transpose of an $m \times n$ matrix $M = (m_{ij})$ is the $n \times m$ matrix $M^T = (m_{ji}^T)$ obtained by reflecting the matrix along its main diagonal. Equivalently, the rows of $M$ become the columns of $M^T$, and the columns of $M$ become the rows of $M^T$:
   $$
   (M^T)_{ij} = M_{ji}
   $$

2. **Transpose of a Matrix Product:**
   For any two matrices $A$ and $B$ whose product $AB$ is defined, the transpose of the product satisfies the **reversal property**:
   $$
   (AB)^T = B^T A^T
   $$
   *Reason for the reversal:* If $A$ is $m \times k$ and $B$ is $k \times p$, then $AB$ is $m \times p$, and its transpose $(AB)^T$ is $p \times m$.
   Looking at the transposes of the individual factors: $B^T$ is $p \times k$ and $A^T$ is $k \times m$. The product $B^T A^T$ has inner dimension $k$ and resulting size $p \times m$. (In contrast, $A^T B^T$ would attempt to multiply $(k \times m)(p \times k)$, which in general is not even defined unless $m = p$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $A^T$

Matrix $A$ has size $2 \times 3$:
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix}
$$
Swapping rows into columns, $A^T$ has size $3 \times 2$:
- Column 1 of $A^T$ is Row 1 of $A$: $\begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}$.
- Column 2 of $A^T$ is Row 2 of $A$: $\begin{pmatrix} 4 \\ 5 \\ 6 \end{pmatrix}$.

$$
A^T = \begin{pmatrix} 1 & 4 \\ 2 & 5 \\ 3 & 6 \end{pmatrix}
$$

### Step 2: Compute $B^T$

Matrix $B$ has size $3 \times 2$:
$$
B = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}
$$
Swapping rows into columns, $B^T$ has size $2 \times 3$:
- Row 1 of $B^T$ is Column 1 of $B$: $\begin{pmatrix} 1 & 2 & -1 \end{pmatrix}$.
- Row 2 of $B^T$ is Column 2 of $B$: $\begin{pmatrix} 0 & 1 & 3 \end{pmatrix}$.

$$
B^T = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & 3 \end{pmatrix}
$$

### Step 3: Compute the Product $AB$

Matrix $A$ ($2 \times 3$) and matrix $B$ ($3 \times 2$) produce a $2 \times 2$ matrix $AB$:
$$
AB = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}
$$

Calculating each entry:
- **Entry $(1, 1)$:**
  $$
  (1)(1) + (2)(2) + (3)(-1) = 1 + 4 - 3 = 2
  $$
- **Entry $(1, 2)$:**
  $$
  (1)(0) + (2)(1) + (3)(3) = 0 + 2 + 9 = 11
  $$
- **Entry $(2, 1)$:**
  $$
  (4)(1) + (5)(2) + (6)(-1) = 4 + 10 - 6 = 8
  $$
- **Entry $(2, 2)$:**
  $$
  (4)(0) + (5)(1) + (6)(3) = 0 + 5 + 18 = 23
  $$

Thus:
$$
AB = \begin{pmatrix} 2 & 11 \\ 8 & 23 \end{pmatrix}
$$

### Step 4: Verify $(AB)^T = B^T A^T$

1. **Left-hand side: $(AB)^T$**
   Transposing the $2 \times 2$ matrix $AB$:
   $$
   (AB)^T = \begin{pmatrix} 2 & 11 \\ 8 & 23 \end{pmatrix}^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}
   $$

2. **Right-hand side: $B^T A^T$**
   Multiply $B^T$ ($2 \times 3$) by $A^T$ ($3 \times 2$):
   $$
   B^T A^T = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & 3 \end{pmatrix} \begin{pmatrix} 1 & 4 \\ 2 & 5 \\ 3 & 6 \end{pmatrix}
   $$

   Calculating each entry:
   - **Entry $(1, 1)$:**
     $$
     (1)(1) + (2)(2) + (-1)(3) = 1 + 4 - 3 = 2
     $$
   - **Entry $(1, 2)$:**
     $$
     (1)(4) + (2)(5) + (-1)(6) = 4 + 10 - 6 = 8
     $$
   - **Entry $(2, 1)$:**
     $$
     (0)(1) + (1)(2) + (3)(3) = 0 + 2 + 9 = 11
     $$
   - **Entry $(2, 2)$:**
     $$
     (0)(4) + (1)(5) + (3)(6) = 0 + 5 + 18 = 23
     $$

   Thus:
   $$
   B^T A^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}
   $$

3. **Comparison:**
   $$
   (AB)^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix} = B^T A^T
   $$
   The equality is verified completely.

---

## 4. Verification and Consistency Checks

1. **Dimension Match:**
   - $\text{size}(A) = 2 \times 3 \implies \text{size}(A^T) = 3 \times 2$.
   - $\text{size}(B) = 3 \times 2 \implies \text{size}(B^T) = 2 \times 3$.
   - $\text{size}(AB) = 2 \times 2 \implies \text{size}((AB)^T) = 2 \times 2$.
   - $\text{size}(B^T A^T) = (2 \times 3) \times (3 \times 2) = 2 \times 2$.
   Both sides have identical dimensions $2 \times 2$.

2. **Component-wise Identity Check:**
   By definition of matrix multiplication:
   $$
   ((AB)^T)_{ij} = (AB)_{ji} = \sum_{r=1}^3 a_{jr} b_{ri} = \sum_{r=1}^3 b_{ri} a_{jr} = \sum_{r=1}^3 (B^T)_{ir} (A^T)_{rj} = (B^T A^T)_{ij}
   $$
   This proves the theoretical identity for every single entry, matching our numerical computation perfectly.

