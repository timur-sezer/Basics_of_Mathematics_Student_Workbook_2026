# Solution to Exercise 11: Shortening the Calculation with Row Operations

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 1 & 3 & 4 \\ 1 & 4 & 6 \end{pmatrix}
$$

1. Compute $\det A$ by first applying elementary row operations to introduce as many zeros as possible.
2. Explicitly state which row operations leave the determinant unchanged.

---

## 2. Theoretical Background and Concepts

1. **Determinant-Preserving Operations (Type III):**
   Adding any scalar multiple of one row to another row:
   $$
   R_i \leftarrow R_i + c R_j \quad (i \ne j)
   $$
   leaves the determinant strictly invariant:
   $$
   \det(A_{\text{after}}) = \det(A_{\text{before}})
   $$
   Because every entry in the first column of $A$ is $1$, subtracting $R_1$ from both $R_2$ and $R_3$ immediately introduces two leading zeros in Column 1 without any scaling or sign changes.

2. **Triangular Determinant Property:**
   Once a matrix is in upper-triangular form, its determinant is simply the product of its diagonal entries:
   $$
   \det U = u_{11} \cdot u_{22} \cdots u_{nn}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Create Zeros in the First Column

Starting with:
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 1 & 3 & 4 \\ 1 & 4 & 6 \end{pmatrix}
$$

We use the leading pivot $1$ in Row 1 to eliminate the entries below it:

1. **Operation 1:** $R_2 \leftarrow R_2 - R_1$
   - *Determinant status:* **Unchanged** (Type III operation).
   - Computation:
     $$
     \begin{pmatrix} 1 & 3 & 4 \end{pmatrix} - \begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} 0 & 1 & 1 \end{pmatrix}
     $$

2. **Operation 2:** $R_3 \leftarrow R_3 - R_1$
   - *Determinant status:* **Unchanged** (Type III operation).
   - Computation:
     $$
     \begin{pmatrix} 1 & 4 & 6 \end{pmatrix} - \begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} 0 & 2 & 3 \end{pmatrix}
     $$

After these two operations, the matrix is:
$$
A_1 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 2 & 3 \end{pmatrix}
$$
with $\det A = \det A_1$.

---

### Step 2: Create a Zero in the Second Column

Using the pivot $1$ in position $(2, 2)$, eliminate the entry $2$ in position $(3, 2)$:

3. **Operation 3:** $R_3 \leftarrow R_3 - 2R_2$
   - *Determinant status:* **Unchanged** (Type III operation).
   - Computation:
     $$
     \begin{pmatrix} 0 & 2 & 3 \end{pmatrix} - 2\begin{pmatrix} 0 & 1 & 1 \end{pmatrix} = \begin{pmatrix} 0 & 2 - 2 & 3 - 2 \end{pmatrix} = \begin{pmatrix} 0 & 0 & 1 \end{pmatrix}
     $$

The matrix is now completely reduced to upper-triangular form:
$$
A_2 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 0 & 1 \end{pmatrix}
$$
with $\det A = \det A_2$.

---

### Step 3: Compute the Determinant

Since $A_2$ is upper triangular, its determinant is the product of its diagonal elements:
$$
\det A_2 = 1 \cdot 1 \cdot 1 = 1
$$

Because all three operations ($R_2 \leftarrow R_2 - R_1$, $R_3 \leftarrow R_3 - R_1$, and $R_3 \leftarrow R_3 - 2R_2$) were Type III row operations, none changed the determinant:
$$
\det A = 1
$$

---

## 4. Verification and Consistency Checks

1. **Direct Calculation via Sarrus' Rule:**
   $$
   \begin{array}{ccc|cc}
   1 & 2 & 3 & 1 & 2 \\
   1 & 3 & 4 & 1 & 3 \\
   1 & 4 & 6 & 1 & 4
   \end{array}
   $$
   - Downward diagonals:
     $$
     (1)(3)(6) + (2)(4)(1) + (3)(1)(4) = 18 + 8 + 12 = 38
     $$
   - Upward diagonals:
     $$
     (1)(3)(3) + (4)(4)(1) + (6)(1)(2) = 9 + 16 + 12 = 37
     $$
   - Difference:
     $$
     \det A = 38 - 37 = 1 \quad \checkmark
     $$

2. **Laplace Expansion Along Column 1 of Matrix $A_1$:**
   From $A_1 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 2 & 3 \end{pmatrix}$:
   $$
   \det A_1 = 1 \cdot \det\begin{pmatrix} 1 & 1 \\ 2 & 3 \end{pmatrix} - 0 + 0 = 1 \cdot ((1)(3) - (1)(2)) = 1 \cdot (3 - 2) = 1 \quad \checkmark
   $$
