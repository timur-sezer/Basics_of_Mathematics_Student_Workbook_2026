# Solution to Exercise 2: Addition and Scalar Multiplication

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix}, \qquad B = \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix}
$$

1. Compute $A + B$.
2. Compute $A - B$.
3. Compute $3A - 2B$.
4. Explain why matrix addition is possible only for matrices of the same size.

---

## 2. Theoretical Background and Concepts

1. **Matrix Addition and Subtraction:**
   Matrix addition (and subtraction) is defined entry-by-entry. If $A = (a_{ij})$ and $B = (b_{ij})$ are two matrices of the same size $m \times n$, their sum $A + B$ and difference $A - B$ are matrices of size $m \times n$ whose entries are given by:
   $$
   (A + B)_{ij} = a_{ij} + b_{ij}, \qquad (A - B)_{ij} = a_{ij} - b_{ij}
   $$
   for all $1 \le i \le m$ and $1 \le j \le n$.

2. **Scalar Multiplication:**
   Multiplying a matrix $A$ by a scalar $c \in \mathbb{R}$ means multiplying every entry of $A$ by $c$:
   $$
   (cA)_{ij} = c \cdot a_{ij}
   $$

3. **Linear Combinations of Matrices:**
   For scalars $\alpha, \beta$ and matrices $A, B$ of identical dimensions:
   $$
   (\alpha A + \beta B)_{ij} = \alpha a_{ij} + \beta b_{ij}
   $$

4. **Dimension Compatibility Condition:**
   Because addition is defined by pairing the entry in position $(i, j)$ of the first matrix with the entry in position $(i, j)$ of the second matrix, every position in the first matrix must have an exact counterpart in the second. If the matrices have differing numbers of rows or columns, some entries would have no corresponding entry to pair with, rendering the operation undefined.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $A + B$

Add corresponding entries of $A$ and $B$:
$$
A + B = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} + \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} 1 + 4 & 2 + (-2) \\ -1 + 0 & 3 + 5 \end{pmatrix}
$$

Evaluating each entry:
- Row 1, Column 1: $1 + 4 = 5$
- Row 1, Column 2: $2 + (-2) = 0$
- Row 2, Column 1: $-1 + 0 = -1$
- Row 2, Column 2: $3 + 5 = 8$

$$
A + B = \begin{pmatrix} 5 & 0 \\ -1 & 8 \end{pmatrix}
$$

### Step 2: Compute $A - B$

Subtract corresponding entries of $B$ from $A$:
$$
A - B = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} - \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} 1 - 4 & 2 - (-2) \\ -1 - 0 & 3 - 5 \end{pmatrix}
$$

Evaluating each entry:
- Row 1, Column 1: $1 - 4 = -3$
- Row 1, Column 2: $2 - (-2) = 2 + 2 = 4$
- Row 2, Column 1: $-1 - 0 = -1$
- Row 2, Column 2: $3 - 5 = -2$

$$
A - B = \begin{pmatrix} -3 & 4 \\ -1 & -2 \end{pmatrix}
$$

### Step 3: Compute $3A - 2B$

First, compute the scalar multiples $3A$ and $2B$:
$$
3A = 3 \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} = \begin{pmatrix} 3(1) & 3(2) \\ 3(-1) & 3(3) \end{pmatrix} = \begin{pmatrix} 3 & 6 \\ -3 & 9 \end{pmatrix}
$$
$$
2B = 2 \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} 2(4) & 2(-2) \\ 2(0) & 2(5) \end{pmatrix} = \begin{pmatrix} 8 & -4 \\ 0 & 10 \end{pmatrix}
$$

Now subtract $2B$ from $3A$:
$$
3A - 2B = \begin{pmatrix} 3 & 6 \\ -3 & 9 \end{pmatrix} - \begin{pmatrix} 8 & -4 \\ 0 & 10 \end{pmatrix} = \begin{pmatrix} 3 - 8 & 6 - (-4) \\ -3 - 0 & 9 - 10 \end{pmatrix}
$$

Evaluating each entry:
- Row 1, Column 1: $3 - 8 = -5$
- Row 1, Column 2: $6 - (-4) = 6 + 4 = 10$
- Row 2, Column 1: $-3 - 0 = -3$
- Row 2, Column 2: $9 - 10 = -1$

$$
3A - 2B = \begin{pmatrix} -5 & 10 \\ -3 & -1 \end{pmatrix}
$$

### Step 4: Explanation of Size Requirement

Matrix addition is defined as an entry-wise operation: the $(i, j)$-th entry of the sum $(A + B)_{ij}$ is computed directly by adding the scalar $a_{ij}$ to the scalar $b_{ij}$. 

For this binary operation to be well-defined:
1. Every entry in $A$ must correspond to a uniquely defined entry in $B$ occupying the exact same position (same row index $i$ and column index $j$).
2. If matrix $A$ has size $m_1 \times n_1$ and matrix $B$ has size $m_2 \times n_2$ with $m_1 \ne m_2$ or $n_1 \ne n_2$, there exist positions in one matrix that have no corresponding counterpart in the other. In that case, the sum cannot be formed component-wise.
3. Therefore, matrix addition $A + B$ is strictly defined if and only if both matrices have identical dimensions ($m \times n$).

---

## 4. Verification and Consistency Checks

1. **Relation Between Sum and Difference:**
   $$
   (A + B) + (A - B) = 2A
   $$
   Substituting our results:
   $$
   \begin{pmatrix} 5 & 0 \\ -1 & 8 \end{pmatrix} + \begin{pmatrix} -3 & 4 \\ -1 & -2 \end{pmatrix} = \begin{pmatrix} 5 - 3 & 0 + 4 \\ -1 - 1 & 8 - 2 \end{pmatrix} = \begin{pmatrix} 2 & 4 \\ -2 & 6 \end{pmatrix}
   $$
   Comparing with $2A$:
   $$
   2A = 2 \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} = \begin{pmatrix} 2 & 4 \\ -2 & 6 \end{pmatrix}
   $$
   The identity holds, confirming that both $A + B$ and $A - B$ are correct.

2. **Alternative Linear Combination Check:**
   Notice that $3A - 2B = (A - B) + 2(A - B)$ is not general, but we can verify:
   $$
   (3A - 2B) + 2(A + B) = 5A
   $$
   $$
   \begin{pmatrix} -5 & 10 \\ -3 & -1 \end{pmatrix} + 2\begin{pmatrix} 5 & 0 \\ -1 & 8 \end{pmatrix} = \begin{pmatrix} -5 + 10 & 10 + 0 \\ -3 - 2 & -1 + 16 \end{pmatrix} = \begin{pmatrix} 5 & 10 \\ -5 & 15 \end{pmatrix} = 5A
   $$
   Matches $5A = \begin{pmatrix} 5 & 10 \\ -5 & 15 \end{pmatrix}$ exactly.
