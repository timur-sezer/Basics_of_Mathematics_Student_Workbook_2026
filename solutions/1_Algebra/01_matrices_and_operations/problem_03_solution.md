# Solution to Exercise 3: When Can Matrices Be Multiplied?

## 1. Problem Statement

The matrix sizes are given as:
$$
A_{2 \times 3}, \qquad B_{3 \times 4}, \qquad C_{4 \times 2}, \qquad D_{2 \times 2}
$$

For the eight products:
$$
AB, \quad BA, \quad BC, \quad CB, \quad AC, \quad CA, \quad AD, \quad DA
$$
determine whether each product is defined. If defined, state the size of the resulting matrix. Justify each decision using the dimension compatibility condition.

---

## 2. Theoretical Background and Concepts

1. **Dimension Compatibility Condition for Matrix Multiplication:**
   The matrix product $M \cdot N$ of two matrices $M$ and $N$ is defined if and only if the **number of columns in the first matrix $M$ equals the number of rows in the second matrix $N$**.

2. **Size of the Resulting Product Matrix:**
   If matrix $M$ has size $m \times k$ and matrix $N$ has size $k \times p$, then:
   - The inner dimensions match ($k = k$).
   - The product $MN$ is well-defined and has size given by the outer dimensions:
     $$
     (M_{m \times k}) \cdot (N_{k \times p}) = (MN)_{m \times p}
     $$

3. **Why the Condition is Necessary:**
   Each entry of the product matrix $(MN)_{ij}$ is computed as the dot product (inner product) of the $i$-th row of $M$ with the $j$-th column of $N$:
   $$
   (MN)_{ij} = \sum_{r=1}^k m_{ir} n_{rj}
   $$
   For this sum to exist, the row vector $\mathbf{r}_i(M)$ and the column vector $\mathbf{c}_j(N)$ must have the exact same number of scalar components ($k$).

---

## 3. Detailed Step-by-Step Solution

We analyze each of the eight products systematically:

### 1. Product $AB$
- Dimensions: $A_{2 \times 3}$ and $B_{3 \times 4}$.
- Number of columns of $A$ is $3$; number of rows of $B$ is $3$.
- Compatibility check: $3 = 3$ (compatible).
- **Result:** **Defined**, with size **$2 \times 4$**.

### 2. Product $BA$
- Dimensions: $B_{3 \times 4}$ and $A_{2 \times 3}$.
- Number of columns of $B$ is $4$; number of rows of $A$ is $2$.
- Compatibility check: $4 \ne 2$ (incompatible).
- **Result:** **Undefined**.

### 3. Product $BC$
- Dimensions: $B_{3 \times 4}$ and $C_{4 \times 2}$.
- Number of columns of $B$ is $4$; number of rows of $C$ is $4$.
- Compatibility check: $4 = 4$ (compatible).
- **Result:** **Defined**, with size **$3 \times 2$**.

### 4. Product $CB$
- Dimensions: $C_{4 \times 2}$ and $B_{3 \times 4}$.
- Number of columns of $C$ is $2$; number of rows of $B$ is $3$.
- Compatibility check: $2 \ne 3$ (incompatible).
- **Result:** **Undefined**.

### 5. Product $AC$
- Dimensions: $A_{2 \times 3}$ and $C_{4 \times 2}$.
- Number of columns of $A$ is $3$; number of rows of $C$ is $4$.
- Compatibility check: $3 \ne 4$ (incompatible).
- **Result:** **Undefined**.

### 6. Product $CA$
- Dimensions: $C_{4 \times 2}$ and $A_{2 \times 3}$.
- Number of columns of $C$ is $2$; number of rows of $A$ is $2$.
- Compatibility check: $2 = 2$ (compatible).
- **Result:** **Defined**, with size **$4 \times 3$**.

### 7. Product $AD$
- Dimensions: $A_{2 \times 3}$ and $D_{2 \times 2}$.
- Number of columns of $A$ is $3$; number of rows of $D$ is $2$.
- Compatibility check: $3 \ne 2$ (incompatible).
- **Result:** **Undefined**.

### 8. Product $DA$
- Dimensions: $D_{2 \times 2}$ and $A_{2 \times 3}$.
- Number of columns of $D$ is $2$; number of rows of $A$ is $2$.
- Compatibility check: $2 = 2$ (compatible).
- **Result:** **Defined**, with size **$2 \times 3$**.

---

## 4. Verification and Consistency Checks

1. **Summary Table:**

   | Product | Left Dimension | Right Dimension | Inner Dimensions | Status | Resulting Size |
   | :---: | :---: | :---: | :---: | :---: | :---: |
   | $AB$ | $2 \times 3$ | $3 \times 4$ | $3 = 3$ | **Defined** | $2 \times 4$ |
   | $BA$ | $3 \times 4$ | $2 \times 3$ | $4 \ne 2$ | **Undefined** | — |
   | $BC$ | $3 \times 4$ | $4 \times 2$ | $4 = 4$ | **Defined** | $3 \times 2$ |
   | $CB$ | $4 \times 2$ | $3 \times 4$ | $2 \ne 3$ | **Undefined** | — |
   | $AC$ | $2 \times 3$ | $4 \times 2$ | $3 \ne 4$ | **Undefined** | — |
   | $CA$ | $4 \times 2$ | $2 \times 3$ | $2 = 2$ | **Defined** | $4 \times 3$ |
   | $AD$ | $2 \times 3$ | $2 \times 2$ | $3 \ne 2$ | **Undefined** | — |
   | $DA$ | $2 \times 2$ | $2 \times 3$ | $2 = 2$ | **Defined** | $2 \times 3$ |

2. **Noncommutativity of Definability:**
   - Notice that while $AB$ is defined ($2 \times 4$), its reverse product $BA$ is completely undefined.
   - Similarly, $BC$ is defined ($3 \times 2$), while $CB$ is undefined.
   - $AC$ is undefined, while $CA$ is defined ($4 \times 3$).
   - $AD$ is undefined, while $DA$ is defined ($2 \times 3$).
   This illustrates that matrix multiplication does not commute even at the level of whether the operation can be formed.
