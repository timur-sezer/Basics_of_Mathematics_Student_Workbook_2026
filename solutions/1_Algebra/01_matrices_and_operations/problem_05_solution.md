# Solution to Exercise 5: Matrix Times Vector

## 1. Problem Statement

Given the matrix $A$ and the vector $x$:
$$
A = \begin{pmatrix} 2 & -1 \\ 1 & 3 \end{pmatrix}, \qquad x = \begin{pmatrix} 4 \\ 2 \end{pmatrix}
$$

1. Compute the matrix-vector product $Ax$.
2. Express $Ax$ as a linear combination of the columns of $A$, with coefficients coming from the vector $x$.

---

## 2. Theoretical Background and Concepts

1. **Row View of Matrix-Vector Multiplication:**
   In the standard row view, the $i$-th entry of $Ax$ is the dot product of the $i$-th row of $A$ with the vector $x$:
   $$
   (Ax)_i = \mathbf{r}_i(A) \cdot x = \sum_{j=1}^n a_{ij} x_j
   $$

2. **Column View (Linear Combination View):**
   A fundamental perspective in linear algebra is that multiplying a matrix $A = \begin{pmatrix} \mathbf{a}_1 & \mathbf{a}_2 & \cdots & \mathbf{a}_n \end{pmatrix}$ by a vector $x = \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{pmatrix}$ computes a **linear combination of the column vectors of $A$**, weighted by the components of $x$:
   $$
   Ax = x_1 \mathbf{a}_1 + x_2 \mathbf{a}_2 + \cdots + x_n \mathbf{a}_n
   $$
   This bridges matrix algebra with vector spaces and spans: the set of all possible outputs $Ax$ is the column space $\operatorname{Col}(A)$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $Ax$ Using the Standard Row-by-Column Rule

Matrix $A$ has size $2 \times 2$ and vector $x$ has size $2 \times 1$. The inner dimensions match ($2 = 2$), resulting in a $2 \times 1$ column vector:
$$
Ax = \begin{pmatrix} 2 & -1 \\ 1 & 3 \end{pmatrix} \begin{pmatrix} 4 \\ 2 \end{pmatrix}
$$

Computing each component:
- **First component (Row 1):**
  $$
  (2)(4) + (-1)(2) = 8 - 2 = 6
  $$
- **Second component (Row 2):**
  $$
  (1)(4) + (3)(2) = 4 + 6 = 10
  $$

Thus:
$$
Ax = \begin{pmatrix} 6 \\ 10 \end{pmatrix}
$$

### Step 2: Express $Ax$ as a Linear Combination of the Columns of $A$

Identify the columns of matrix $A$:
$$
\mathbf{a}_1 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}, \qquad \mathbf{a}_2 = \begin{pmatrix} -1 \\ 3 \end{pmatrix}
$$

The scalar coefficients from the vector $x = \begin{pmatrix} 4 \\ 2 \end{pmatrix}$ are:
$$
x_1 = 4, \qquad x_2 = 2
$$

Forming the linear combination:
$$
Ax = 4 \mathbf{a}_1 + 2 \mathbf{a}_2 = 4 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 2 \begin{pmatrix} -1 \\ 3 \end{pmatrix}
$$

Evaluating this linear combination explicitly:
$$
4 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 2 \begin{pmatrix} -1 \\ 3 \end{pmatrix} = \begin{pmatrix} 4 \cdot 2 \\ 4 \cdot 1 \end{pmatrix} + \begin{pmatrix} 2 \cdot (-1) \\ 2 \cdot 3 \end{pmatrix} = \begin{pmatrix} 8 \\ 4 \end{pmatrix} + \begin{pmatrix} -2 \\ 6 \end{pmatrix} = \begin{pmatrix} 8 - 2 \\ 4 + 6 \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}
$$

Both methods yield the exact same vector.

---

## 4. Verification and Consistency Checks

1. **Equivalence of the Two Perspectives:**
   - Row-dot-product perspective:
     $$
     Ax = \begin{pmatrix} 2(4) - 1(2) \\ 1(4) + 3(2) \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}
     $$
   - Column-linear-combination perspective:
     $$
     Ax = \begin{pmatrix} 4(2) + 2(-1) \\ 4(1) + 2(3) \end{pmatrix} = \begin{pmatrix} 8 - 2 \\ 4 + 6 \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}
     $$
   Because addition in $\mathbb{R}$ is commutative ($2(4) + (-1)(2) = 4(2) + 2(-1)$), the row and column views are algebraically identical.

2. **Linear System Consistency Check:**
   Solving $A \begin{pmatrix} u \\ v \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}$ via Cramer's Rule or Gaussian elimination:
   - $\det(A) = 2(3) - (-1)(1) = 6 + 1 = 7 \ne 0$.
   - $u = \frac{\det\begin{pmatrix}6 & -1 \\ 10 & 3\end{pmatrix}}{7} = \frac{18 - (-10)}{7} = \frac{28}{7} = 4$.
   - $v = \frac{\det\begin{pmatrix}2 & 6 \\ 1 & 10\end{pmatrix}}{7} = \frac{20 - 6}{7} = \frac{14}{7} = 2$.
   This precisely recovers vector $x = \begin{pmatrix} 4 \\ 2 \end{pmatrix}$, confirming the calculation.

