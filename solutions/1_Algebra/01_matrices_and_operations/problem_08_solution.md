# Solution to Exercise 8: Row Operations and Their Reversibility

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix}
$$

Perform, in order, the following elementary row operations:
1. $R_2 \leftarrow R_2 - 2R_1$
2. $R_3 \leftarrow R_3 + R_1$
3. Interchange $R_2$ and $R_3$

Write the matrix after each step. Then, for each of the three operations, state the corresponding inverse row operation that reverses it.

---

## 2. Theoretical Background and Concepts

1. **Elementary Row Operations:**
   There are three types of elementary row operations:
   - **Type I (Row Swap):** Interchanging two rows: $R_i \leftrightarrow R_j$.
   - **Type II (Row Scaling):** Multiplying a row by a non-zero scalar $c \ne 0$: $R_i \leftarrow c R_i$.
   - **Type III (Row Addition/Replacement):** Adding a scalar multiple of one row to another row: $R_i \leftarrow R_i + c R_j$ ($i \ne j$).

2. **Reversibility of Elementary Row Operations:**
   Every elementary row operation is completely invertible. That is, if a row operation transforms matrix $M$ to $M'$, there is another elementary row operation of the same type that transforms $M'$ back into $M$:
   - The inverse of adding $c R_j$ to $R_i$ ($R_i \leftarrow R_i + c R_j$) is subtracting $c R_j$ from $R_i$ ($R_i \leftarrow R_i - c R_j$).
   - The inverse of swapping $R_i$ and $R_j$ ($R_i \leftrightarrow R_j$) is swapping them again ($R_i \leftrightarrow R_j$).
   - The inverse of scaling $R_i$ by $c \ne 0$ is scaling $R_i$ by $1/c$.

3. **Connection to Elementary Matrices:**
   Each row operation corresponds to pre-multiplying by an invertible elementary matrix $E$: $A' = EA$, with inverse $A = E^{-1} A'$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Perform $R_2 \leftarrow R_2 - 2R_1$

Starting with:
$$
A = \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix}
$$

Subtract $2$ times Row 1 from Row 2:
$$
R_2 - 2R_1 = \begin{pmatrix} 2 & 4 & 1 \end{pmatrix} - 2\begin{pmatrix} 1 & 2 & -1 \end{pmatrix} = \begin{pmatrix} 2 - 2 & 4 - 4 & 1 - (-2) \end{pmatrix} = \begin{pmatrix} 0 & 0 & 3 \end{pmatrix}
$$

Rows 1 and 3 remain unchanged:
$$
A_1 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix}
$$

- **Reversing Operation:**
  To undo subtracting $2R_1$ from $R_2$, add $2R_1$ back to $R_2$:
  $$
  R_2 \leftarrow R_2 + 2R_1
  $$

---

### Step 2: Perform $R_3 \leftarrow R_3 + R_1$

Applying this to $A_1$:
$$
A_1 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix}
$$

Add Row 1 to Row 3:
$$
R_3 + R_1 = \begin{pmatrix} -1 & 1 & 3 \end{pmatrix} + \begin{pmatrix} 1 & 2 & -1 \end{pmatrix} = \begin{pmatrix} -1 + 1 & 1 + 2 & 3 + (-1) \end{pmatrix} = \begin{pmatrix} 0 & 3 & 2 \end{pmatrix}
$$

Rows 1 and 2 remain unchanged:
$$
A_2 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix}
$$

- **Reversing Operation:**
  To undo adding $R_1$ to $R_3$, subtract $R_1$ from $R_3$:
  $$
  R_3 \leftarrow R_3 - R_1
  $$

---

### Step 3: Interchange $R_2$ and $R_3$

Applying this to $A_2$:
$$
A_2 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix}
$$

Swap the second and third rows:
- The new Row 2 becomes the old Row 3: $\begin{pmatrix} 0 & 3 & 2 \end{pmatrix}$.
- The new Row 3 becomes the old Row 2: $\begin{pmatrix} 0 & 0 & 3 \end{pmatrix}$.

$$
A_3 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 2 \\ 0 & 0 & 3 \end{pmatrix}
$$

- **Reversing Operation:**
  Interchanging two rows is its own inverse (an involution). To undo the swap, interchange the two rows again:
  $$
  R_2 \leftrightarrow R_3 \quad (\text{or } \text{interchange } R_2 \text{ and } R_3)
  $$

---

## 4. Verification and Consistency Checks

1. **Reconstruction Verification (Applying the Inverses in Reverse Order):**
   Start from the final matrix $A_3$ and apply the reverse operations in reverse order:
   - Apply $R_2 \leftrightarrow R_3$ to $A_3$:
     $$
     \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 2 \\ 0 & 0 & 3 \end{pmatrix} \xrightarrow{R_2 \leftrightarrow R_3} \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix} = A_2 \quad \checkmark
     $$
   - Apply $R_3 \leftarrow R_3 - R_1$ to $A_2$:
     $$
     \begin{pmatrix} 0 & 3 & 2 \end{pmatrix} - \begin{pmatrix} 1 & 2 & -1 \end{pmatrix} = \begin{pmatrix} -1 & 1 & 3 \end{pmatrix}
     $$
     $$
     \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix} \xrightarrow{R_3 \leftarrow R_3 - R_1} \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix} = A_1 \quad \checkmark
     $$
   - Apply $R_2 \leftarrow R_2 + 2R_1$ to $A_1$:
     $$
     \begin{pmatrix} 0 & 0 & 3 \end{pmatrix} + 2\begin{pmatrix} 1 & 2 & -1 \end{pmatrix} = \begin{pmatrix} 2 & 4 & 1 \end{pmatrix}
     $$
     $$
     \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix} \xrightarrow{R_2 \leftarrow R_2 + 2R_1} \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix} = A \quad \checkmark
     $$
   The original matrix $A$ is precisely recovered.

2. **Determinant Invariance Check:**
   - Type III operations leave the determinant unchanged.
   - Type I operations (row swap) multiply the determinant by $-1$.
   - The triangular matrix $A_3$ has determinant $\det(A_3) = 1 \cdot 3 \cdot 3 = 9$.
   - Thus, $\det(A) = -\det(A_3) = -9$.
   - Direct determinant of $A$ by cofactor expansion along row 1:
     $$
     \det(A) = 1(12 - 1) - 2(6 - (-1)) + (-1)(2 - (-4)) = 1(11) - 2(7) - 1(6) = 11 - 14 - 6 = -9 \quad \checkmark
     $$
   This verifies the arithmetic of all row operations.
