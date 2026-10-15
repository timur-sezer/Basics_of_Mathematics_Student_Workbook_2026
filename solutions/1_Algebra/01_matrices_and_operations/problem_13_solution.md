# Solution to Exercise 13: A Recurrence Written in Matrix Form

## 1. Problem Statement

Given the matrix:
$$
F = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix}
$$

1. Compute the powers $F^2$, $F^3$, $F^4$, and $F^5$.
2. Compare the resulting matrix entries with the Fibonacci sequence:
   $$
   0, 1, 1, 2, 3, 5, 8, \dots
   $$
   and describe the relationship observed.
3. Compute the product:
   $$
   F \begin{pmatrix} a \\ b \end{pmatrix}
   $$
4. Explain how this matrix-vector multiplication models one step of the Fibonacci recurrence.

---

## 2. Theoretical Background and Concepts

1. **The Fibonacci Recurrence:**
   The Fibonacci sequence $(f_n)_{n \ge 0}$ is defined by the initial conditions and recurrence relation:
   $$
   f_0 = 0, \quad f_1 = 1, \quad f_{n+1} = f_n + f_{n-1} \quad (n \ge 1)
   $$
   The sequence begins:
   $$
   f_0=0, \; f_1=1, \; f_2=1, \; f_3=2, \; f_4=3, \; f_5=5, \; f_6=8, \; f_7=13, \; \dots
   $$

2. **Matrix Representation of Linear Recurrences:**
   A second-order linear recurrence can be transformed into a first-order system of difference equations by bundling consecutive terms into a state vector:
   $$
   \mathbf{v}_n = \begin{pmatrix} f_{n+1} \\ f_n \end{pmatrix}
   $$
   The transition between consecutive states $\mathbf{v}_n \to \mathbf{v}_{n+1}$ is governed by a transition matrix $F$:
   $$
   \mathbf{v}_{n+1} = F \mathbf{v}_n \implies \mathbf{v}_n = F^n \mathbf{v}_0
   $$

3. **Cassini's Identity:**
   Taking the determinant on both sides of $F^n = \begin{pmatrix} f_{n+1} & f_n \\ f_n & f_{n-1} \end{pmatrix}$ gives:
   $$
   \det(F^n) = (\det F)^n = (-1)^n \implies f_{n+1}f_{n-1} - f_n^2 = (-1)^n
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute Small Powers of $F$

- **Compute $F^2$:**
  $$
  F^2 = F \cdot F = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 1(1) + 1(1) & 1(1) + 1(0) \\ 1(1) + 0(1) & 1(1) + 0(0) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}
  $$

- **Compute $F^3$:**
  $$
  F^3 = F^2 \cdot F = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 2(1) + 1(1) & 2(1) + 1(0) \\ 1(1) + 1(1) & 1(1) + 1(0) \end{pmatrix} = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix}
  $$

- **Compute $F^4$:**
  $$
  F^4 = F^3 \cdot F = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 3(1) + 2(1) & 3(1) + 2(0) \\ 2(1) + 1(1) & 2(1) + 1(0) \end{pmatrix} = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix}
  $$

- **Compute $F^5$:**
  $$
  F^5 = F^4 \cdot F = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 5(1) + 3(1) & 5(1) + 3(0) \\ 3(1) + 2(1) & 3(1) + 2(0) \end{pmatrix} = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix}
  $$

---

### Step 2: Comparison with the Fibonacci Sequence

Listing the Fibonacci numbers:
$$
f_0 = 0, \quad f_1 = 1, \quad f_2 = 1, \quad f_3 = 2, \quad f_4 = 3, \quad f_5 = 5, \quad f_6 = 8
$$

Expressing each calculated power using Fibonacci notation:
- $F^1 = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} f_2 & f_1 \\ f_1 & f_0 \end{pmatrix}$
- $F^2 = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} = \begin{pmatrix} f_3 & f_2 \\ f_2 & f_1 \end{pmatrix}$
- $F^3 = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix} = \begin{pmatrix} f_4 & f_3 \\ f_3 & f_2 \end{pmatrix}$
- $F^4 = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix} = \begin{pmatrix} f_5 & f_4 \\ f_4 & f_3 \end{pmatrix}$
- $F^5 = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix} = \begin{pmatrix} f_6 & f_5 \\ f_5 & f_4 \end{pmatrix}$

**Observed Relationship:**
For every integer $n \ge 1$, the $n$-th power of $F$ consists entirely of Fibonacci numbers:
$$
F^n = \begin{pmatrix} f_{n+1} & f_n \\ f_n & f_{n-1} \end{pmatrix}
$$

---

### Step 3: Compute $F \begin{pmatrix} a \\ b \end{pmatrix}$

Multiply the matrix $F$ by the arbitrary vector $\begin{pmatrix} a \\ b \end{pmatrix}$:
$$
F \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} 1 \cdot a + 1 \cdot b \\ 1 \cdot a + 0 \cdot b \end{pmatrix} = \begin{pmatrix} a + b \\ a \end{pmatrix}
$$

---

### Step 4: Explanation of the Recurrence Step

Suppose the input vector holds two consecutive terms of a Fibonacci-like sequence:
$$
\begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} f_k \\ f_{k-1} \end{pmatrix}
$$

Applying the matrix transformation yields:
$$
F \begin{pmatrix} f_k \\ f_{k-1} \end{pmatrix} = \begin{pmatrix} f_k + f_{k-1} \\ f_k \end{pmatrix} = \begin{pmatrix} f_{k+1} \\ f_k \end{pmatrix}
$$

This matrix-vector operation performs two vital tasks simultaneously:
1. **Generates the next term:** The first row computes the sum $f_k + f_{k-1} = f_{k+1}$, advancing the recurrence.
2. **Updates the memory (shift register):** The second row simply copies the current term $f_k$ to the bottom position, ensuring it is ready to be used as the predecessor in the next recurrence step.

Thus, multiplying by $F$ precisely advances the sequence by one step.

---

## 4. Verification and Consistency Checks

1. **Inductive Step Check:**
   Assume $F^n = \begin{pmatrix} f_{n+1} & f_n \\ f_n & f_{n-1} \end{pmatrix}$. Then:
   $$
   F^{n+1} = F^n \cdot F = \begin{pmatrix} f_{n+1} & f_n \\ f_n & f_{n-1} \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} f_{n+1} + f_n & f_{n+1} \\ f_n + f_{n-1} & f_n \end{pmatrix} = \begin{pmatrix} f_{n+2} & f_{n+1} \\ f_{n+1} & f_n \end{pmatrix}
   $$
   This proves the general matrix formula for all $n \ge 1$ by mathematical induction.

2. **Cassini's Identity Check on $F^5$:**
   - $\det(F) = 1(0) - 1(1) = -1$.
   - $\det(F^5) = (\det F)^5 = (-1)^5 = -1$.
   - From our computed matrix entries:
     $$
     \det(F^5) = \det\begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix} = (8)(3) - (5)(5) = 24 - 25 = -1 \quad \checkmark
     $$
   The determinant identity holds perfectly.

