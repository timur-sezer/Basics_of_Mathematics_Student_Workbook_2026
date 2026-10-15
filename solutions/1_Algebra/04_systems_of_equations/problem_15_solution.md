# Solution to Exercise 15: Classifying Three Systems

## 1. Problem Statement

For each of the following three linear systems, perform only as much Gaussian elimination as necessary to determine its type:

1. **System 1:**
   $$
   \begin{cases}
   x + y = 2, \\
   x - y = 0.
   \end{cases}
   $$

2. **System 2:**
   $$
   \begin{cases}
   x + y = 2, \\
   2x + 2y = 4.
   \end{cases}
   $$

3. **System 3:**
   $$
   \begin{cases}
   x + y = 2, \\
   2x + 2y = 5.
   \end{cases}
   $$

**Instructions:**
- Perform minimal row elimination to establish the echelon structure.
- Justify the classification for each system: **exactly one solution**, **infinitely many solutions**, or **no solution**.

---

## 2. Theoretical Background and Concepts

1. **The Three Fundamental Cases (Rouché–Capelli Classification):**
   Given an $m \times n$ system $Ax = b$, Gaussian elimination reduces the augmented matrix $[A \mid b]$ to row echelon form:
   - **Case I: Exactly One Solution**
     Occurs when $\operatorname{rank}(A) = \operatorname{rank}[A \mid b] = n$. Every column contains a pivot, leaving zero free variables.
   - **Case II: Infinitely Many Solutions**
     Occurs when $\operatorname{rank}(A) = \operatorname{rank}[A \mid b] < n$. The system is consistent, but at least one column lacks a pivot, yielding $n - \operatorname{rank}(A)$ free variables.
   - **Case III: No Solution (Inconsistent)**
     Occurs when $\operatorname{rank}(A) < \operatorname{rank}[A \mid b]$. A contradiction row of the form $\left(\begin{array}{cc|c} 0 & 0 & c \end{array}\right)$ with $c \ne 0$ arises ($0 = c$).

2. **Geometric View in $\mathbb{R}^2$:**
   - Case I: Two lines with different slopes intersecting at a single point.
   - Case II: Two identical, coincident lines sharing infinitely many points.
   - Case III: Two distinct, parallel lines that never intersect.

---

## 3. Detailed Step-by-Step Solution

### System 1: Classification via Minimal Elimination

1. **Set up the augmented matrix:**
   $$
   [A \mid b] = \left(\begin{array}{cc|c}
   1 & 1 & 2 \\
   1 & -1 & 0
   \end{array}\right)
   $$

2. **Perform one elementary row operation ($R_2 \leftarrow R_2 - R_1$):**
   - Left side: $\begin{pmatrix} 1 & -1 \end{pmatrix} - \begin{pmatrix} 1 & 1 \end{pmatrix} = \begin{pmatrix} 0 & -2 \end{pmatrix}$
   - Right side: $0 - 2 = -2$

   $$
   \left(\begin{array}{cc|c}
   1 & 1 & 2 \\
   0 & -2 & -2
   \end{array}\right)
   $$

3. **Structural Analysis and Classification:**
   - Both diagonal positions contain non-zero pivots: $1$ in column 1, and $-2$ in column 2.
   - $\operatorname{rank}(A) = 2$ and $\operatorname{rank}[A \mid b] = 2$.
   - Since $\operatorname{rank}(A) = n = 2$, there are no free variables and no contradictions.
   - *(Optional solve: $-2y = -2 \implies y = 1$, then $x + 1 = 2 \implies x = 1$.)*

**Classification:** **Exactly one solution** (unique solution at $(1, 1)$).

---

### System 2: Classification via Minimal Elimination

1. **Set up the augmented matrix:**
   $$
   [A \mid b] = \left(\begin{array}{cc|c}
   1 & 1 & 2 \\
   2 & 2 & 4
   \end{array}\right)
   $$

2. **Perform one elementary row operation ($R_2 \leftarrow R_2 - 2R_1$):**
   - Left side: $\begin{pmatrix} 2 & 2 \end{pmatrix} - 2\begin{pmatrix} 1 & 1 \end{pmatrix} = \begin{pmatrix} 0 & 0 \end{pmatrix}$
   - Right side: $4 - 2(2) = 4 - 4 = 0$

   $$
   \left(\begin{array}{cc|c}
   1 & 1 & 2 \\
   0 & 0 & 0
   \end{array}\right)
   $$

3. **Structural Analysis and Classification:**
   - Row 2 has vanished completely into zeros: $0 \cdot x + 0 \cdot y = 0$, which is trivially true ($0 = 0$).
   - $\operatorname{rank}(A) = 1$ and $\operatorname{rank}[A \mid b] = 1$.
   - Because the system is consistent and $\operatorname{rank}(A) < n$ ($1 < 2$), there is $n - \operatorname{rank}(A) = 2 - 1 = 1$ free variable ($y = t$, $x = 2 - t$).

**Classification:** **Infinitely many solutions** (the two equations describe the same line).

---

### System 3: Classification via Minimal Elimination

1. **Set up the augmented matrix:**
   $$
   [A \mid b] = \left(\begin{array}{cc|c}
   1 & 1 & 2 \\
   2 & 2 & 5
   \end{array}\right)
   $$

2. **Perform one elementary row operation ($R_2 \leftarrow R_2 - 2R_1$):**
   - Left side: $\begin{pmatrix} 2 & 2 \end{pmatrix} - 2\begin{pmatrix} 1 & 1 \end{pmatrix} = \begin{pmatrix} 0 & 0 \end{pmatrix}$
   - Right side: $5 - 2(2) = 5 - 4 = 1$

   $$
   \left(\begin{array}{cc|c}
   1 & 1 & 2 \\
   0 & 0 & 1
   \end{array}\right)
   $$

3. **Structural Analysis and Classification:**
   - Row 2 yields the statement:
     $$
     0 \cdot x + 0 \cdot y = 1 \implies 0 = 1 \quad (\text{Contradiction!})
     $$
   - Here, $\operatorname{rank}(A) = 1$, but $\operatorname{rank}[A \mid b] = 2$.
   - Because $\operatorname{rank}(A) < \operatorname{rank}[A \mid b]$, the augmented column introduces an extra pivot.

**Classification:** **No solution** (the system is inconsistent).

---

## 4. Verification and Consistency Checks

1. **Geometric Summary Verification:**

| System | Equation 1 Line ($L_1$) | Equation 2 Line ($L_2$) | Slopes ($m_1, m_2$) | Geometric State | Algebraic Classification |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **1** | $y = -x + 2$ | $y = x$ | $m_1 = -1, m_2 = 1$ | Non-parallel lines intersecting transversely | **One solution** |
| **2** | $y = -x + 2$ | $y = -x + 2$ | $m_1 = -1, m_2 = -1$ | Identical, coincident lines | **Infinitely many solutions** |
| **3** | $y = -x + 2$ | $y = -x + \frac{5}{2}$ | $m_1 = -1, m_2 = -1$ | Distinct parallel lines ($y$-intercepts $2 \ne 2.5$) | **No solution** |

2. **Minimal Operation Audit:**
   In all three cases, exactly **one single row operation** ($R_2 - R_1$ or $R_2 - 2R_1$) was sufficient to expose the pivot structure of the second row and immediately reveal the exact system category without superfluous computation.
