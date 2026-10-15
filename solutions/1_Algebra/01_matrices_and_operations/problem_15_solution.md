# Solution to Exercise 15: Associativity of Multiplication and Different Calculation Paths

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}, \qquad C = \begin{pmatrix} 2 & 1 \\ 0 & -1 \end{pmatrix}
$$

1. Compute $(AB)C$.
2. Compute $A(BC)$.
3. Compare the results and count the intermediate scalar arithmetic operations required for each calculation path.
4. Explain what the associativity of matrix multiplication means in this example.

---

## 2. Theoretical Background and Concepts

1. **Associativity of Matrix Multiplication:**
   For any matrices $A, B, C$ whose compatible sizes permit the products $(AB)C$ and $A(BC)$, the associative property guarantees:
   $$
   (AB)C = A(BC)
   $$
   This algebraic property is a direct consequence of the fact that matrix multiplication represents the composition of linear transformations, and function composition is always associative:
   $$
   ((T_A \circ T_B) \circ T_C)(v) = (T_A \circ (T_B \circ T_C))(v)
   $$

2. **Computational Complexity (Matrix Chain Multiplication):**
   Although the mathematical result is identical regardless of parenthesization, the number of arithmetic operations can vary significantly depending on the order of multiplications.
   Multiplying an $m \times k$ matrix by a $k \times p$ matrix requires:
   - $m \cdot k \cdot p$ scalar multiplications,
   - $m \cdot (k - 1) \cdot p$ scalar additions.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $(AB)C$ (Path 1)

1. **First Product: $AB$**
   Matrix $A$ has size $2 \times 3$ and matrix $B$ has size $3 \times 2$. The product $AB$ has size $2 \times 2$:
   $$
   AB = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}
   $$
   Computing entries:
   - $(1, 1)$: $1(1) + 2(2) + 0(-1) = 1 + 4 + 0 = 5$
   - $(1, 2)$: $1(0) + 2(1) + 0(3) = 0 + 2 + 0 = 2$
   - $(2, 1)$: $0(1) + 1(2) + 1(-1) = 0 + 2 - 1 = 1$
   - $(2, 2)$: $0(0) + 1(1) + 1(3) = 0 + 1 + 3 = 4$

   $$
   AB = \begin{pmatrix} 5 & 2 \\ 1 & 4 \end{pmatrix}
   $$

2. **Second Product: $(AB)C$**
   Multiply $(AB)_{2 \times 2}$ by $C_{2 \times 2}$:
   $$
   (AB)C = \begin{pmatrix} 5 & 2 \\ 1 & 4 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & -1 \end{pmatrix}
   $$
   Computing entries:
   - $(1, 1)$: $5(2) + 2(0) = 10 + 0 = 10$
   - $(1, 2)$: $5(1) + 2(-1) = 5 - 2 = 3$
   - $(2, 1)$: $1(2) + 4(0) = 2 + 0 = 2$
   - $(2, 2)$: $1(1) + 4(-1) = 1 - 4 = -3$

   $$
   (AB)C = \begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix}
   $$

---

### Step 2: Compute $A(BC)$ (Path 2)

1. **First Product: $BC$**
   Matrix $B$ has size $3 \times 2$ and matrix $C$ has size $2 \times 2$. The product $BC$ has size $3 \times 2$:
   $$
   BC = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & -1 \end{pmatrix}
   $$
   Computing entries:
   - $(1, 1)$: $1(2) + 0(0) = 2$
   - $(1, 2)$: $1(1) + 0(-1) = 1$
   - $(2, 1)$: $2(2) + 1(0) = 4 + 0 = 4$
   - $(2, 2)$: $2(1) + 1(-1) = 2 - 1 = 1$
   - $(3, 1)$: $(-1)(2) + 3(0) = -2 + 0 = -2$
   - $(3, 2)$: $(-1)(1) + 3(-1) = -1 - 3 = -4$

   $$
   BC = \begin{pmatrix} 2 & 1 \\ 4 & 1 \\ -2 & -4 \end{pmatrix}
   $$

2. **Second Product: $A(BC)$**
   Multiply $A_{2 \times 3}$ by $(BC)_{3 \times 2}$:
   $$
   A(BC) = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 4 & 1 \\ -2 & -4 \end{pmatrix}
   $$
   Computing entries:
   - $(1, 1)$: $1(2) + 2(4) + 0(-2) = 2 + 8 + 0 = 10$
   - $(1, 2)$: $1(1) + 2(1) + 0(-4) = 1 + 2 + 0 = 3$
   - $(2, 1)$: $0(2) + 1(4) + 1(-2) = 0 + 4 - 2 = 2$
   - $(2, 2)$: $0(1) + 1(1) + 1(-4) = 0 + 1 - 4 = -3$

   $$
   A(BC) = \begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix}
   $$

---

### Step 3: Comparison and Operation Count

Both calculation paths yield the exact same resulting matrix:
$$
(AB)C = A(BC) = \begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix}
$$

**Operation Count Comparison:**

1. **Path 1: $(AB)C$**
   - For $AB$ ($2 \times 3$ by $3 \times 2$): $2 \cdot 3 \cdot 2 = 12$ multiplications and $2 \cdot 2 \cdot 2 = 8$ additions.
   - For $(AB)C$ ($2 \times 2$ by $2 \times 2$): $2 \cdot 2 \cdot 2 = 8$ multiplications and $2 \cdot 1 \cdot 2 = 4$ additions.
   - **Total Path 1:** $12 + 8 = 20$ multiplications, $8 + 4 = 12$ additions (**$32$ total arithmetic operations**).

2. **Path 2: $A(BC)$**
   - For $BC$ ($3 \times 2$ by $2 \times 2$): $3 \cdot 2 \cdot 2 = 12$ multiplications and $3 \cdot 1 \cdot 2 = 6$ additions.
   - For $A(BC)$ ($2 \times 3$ by $3 \times 2$): $2 \cdot 3 \cdot 2 = 12$ multiplications and $2 \cdot 2 \cdot 2 = 8$ additions.
   - **Total Path 2:** $12 + 12 = 24$ multiplications, $6 + 8 = 14$ additions (**$38$ total arithmetic operations**).

Path 1 requires $20$ multiplications versus $24$ multiplications in Path 2. This shows that parenthesization influences computational cost even when the mathematical result is identical.

---

### Step 4: Meaning of Associativity in this Example

In this example, associativity means:
- The geometric transformation represented by the sequence of operations $C$ followed by $B$ followed by $A$ does not depend on whether we view $AB$ as an intermediate composite operator applied to $C$, or $BC$ as an intermediate operator pre-composed with $A$.
- Parentheses can be omitted entirely without ambiguity, allowing the product to be written simply as $ABC$.

---

## 4. Verification and Consistency Checks

1. **Vector Evaluation Check:**
   Apply both forms to the test vector $v = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$:
   - From our final matrix:
     $$
     (ABC)v = \begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix} \begin{pmatrix} 1 \\ 1 \end{pmatrix} = \begin{pmatrix} 13 \\ -1 \end{pmatrix}
     $$
   - Evaluating step-by-step from right to left:
     $$
     Cv = \begin{pmatrix} 2 & 1 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 1 \\ 1 \end{pmatrix} = \begin{pmatrix} 3 \\ -1 \end{pmatrix}
     $$
     $$
     B(Cv) = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix} \begin{pmatrix} 3 \\ -1 \end{pmatrix} = \begin{pmatrix} 3 + 0 \\ 6 - 1 \\ -3 - 3 \end{pmatrix} = \begin{pmatrix} 3 \\ 5 \\ -6 \end{pmatrix}
     $$
     $$
     A(B(Cv)) = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 3 \\ 5 \\ -6 \end{pmatrix} = \begin{pmatrix} 3 + 10 + 0 \\ 0 + 5 - 6 \end{pmatrix} = \begin{pmatrix} 13 \\ -1 \end{pmatrix} \quad \checkmark
     $$
   The action on an arbitrary vector confirms the validity of the computed matrix product.

