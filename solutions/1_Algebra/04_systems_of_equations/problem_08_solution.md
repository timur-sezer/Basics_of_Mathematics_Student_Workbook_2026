# Solution to Exercise 8: Two Systems with the Same Coefficient Matrix

## 1. Problem Statement

Solve by Gaussian elimination the two linear systems:
$$
\text{System 1: } \begin{cases} 2x + y = 5, \\ x - y = 1, \end{cases} \qquad \text{System 2: } \begin{cases} 2x + y = 1, \\ x - y = 4. \end{cases}
$$

Compare the successive elimination steps. Identify which part of the calculation is identical in both cases, and explain why this occurs from both an algebraic and structural perspective.

---

## 2. Theoretical Background and Concepts

1. **Matrix Representation with Multiple Right-Hand Sides:**
   Both systems share the same coefficient matrix $A$, but have different right-hand side vectors $b_1$ and $b_2$:
   $$
   A = \begin{pmatrix} 2 & 1 \\ 1 & -1 \end{pmatrix}, \quad b_1 = \begin{pmatrix} 5 \\ 1 \end{pmatrix}, \quad b_2 = \begin{pmatrix} 1 \\ 4 \end{pmatrix}
   $$
   We can express both problems simultaneously using a combined augmented matrix:
   $$
   [A \mid b_1 \mid b_2] = \left(\begin{array}{cc|c|c} 2 & 1 & 5 & 1 \\ 1 & -1 & 1 & 4 \end{array}\right)
   $$

2. **Independence of Row Operations from the Right-Hand Side:**
   Elementary row operations are chosen entirely based on the entries of $A$ to eliminate sub-diagonal coefficients and produce pivots. The multipliers and the row combinations depend exclusively on $A$. The right-hand side vectors passively undergo the exact same row operations dictated by $A$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Solving System 1

Write the augmented matrix $[A \mid b_1]$:
$$
[A \mid b_1] = \left(\begin{array}{cc|c} 2 & 1 & 5 \\ 1 & -1 & 1 \end{array}\right)
$$

1. **Row interchange ($R_1 \leftrightarrow R_2$)** to obtain a pivot of $1$ in the first column:
   $$
   \left(\begin{array}{cc|c} 1 & -1 & 1 \\ 2 & 1 & 5 \end{array}\right)
   $$
2. **Eliminate the entry below the pivot ($R_2 \leftarrow R_2 - 2R_1$):**
   - Left side: $\begin{pmatrix} 2 & 1 \end{pmatrix} - 2\begin{pmatrix} 1 & -1 \end{pmatrix} = \begin{pmatrix} 0 & 3 \end{pmatrix}$
   - Right side: $5 - 2(1) = 3$
   $$
   \left(\begin{array}{cc|c} 1 & -1 & 1 \\ 0 & 3 & 3 \end{array}\right)
   $$
3. **Back-substitution:**
   - From Row 2: $3y = 3 \implies y = 1$
   - From Row 1: $x - y = 1 \implies x - 1 = 1 \implies x = 2$

**Solution to System 1:**
$$
\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 2 \\ 1 \end{pmatrix}
$$

---

### Step 2: Solving System 2

Write the augmented matrix $[A \mid b_2]$:
$$
[A \mid b_2] = \left(\begin{array}{cc|c} 2 & 1 & 1 \\ 1 & -1 & 4 \end{array}\right)
$$

1. **Row interchange ($R_1 \leftrightarrow R_2$):**
   $$
   \left(\begin{array}{cc|c} 1 & -1 & 4 \\ 2 & 1 & 1 \end{array}\right)
   $$
2. **Eliminate the entry below the pivot ($R_2 \leftarrow R_2 - 2R_1$):**
   - Left side: $\begin{pmatrix} 2 & 1 \end{pmatrix} - 2\begin{pmatrix} 1 & -1 \end{pmatrix} = \begin{pmatrix} 0 & 3 \end{pmatrix}$
   - Right side: $1 - 2(4) = 1 - 8 = -7$
   $$
   \left(\begin{array}{cc|c} 1 & -1 & 4 \\ 0 & 3 & -7 \end{array}\right)
   $$
3. **Back-substitution:**
   - From Row 2: $3y = -7 \implies y = -\frac{7}{3}$
   - From Row 1: $x - y = 4 \implies x - \left(-\frac{7}{3}\right) = 4 \implies x + \frac{7}{3} = \frac{12}{3} \implies x = \frac{5}{3}$

**Solution to System 2:**
$$
\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} \frac{5}{3} \\ -\frac{7}{3} \end{pmatrix}
$$

---

### Step 3: Comparative Analysis of the Steps

1. **What is identical:**
   - The choice of row operations: swapping $R_1 \leftrightarrow R_2$ and subtracting $2R_1$ from $R_2$.
   - The entire left-hand side of the augmented matrix at every step:
     $$
     \begin{pmatrix} 2 & 1 \\ 1 & -1 \end{pmatrix} \xrightarrow{R_1 \leftrightarrow R_2} \begin{pmatrix} 1 & -1 \\ 2 & 1 \end{pmatrix} \xrightarrow{R_2 - 2R_1} \begin{pmatrix} 1 & -1 \\ 0 & 3 \end{pmatrix}
     $$
   - The coefficients of the triangular system used during back-substitution ($3y = \dots$ and $x - y = \dots$).

2. **Why this occurs:**
   - The elementary row operations that transform a system into upper triangular form are solely governed by the linear relationships between the variable coefficients in $A$.
   - The right-hand side vectors $b_1$ and $b_2$ are passively transformed by the same elementary matrices:
     $$
     E = E_2 E_1 = \begin{pmatrix} 1 & 0 \\ -2 & 1 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 1 \\ 1 & -2 \end{pmatrix}
     $$
   - Because $E$ depends only on $A$, $E A$ produces the exact same upper triangular matrix $\begin{pmatrix} 1 & -1 \\ 0 & 3 \end{pmatrix}$ regardless of whether it is applied to $b_1$ or $b_2$.
   - This structural invariance shows that solving multiple systems with the same coefficient matrix is best performed by row-reducing the multi-augmented matrix $[A \mid b_1 \mid b_2]$ simultaneously.

---

## 4. Verification and Consistency Checks

1. **Substitute System 1 solution $(2, 1)$:**
   - Equation 1: $2(2) + 1 = 4 + 1 = 5$ (Matches $b_1^{(1)} \checkmark$)
   - Equation 2: $2 - 1 = 1$ (Matches $b_1^{(2)} \checkmark$)

2. **Substitute System 2 solution $\left(\frac{5}{3}, -\frac{7}{3}\right)$:**
   - Equation 1: $2\left(\frac{5}{3}\right) + \left(-\frac{7}{3}\right) = \frac{10 - 7}{3} = \frac{3}{3} = 1$ (Matches $b_2^{(1)} \checkmark$)
   - Equation 2: $\frac{5}{3} - \left(-\frac{7}{3}\right) = \frac{5 + 7}{3} = \frac{12}{3} = 4$ (Matches $b_2^{(2)} \checkmark$)

3. **Simultaneous Augmented Matrix Check:**
   $$
   \left(\begin{array}{cc|c|c} 2 & 1 & 5 & 1 \\ 1 & -1 & 1 & 4 \end{array}\right) \xrightarrow{R_1 \leftrightarrow R_2} \left(\begin{array}{cc|c|c} 1 & -1 & 1 & 4 \\ 2 & 1 & 5 & 1 \end{array}\right) \xrightarrow{R_2 - 2R_1} \left(\begin{array}{cc|c|c} 1 & -1 & 1 & 4 \\ 0 & 3 & 3 & -7 \end{array}\right)
   $$
   Both solutions emerge directly from the simultaneous reduction, validating the mathematical reasoning.
