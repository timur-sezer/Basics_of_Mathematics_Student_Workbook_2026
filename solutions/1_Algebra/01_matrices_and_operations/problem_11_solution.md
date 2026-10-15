# Solution to Exercise 11: When Do Matrices Commute?

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} a & b \\ c & d \end{pmatrix}
$$

1. Find the necessary and sufficient conditions on the entries $a, b, c, d$ under which $AB = BA$.
2. Describe the general form of all such matrices $B$ that commute with $A$.

---

## 2. Theoretical Background and Concepts

1. **Commutativity of Matrices:**
   Two square matrices $A$ and $B$ of the same dimension commute if their commutator vanishes:
   $$
   [A, B] = AB - BA = 0 \iff AB = BA
   $$
   While matrix multiplication is noncommutative in general, the set of matrices that commute with a given matrix $A$ forms a subspace and a subring of $M_n(\mathbb{R})$, called the **centralizer** (or commutant) of $A$, denoted $C(A)$.

2. **Polynomials in $A$:**
   Any scalar multiple of the identity $aI$ and any polynomial $p(A) = c_0 I + c_1 A + \dots + c_k A^k$ commutes with $A$. For non-diagonalizable $2 \times 2$ matrices with a single eigenvalue (such as the shear matrix $A$), the centralizer consists precisely of the polynomials in $A$ of degree at most $1$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Product $AB$

Multiply $A$ by $B$:
$$
AB = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} a & b \\ c & d \end{pmatrix}
$$

Computing each entry:
- Entry $(1, 1)$: $(1)(a) + (1)(c) = a + c$
- Entry $(1, 2)$: $(1)(b) + (1)(d) = b + d$
- Entry $(2, 1)$: $(0)(a) + (1)(c) = c$
- Entry $(2, 2)$: $(0)(b) + (1)(d) = d$

Thus:
$$
AB = \begin{pmatrix} a + c & b + d \\ c & d \end{pmatrix}
$$

### Step 2: Compute the Product $BA$

Multiply $B$ by $A$:
$$
BA = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}
$$

Computing each entry:
- Entry $(1, 1)$: $(a)(1) + (b)(0) = a$
- Entry $(1, 2)$: $(a)(1) + (b)(1) = a + b$
- Entry $(2, 1)$: $(c)(1) + (d)(0) = c$
- Entry $(2, 2)$: $(c)(1) + (d)(1) = c + d$

Thus:
$$
BA = \begin{pmatrix} a & a + b \\ c & c + d \end{pmatrix}
$$

### Step 3: Equate $AB$ and $BA$ Entry-by-Entry

Setting $AB = BA$ yields the system of four equations:
1. **Entry $(1, 1)$:**
   $$
   a + c = a \implies c = 0
   $$
2. **Entry $(1, 2)$:**
   $$
   b + d = a + b \implies d = a
   $$
3. **Entry $(2, 1)$:**
   $$
   c = c \implies \text{satisfied for all } c
   $$
4. **Entry $(2, 2)$:**
   $$
   d = c + d \implies c = 0
   $$

From equations (1) and (4), we obtain **$c = 0$**.
From equation (2), we obtain **$d = a$**.
The parameter $b$ can be **any real number**, and $a$ can be **any real number**.

### Step 4: Describe the General Form of Matrix $B$

Substituting $c = 0$ and $d = a$ into $B$:
$$
B = \begin{pmatrix} a & b \\ 0 & a \end{pmatrix}, \qquad \text{for any } a, b \in \mathbb{R}
$$

**Structural Description:**
Any commuting matrix $B$ can be written as:
$$
B = a \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} + b \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = a I + b (A - I) = (a - b)I + bA
$$
This demonstrates that the commuting matrices are precisely the upper triangular matrices with equal diagonal entries, or equivalently, linear combinations of the identity matrix $I$ and matrix $A$.

---

## 4. Verification and Consistency Checks

1. **Direct Substitution Check:**
   Let $B = \begin{pmatrix} a & b \\ 0 & a \end{pmatrix}$. Compute both products:
   - $AB$:
     $$
     AB = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} a & b \\ 0 & a \end{pmatrix} = \begin{pmatrix} 1(a) + 1(0) & 1(b) + 1(a) \\ 0(a) + 1(0) & 0(b) + 1(a) \end{pmatrix} = \begin{pmatrix} a & a + b \\ 0 & a \end{pmatrix}
     $$
   - $BA$:
     $$
     BA = \begin{pmatrix} a & b \\ 0 & a \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} a(1) + b(0) & a(1) + b(1) \\ 0(1) + a(0) & 0(1) + a(1) \end{pmatrix} = \begin{pmatrix} a & a + b \\ 0 & a \end{pmatrix}
     $$
   Since $AB = BA = \begin{pmatrix} a & a + b \\ 0 & a \end{pmatrix}$ holds for all $a, b \in \mathbb{R}$, the solution is both necessary and sufficient.

2. **Counterexample for Non-Commuting Case:**
   Choose a matrix violating $c = 0$, say $c = 1$ with $a = 1, b = 0, d = 1$:
   $$
   B' = \begin{pmatrix} 1 & 0 \\ 1 & 1 \end{pmatrix} \implies AB' = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}, \quad B'A = \begin{pmatrix} 1 & 1 \\ 1 & 2 \end{pmatrix} \ne AB'
   $$
   Confirming that $c = 0$ is strictly required.
