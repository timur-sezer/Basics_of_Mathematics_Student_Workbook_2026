# Solution to Exercise 11: Decomposition into Parallel and Perpendicular Components

## 1. Problem Statement

Given the vectors in $\mathbb{R}^2$:
$$
u = (3, 4), \qquad v = (1, 2)
$$

1. Decompose vector $u$ into two components:
   - A component $u_{\parallel}$ parallel to $v$,
   - A component $u_{\perp}$ perpendicular to $v$.
2. Verify both of the following conditions:
   $$
   u = u_{\parallel} + u_{\perp}, \qquad u_{\perp} \cdot v = 0
   $$
3. Explain why verifying both equations provides two mathematically independent checks of correctness.

---

## 2. Theoretical Background and Concepts

1. **Orthogonal Decomposition Theorem:**
   Let $v \ne \mathbf{0}$ be a fixed vector in an inner product space $V$, and let $L = \operatorname{span}(v)$ be the 1-dimensional subspace spanned by $v$.
   Every vector $u \in V$ can be decomposed uniquely as:
   $$
   u = u_{\parallel} + u_{\perp}
   $$
   where $u_{\parallel} \in L$ and $u_{\perp} \in L^\perp$ (the orthogonal complement of $L$).

2. **Formulas for the Components:**
   - **Parallel component (orthogonal projection onto $v$):**
     $$
     u_{\parallel} = \operatorname{proj}_v u = \left(\frac{u \cdot v}{\|v\|^2}\right) v
     $$
   - **Perpendicular component (rejection/residual):**
     $$
     u_{\perp} = u - u_{\parallel}
     $$

3. **Geometric Minimization Property:**
   $u_{\parallel}$ is the unique vector in $\operatorname{span}(v)$ that minimizes the distance $\|u - c v\|$. The error vector $u_{\perp} = u - u_{\parallel}$ is orthogonal to every vector in $\operatorname{span}(v)$, ensuring that $\|u_{\perp}\|$ is the exact Euclidean distance from $u$ to the line $\operatorname{span}(v)$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Parallel Component $u_{\parallel}$

1. **Calculate the dot product $u \cdot v$:**
   $$
   u \cdot v = (3)(1) + (4)(2) = 3 + 8 = 11
   $$

2. **Calculate the squared norm $\|v\|^2$:**
   $$
   \|v\|^2 = 1^2 + 2^2 = 1 + 4 = 5
   $$

3. **Compute the scalar projection factor:**
   $$
   c = \frac{u \cdot v}{\|v\|^2} = \frac{11}{5} = 2.2
   $$

4. **Multiply $v$ by the scalar factor:**
   $$
   u_{\parallel} = \frac{11}{5} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} \frac{11}{5} \\ \frac{22}{5} \end{pmatrix} = \begin{pmatrix} 2.2 \\ 4.4 \end{pmatrix}
   $$

In row notation:
$$
u_{\parallel} = \left(\frac{11}{5}, \frac{22}{5}\right)
$$

---

### Step 2: Compute the Perpendicular Component $u_{\perp}$

Subtract $u_{\parallel}$ from $u$:
$$
u_{\perp} = u - u_{\parallel} = \begin{pmatrix} 3 \\ 4 \end{pmatrix} - \begin{pmatrix} \frac{11}{5} \\ \frac{22}{5} \end{pmatrix}
$$
Express $u$ with a common denominator of $5$:
$$
u = \begin{pmatrix} \frac{15}{5} \\ \frac{20}{5} \end{pmatrix}
$$
Subtract the components:
$$
u_{\perp} = \begin{pmatrix} \frac{15 - 11}{5} \\ \frac{20 - 22}{5} \end{pmatrix} = \begin{pmatrix} \frac{4}{5} \\ -\frac{2}{5} \end{pmatrix} = \begin{pmatrix} 0.8 \\ -0.4 \end{pmatrix}
$$

In row notation:
$$
u_{\perp} = \left(\frac{4}{5}, -\frac{2}{5}\right)
$$

---

### Step 3: Perform the Two Verifications

1. **Verification 1: Additive Completeness ($u = u_{\parallel} + u_{\perp}$):**
   $$
   u_{\parallel} + u_{\perp} = \begin{pmatrix} \frac{11}{5} \\ \frac{22}{5} \end{pmatrix} + \begin{pmatrix} \frac{4}{5} \\ -\frac{2}{5} \end{pmatrix} = \begin{pmatrix} \frac{11 + 4}{5} \\ \frac{22 - 2}{5} \end{pmatrix} = \begin{pmatrix} \frac{15}{5} \\ \frac{20}{5} \end{pmatrix} = \begin{pmatrix} 3 \\ 4 \end{pmatrix} = u \quad (\checkmark)
   $$

2. **Verification 2: Orthogonality ($u_{\perp} \cdot v = 0$):**
   $$
   u_{\perp} \cdot v = \left(\frac{4}{5}\right)(1) + \left(-\frac{2}{5}\right)(2) = \frac{4}{5} - \frac{4}{5} = 0 \quad (\checkmark)
   $$

Both conditions are verified.

---

### Step 4: Why These Are Two Independent Checks

The two tests check two entirely different properties of the decomposition:

1. **Test 1 ($u = u_{\parallel} + u_{\perp}$) checks Vector Conservation (Completeness):**
   - This test verifies purely that no part of vector $u$ was lost during the algebraic splitting.
   - However, by itself, this test is **not sufficient** to guarantee a valid projection. For example, if someone arbitrarily chose $u_{\parallel} = (1, 1)$ and $u_{\perp} = (2, 3)$, their sum would equal $(3, 4) = u$, passing Test 1 completely, even though $(1, 1)$ is not parallel to $v$ and $(2, 3)$ is not perpendicular to $v$.
2. **Test 2 ($u_{\perp} \cdot v = 0$) checks Geometric Orthogonality:**
   - This test verifies that the error vector makes a right angle ($90^\circ$) with the reference direction $v$.
   - However, by itself, Test 2 is also **not sufficient**. For example, the vector $w = (2, -1)$ satisfies $w \cdot v = 2(1) + (-1)(2) = 0$, but $w$ has no connection to vector $u$.
3. **Independence and Sufficiency:**
   - If one miscalculated the projection coefficient (e.g., writing $c = 2$ instead of $\frac{11}{5}$), computing $u_{\perp} = u - 2v$ would still trivially satisfy $u_{\parallel} + u_{\perp} = u$, but it would **fail** $u_{\perp} \cdot v = 0$.
   - Therefore, the two conditions check independent degrees of freedom: one checks that the components sum to the target vector, and the other checks that the orientation is precisely orthogonal. Together, they form necessary and sufficient conditions for the unique orthogonal decomposition.

---

## 4. Verification and Consistency Checks

1. **Pythagorean Norm Check:**
   - $\|u\|^2 = 3^2 + 4^2 = 9 + 16 = 25$
   - $\|u_{\parallel}\|^2 = \left(\frac{11}{5}\right)^2 + \left(\frac{22}{5}\right)^2 = \frac{121 + 484}{25} = \frac{605}{25} = \frac{121}{5} = 24.2$
   - $\|u_{\perp}\|^2 = \left(\frac{4}{5}\right)^2 + \left(-\frac{2}{5}\right)^2 = \frac{16 + 4}{25} = \frac{20}{25} = \frac{4}{5} = 0.8$
   - $\|u_{\parallel}\|^2 + \|u_{\perp}\|^2 = 24.2 + 0.8 = 25.0 = \|u\|^2 \quad (\checkmark)$

2. **Collinearity Check for $u_{\parallel}$ and $v$:**
   $$
   u_{\parallel} = \begin{pmatrix} 2.2 \\ 4.4 \end{pmatrix} = 2.2 \begin{pmatrix} 1 \\ 2 \end{pmatrix} = 2.2 v \quad (\checkmark)
   $$
   The parallel component is confirmed to be an exact scalar multiple of $v$.
