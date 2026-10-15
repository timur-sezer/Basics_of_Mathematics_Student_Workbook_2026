# Solution to Exercise 10: Columns of a Matrix Product

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 2 \\ -1 & 0 \\ 3 & 1 \end{pmatrix}
$$
Denote the columns of $B$ by $b_1$ and $b_2$:
$$
b_1 = \begin{pmatrix} 1 \\ -1 \\ 3 \end{pmatrix}, \qquad b_2 = \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix}
$$

1. Compute $Ab_1$ and $Ab_2$.
2. Compute the full matrix product $AB$.
3. Compare the results and explain why the columns of $AB$ are precisely the vectors $Ab_1$ and $Ab_2$.

---

## 2. Theoretical Background and Concepts

1. **Column Partitioning of a Matrix Product:**
   Let $A$ be an $m \times k$ matrix and let $B$ be a $k \times p$ matrix whose columns are denoted by $b_1, b_2, \dots, b_p \in \mathbb{R}^k$:
   $$
   B = \begin{pmatrix} b_1 & b_2 & \cdots & b_p \end{pmatrix}
   $$
   Then the product matrix $AB$ can be partitioned directly column-by-column:
   $$
   AB = A \begin{pmatrix} b_1 & b_2 & \cdots & b_p \end{pmatrix} = \begin{pmatrix} Ab_1 & Ab_2 & \cdots & Ab_p \end{pmatrix}
   $$

2. **Index-Level Justification:**
   The entry in row $i$ and column $j$ of the matrix product $AB$ is given by:
   $$
   (AB)_{ij} = \sum_{r=1}^k a_{ir} B_{rj}
   $$
   Notice that the scalars $B_{rj}$ ($r = 1, \dots, k$) are precisely the components of the column vector $b_j$.
   Therefore, the $i$-th entry of the $j$-th column of $AB$ is:
   $$
   (AB)_{ij} = \mathbf{r}_i(A) \cdot b_j = (Ab_j)_i
   $$
   Since this holds for every row index $i$, the entire $j$-th column of $AB$ is identically the vector $Ab_j$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $Ab_1$ and $Ab_2$

1. **Compute $Ab_1$:**
   $$
   Ab_1 = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 \\ -1 \\ 3 \end{pmatrix}
   $$
   - Component 1: $(1)(1) + (2)(-1) + (0)(3) = 1 - 2 + 0 = -1$
   - Component 2: $(0)(1) + (1)(-1) + (1)(3) = 0 - 1 + 3 = 2$
   $$
   Ab_1 = \begin{pmatrix} -1 \\ 2 \end{pmatrix}
   $$

2. **Compute $Ab_2$:**
   $$
   Ab_2 = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix}
   $$
   - Component 1: $(1)(2) + (2)(0) + (0)(1) = 2 + 0 + 0 = 2$
   - Component 2: $(0)(2) + (1)(0) + (1)(1) = 0 + 0 + 1 = 1$
   $$
   Ab_2 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}
   $$

---

### Step 2: Compute the Matrix Product $AB$

Matrix $A$ has size $2 \times 3$ and matrix $B$ has size $3 \times 2$. The product $AB$ has size $2 \times 2$:
$$
AB = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 2 \\ -1 & 0 \\ 3 & 1 \end{pmatrix}
$$

Computing each entry using the standard row-by-column method:
- **Entry $(1, 1)$:**
  $$
  (1)(1) + (2)(-1) + (0)(3) = 1 - 2 + 0 = -1
  $$
- **Entry $(1, 2)$:**
  $$
  (1)(2) + (2)(0) + (0)(1) = 2 + 0 + 0 = 2
  $$
- **Entry $(2, 1)$:**
  $$
  (0)(1) + (1)(-1) + (1)(3) = 0 - 1 + 3 = 2
  $$
- **Entry $(2, 2)$:**
  $$
  (0)(2) + (1)(0) + (1)(1) = 0 + 0 + 1 = 1
  $$

Thus:
$$
AB = \begin{pmatrix} -1 & 2 \\ 2 & 1 \end{pmatrix}
$$

---

### Step 3: Comparison and Explanation

Comparing the columns of $AB$ with the vectors $Ab_1$ and $Ab_2$:
- Column 1 of $AB$ is $\begin{pmatrix} -1 \\ 2 \end{pmatrix}$, which matches $Ab_1$ exactly.
- Column 2 of $AB$ is $\begin{pmatrix} 2 \\ 1 \end{pmatrix}$, which matches $Ab_2$ exactly.

Therefore:
$$
AB = \begin{pmatrix} Ab_1 & Ab_2 \end{pmatrix} = \begin{pmatrix} -1 & 2 \\ 2 & 1 \end{pmatrix}
$$

**Why this holds:**
When multiplying matrix $A$ by matrix $B$, each column $j$ of the result is produced independently by multiplying all rows of $A$ by the $j$-th column of $B$. That operation is, by definition, the matrix-vector multiplication $A b_j$. Hence, computing a matrix product $AB$ is equivalent to applying the transformation $A$ simultaneously to each column vector of $B$.

---

## 4. Verification and Consistency Checks

1. **Linear Combination Form for Each Column:**
   - For $Ab_1$:
     $$
     1 \begin{pmatrix} 1 \\ 0 \end{pmatrix} + (-1) \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 3 \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 1 - 2 + 0 \\ 0 - 1 + 3 \end{pmatrix} = \begin{pmatrix} -1 \\ 2 \end{pmatrix} \quad \checkmark
     $$
   - For $Ab_2$:
     $$
     2 \begin{pmatrix} 1 \\ 0 \end{pmatrix} + 0 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 1 \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 2 + 0 + 0 \\ 0 + 0 + 1 \end{pmatrix} = \begin{pmatrix} 2 \\ 1 \end{pmatrix} \quad \checkmark
     $$
   This reinforces that column operations and matrix multiplication produce identical outputs.

2. **Trace and Determinant Check of $AB$:**
   - $\operatorname{tr}(AB) = -1 + 1 = 0$.
   - $\det(AB) = (-1)(1) - (2)(2) = -1 - 4 = -5$.
   Both values are consistent with the calculated entries.
