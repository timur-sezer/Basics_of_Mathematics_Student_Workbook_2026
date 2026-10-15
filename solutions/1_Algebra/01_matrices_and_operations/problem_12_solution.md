# Solution to Exercise 12: Formula for a Matrix Power

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}
$$

1. Compute $A^2$, $A^3$, and $A^4$.
2. Formulate a general conjecture for $A^n$ for any positive integer $n \in \mathbb{N}_{\ge 1}$.
3. Prove the formula using mathematical induction: assume the formula holds for $n$, multiply by $A$, and demonstrate that it yields the formula for $n + 1$.

---

## 2. Theoretical Background and Concepts

1. **Matrix Powers:**
   For a square matrix $A$, higher powers are defined iteratively by $A^1 = A$ and $A^{k+1} = A^k A$.

2. **Principle of Mathematical Induction:**
   To prove a statement $P(n)$ is true for all positive integers $n \ge 1$:
   - **Base Case:** Prove $P(1)$ is true.
   - **Inductive Hypothesis:** Assume $P(n)$ is true for an arbitrary integer $n \ge 1$.
   - **Inductive Step:** Show that $P(n) \implies P(n+1)$ is true using matrix multiplication.
   - **Conclusion:** By induction, $P(n)$ holds for all $n \ge 1$.

3. **Geometric Interpretation (Shear Mapping):**
   The matrix $A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$ represents a standard horizontal shear parallel to the $x$-axis:
   $$
   \begin{pmatrix} x \\ y \end{pmatrix} \mapsto \begin{pmatrix} x + y \\ y \end{pmatrix}
   $$
   Applying this transformation repeatedly adds the vertical height $y$ to the horizontal coordinate $x$ at each iteration.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute Small Powers $A^2$, $A^3$, and $A^4$

- **Compute $A^2$:**
  $$
  A^2 = A \cdot A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + 1(0) & 1(1) + 1(1) \\ 0(1) + 1(0) & 0(1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}
  $$

- **Compute $A^3$:**
  $$
  A^3 = A^2 \cdot A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + 2(0) & 1(1) + 2(1) \\ 0(1) + 1(0) & 0(1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix}
  $$

- **Compute $A^4$:**
  $$
  A^4 = A^3 \cdot A = \begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + 3(0) & 1(1) + 3(1) \\ 0(1) + 1(0) & 0(1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 4 \\ 0 & 1 \end{pmatrix}
  $$

### Step 2: Formulate the Conjecture for $A^n$

Observing the sequence of powers:
$$
A^1 = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}, \quad A^2 = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}, \quad A^3 = \begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix}, \quad A^4 = \begin{pmatrix} 1 & 4 \\ 0 & 1 \end{pmatrix}
$$
In every case:
- The diagonal entries are constantly $1$.
- The bottom-left entry is constantly $0$.
- The top-right entry equals the exponent $n$.

**Conjecture:** For all integers $n \ge 1$:
$$
A^n = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix}
$$

### Step 3: Proof by Mathematical Induction

1. **Base Case ($n = 1$):**
   For $n = 1$:
   $$
   \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = A^1
   $$
   The formula holds for the base case.

2. **Inductive Hypothesis:**
   Assume that for some integer $n \ge 1$, the formula holds:
   $$
   A^n = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix}
   $$

3. **Inductive Step ($n \to n + 1$):**
   We compute $A^{n+1}$ by multiplying the assumed form of $A^n$ by $A$:
   $$
   A^{n+1} = A^n \cdot A = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}
   $$
   Carrying out the matrix multiplication:
   - Entry $(1, 1)$: $1 \cdot 1 + n \cdot 0 = 1$
   - Entry $(1, 2)$: $1 \cdot 1 + n \cdot 1 = 1 + n = n + 1$
   - Entry $(2, 1)$: $0 \cdot 1 + 1 \cdot 0 = 0$
   - Entry $(2, 2)$: $0 \cdot 1 + 1 \cdot 1 = 1$

   Therefore:
   $$
   A^{n+1} = \begin{pmatrix} 1 & n + 1 \\ 0 & 1 \end{pmatrix}
   $$
   This is precisely the conjectured formula evaluated at $n + 1$.

4. **Conclusion:**
   By the principle of mathematical induction, the formula:
   $$
   A^n = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix}
   $$
   is true for every positive integer $n \in \mathbb{N}_{\ge 1}$.

---

## 4. Verification and Consistency Checks

1. **Binomial Expansion Check:**
   Write $A = I + N$ where $I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$ and $N = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$.
   Since $IN = NI = N$, we can use the binomial theorem:
   $$
   N^2 = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} = 0
   $$
   Thus $N^k = 0$ for all $k \ge 2$.
   $$
   A^n = (I + N)^n = I^n + \binom{n}{1} I^{n-1} N + \sum_{k=2}^n \binom{n}{k} I^{n-k} N^k = I + nN
   $$
   Substituting $I$ and $N$:
   $$
   I + nN = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} + n \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix}
   $$
   This algebraic check confirms the inductive result independently.

2. **Exponent Law Check:**
   Verify $A^m A^n = A^{m+n}$:
   $$
   \begin{pmatrix} 1 & m \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & n + m \\ 0 & 1 \end{pmatrix} = A^{m+n} \quad \checkmark
   $$
   The exponent laws hold for all $m, n \in \mathbb{N}$.
