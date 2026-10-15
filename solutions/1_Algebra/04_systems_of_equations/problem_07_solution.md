# Solution to Exercise 7: Choosing a Method Deliberately

## 1. Problem Statement

Do not solve all of the following systems completely. For each situation, choose the method that best exploits its structure and justify your choice:

1. **Case 1:** One system with a triangular coefficient matrix:
   $$
   \begin{cases}
   2x - y = 3, \\
   4y = 8.
   \end{cases}
   $$
2. **Case 2:** Three systems $Ax = b_i$ ($i = 1, 2, 3$) with the same invertible matrix $A$, where the inverse matrix $A^{-1}$ is already known.
3. **Case 3:** One $3 \times 3$ system for which the inverse matrix is not given and the goal is only to find one solution vector.

**Instructions:**
- For **Case 1**, carry out the chosen method completely.
- For **Cases 2 and 3**, describe the plan and indicate which part of the computation would be reusable or unnecessary.
- Refer explicitly to the number of right-hand sides and the structural properties of the coefficient matrix rather than judging methods merely by name.

---

## 2. Theoretical Background and Concepts

1. **Triangular Systems and Back-Substitution:**
   A system whose coefficient matrix is upper or lower triangular requires no forward elimination operations. The unknowns can be solved sequentially via direct back-substitution (or forward-substitution) in $\mathcal{O}(n^2)$ arithmetic operations, compared to $\mathcal{O}(n^3)$ for general elimination.

2. **Computational Cost Comparison:**
   - **Gaussian Elimination (Single RHS):** Solving $[A \mid b]$ takes approximately $\frac{2}{3}n^3 + \mathcal{O}(n^2)$ floating-point operations (flops).
   - **Matrix Inversion:** Computing $A^{-1}$ via $[A \mid I_n]$ requires approximately $2n^3$ flops (roughly $3$ times the work of solving a single system).
   - **Matrix-Vector Multiplication:** Multiplying a known $n \times n$ matrix by an $n \times 1$ vector requires exactly $n^2$ multiplications and $n(n-1)$ additions, which is $\mathcal{O}(n^2)$ flops.

3. **Multi-RHS Problem Structure:**
   When solving $Ax = b_i$ for multiple right-hand sides $b_1, b_2, \dots, b_k$:
   - If $A^{-1}$ is already known, each solution is obtained via a single matrix-vector multiplication $x_i = A^{-1}b_i$ in $\mathcal{O}(n^2)$ time.
   - If $A^{-1}$ is not known, simultaneous Gaussian elimination on $[A \mid b_1 \mid b_2 \mid \dots \mid b_k]$ or an $LU$ decomposition is far more efficient than computing $A^{-1}$.

---

## 3. Detailed Step-by-Step Solution

### Case 1: Triangular System

#### Selection and Justification:
The system can be written in matrix form as:
$$
\begin{pmatrix}
2 & -1 \\
0 & 4
\end{pmatrix}
\begin{pmatrix}
x \\
y
\end{pmatrix}
=
\begin{pmatrix}
3 \\
8
\end{pmatrix}
$$
The coefficient matrix is already **upper triangular** (the sub-diagonal entry is zero). Performing row elimination is completely unnecessary because the variable $y$ is already decoupled in the second equation. The optimal method is **direct back-substitution**.

#### Complete Execution:
1. **Solve for $y$ from the bottom equation:**
   $$
   4y = 8 \implies y = \frac{8}{4} = 2
   $$
2. **Substitute $y = 2$ into the top equation to solve for $x$:**
   $$
   2x - y = 3 \implies 2x - 2 = 3 \implies 2x = 5 \implies x = \frac{5}{2}
   $$

The unique solution is:
$$
\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} \frac{5}{2} \\ 2 \end{pmatrix}
$$

---

### Case 2: Three Systems with the Same Invertible Matrix and Known $A^{-1}$

#### Selection and Justification:
- **Optimal Method:** **Direct matrix-vector multiplication**, $x_i = A^{-1}b_i$ for each $i \in \{1, 2, 3\}$.
- **Justification:**
  - Finding a matrix inverse from scratch is typically computationally expensive ($\mathcal{O}(n^3)$). However, in this scenario, $A^{-1}$ is **already provided/precomputed**.
  - Evaluating each solution requires only one matrix-vector multiplication:
    $$
    x_1 = A^{-1}b_1, \quad x_2 = A^{-1}b_2, \quad x_3 = A^{-1}b_3
    $$
  - Each multiplication requires only $\mathcal{O}(n^2)$ operations. For $n = 3$, each product takes only $3^2 = 9$ scalar multiplications and $6$ additions.

#### Reusable vs. Unnecessary Computation:
- **Reusable Component:** The precomputed inverse $A^{-1}$ is reused completely across all three systems. It acts as a static linear operator mapping each input vector $b_i$ directly to its corresponding state vector $x_i$.
- **Unnecessary Computation:** Re-running Gaussian elimination on each augmented matrix $[A \mid b_i]$ separately would require repeating the forward elimination on $A$ three separate times. That would perform redundant row operations that have already been codified inside $A^{-1}$.

---

### Case 3: One $3 \times 3$ System with Unknown $A^{-1}$

#### Selection and Justification:
- **Optimal Method:** **Gaussian elimination with back-substitution** applied directly to the augmented matrix $[A \mid b]$.
- **Justification:**
  - We only need a single solution vector $x$ for one specific right-hand side $b$.
  - Solving the single system via Gaussian elimination with back-substitution on the augmented matrix $[A \mid b]$ directly produces the solution vector without the computational overhead of constructing the full inverse matrix.
  - Inverting a matrix requires transforming $[A \mid I_3] \to [I_3 \mid A^{-1}]$, which is structurally equivalent to solving 3 separate systems simultaneously (one for each canonical basis vector $e_1, e_2, e_3$).

#### Reusable vs. Unnecessary Computation:
- **Unnecessary Computation:** Computing $A^{-1}$ constructs all $9$ entries of the full inverse matrix. Because only a single solution vector is required, explicitly calculating all nine entries is unnecessary when only the specific linear combination $A^{-1}b$ is sought. Gaussian elimination computes this target vector directly.
- **Reusable Component:** In a single-solve scenario, there is no subsequent step to reuse data. However, if multiple future vectors $b$ were anticipated, computing the $LU$ factorization ($A = LU$) would be the standard alternative, enabling reuse via forward and backward substitutions without constructing $A^{-1}$ explicitly.

---

## 4. Verification and Consistency Checks

1. **Verification of Case 1 Solution:**
   Substitute $(x, y) = \left(\frac{5}{2}, 2\right)$ into the original equations:
   - Equation 1: $2\left(\frac{5}{2}\right) - 2 = 5 - 2 = 3$ (Matches RHS $\checkmark$)
   - Equation 2: $4(2) = 8$ (Matches RHS $\checkmark$)

2. **Structural Decision Summary Matrix:**

| Scenario | Structure / Given Data | Recommended Method | Relative Complexity | Key Rationale |
| :--- | :--- | :--- | :--- | :--- |
| **Case 1** | Upper triangular coefficient matrix | Back-substitution | $\mathcal{O}(n^2)$ | Elimination is already completed by problem structure. |
| **Case 2** | Multiple RHS ($k=3$), $A^{-1}$ precomputed | Matrix multiplication $x_i = A^{-1}b_i$ | $3 \times \mathcal{O}(n^2)$ | Exploits the precomputed inverse; avoids redundant row reductions. |
| **Case 3** | Single RHS ($k=1$), $A^{-1}$ unknown | Gaussian elimination on $[A \mid b]$ | Direct elimination | Avoids computing all entries of the full inverse matrix. |
