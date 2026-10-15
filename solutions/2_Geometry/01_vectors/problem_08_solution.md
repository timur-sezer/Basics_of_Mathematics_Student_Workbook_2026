# Solution to Exercise 8: Linear Combination and Checking the Result

## 1. Problem Statement

Given the vectors in $\mathbb{R}^2$:
$$
u = (1, 1), \qquad v = (2, -1), \qquad w = (5, 1)
$$

1. Determine whether $w$ can be expressed as a linear combination of $u$ and $v$:
   $$
   w = a u + b v
   $$
2. If so, find the unique scalar coefficients $a$ and $b$.
3. Reconstruct $w$ by evaluating $a u + b v$ with the calculated coefficients to verify consistency.
4. Explain the geometric meaning of the existence and uniqueness of such coefficients.

---

## 2. Theoretical Background and Concepts

1. **Linear Combinations and Basis in $\mathbb{R}^2$:**
   A vector $w$ is a linear combination of $u$ and $v$ if there exist scalars $a, b \in \mathbb{R}$ such that $a u + b v = w$.
   In vector components, this corresponds to the $2 \times 2$ linear system:
   $$
   \begin{pmatrix} u_1 & v_1 \\ u_2 & v_2 \end{pmatrix} \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} w_1 \\ w_2 \end{pmatrix}
   $$

2. **Linear Independence and Spanning:**
   Two vectors $u, v \in \mathbb{R}^2$ form a basis for $\mathbb{R}^2$ if and only if they are not collinear, which holds if and only if:
   $$
   \det \begin{pmatrix} u_1 & v_1 \\ u_2 & v_2 \end{pmatrix} = u_1 v_2 - u_2 v_1 \ne 0
   $$
   When $u$ and $v$ form a basis, **every** vector $w \in \mathbb{R}^2$ can be uniquely expressed as a linear combination of $u$ and $v$. The coefficients $(a, b)$ represent the coordinates of $w$ with respect to the basis $\{u, v\}$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up the Linear System for Coefficients $a$ and $b$

Write the vector equation $a u + b v = w$ in component form:
$$
a \begin{pmatrix} 1 \\ 1 \end{pmatrix} + b \begin{pmatrix} 2 \\ -1 \end{pmatrix} = \begin{pmatrix} 5 \\ 1 \end{pmatrix}
$$

This yields the system of two linear equations in unknowns $a$ and $b$:
$$
\begin{cases}
a + 2b = 5, & \text{(Equation 1)} \\
a - b = 1. & \text{(Equation 2)}
\end{cases}
$$

---

### Step 2: Solve the Linear System

1. **Subtract Equation 2 from Equation 1 to eliminate $a$:**
   $$
   (a + 2b) - (a - b) = 5 - 1
   $$
   $$
   3b = 4 \implies b = \frac{4}{3}
   $$

2. **Substitute $b = \frac{4}{3}$ into Equation 2 to find $a$:**
   $$
   a - \frac{4}{3} = 1 \implies a = 1 + \frac{4}{3} = \frac{7}{3}
   $$

Thus, $w$ can indeed be written as a linear combination of $u$ and $v$, with coefficients:
$$
a = \frac{7}{3}, \qquad b = \frac{4}{3}
$$

---

### Step 3: Reconstruct $w$ to Verify

Evaluate $a u + b v$ using the calculated values:
$$
a u + b v = \frac{7}{3} \begin{pmatrix} 1 \\ 1 \end{pmatrix} + \frac{4}{3} \begin{pmatrix} 2 \\ -1 \end{pmatrix}
$$
Multiply components by scalars:
$$
= \begin{pmatrix} \frac{7}{3} \\ \frac{7}{3} \end{pmatrix} + \begin{pmatrix} \frac{8}{3} \\ -\frac{4}{3} \end{pmatrix}
$$
Add the components:
$$
= \begin{pmatrix} \frac{7 + 8}{3} \\ \frac{7 - 4}{3} \end{pmatrix} = \begin{pmatrix} \frac{15}{3} \\ \frac{3}{3} \end{pmatrix} = \begin{pmatrix} 5 \\ 1 \end{pmatrix} = w \quad (\checkmark)
$$

The reconstructed vector matches $w = (5, 1)$ exactly.

---

### Step 4: Geometric Meaning of the Coefficients

1. **Non-Orthogonal (Oblique) Coordinate System:**
   - The standard basis vectors $e_1 = (1, 0)$ and $e_2 = (0, 1)$ define orthogonal Cartesian grid lines.
   - The vectors $u = (1, 1)$ and $v = (2, -1)$ are linearly independent since they point along different lines (slope of $u$ is $+1$, slope of $v$ is $-0.5$).
   - Together, $u$ and $v$ form an **oblique coordinate frame** spanning the entire plane $\mathbb{R}^2$.
2. **Reaching Point $W(5, 1)$ via Vector Scaling:**
   - To reach the target point $W(5, 1)$ from the origin, one travels $\frac{7}{3}$ units along the line of $u$, and then from that intermediate point travels $\frac{4}{3}$ units parallel to the direction of $v$.
   - The existence of $(a, b)$ proves that the plane spanned by $u$ and $v$ includes $w$.
   - The uniqueness of $(a, b)$ follows from the fact that $u$ and $v$ are non-collinear; there is only one parallelogram with sides parallel to $u$ and $v$ having the origin and $W$ as opposite vertices.

---

## 4. Verification and Consistency Checks

1. **Matrix Inversion Check:**
   The matrix form is $\begin{pmatrix} 1 & 2 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} 5 \\ 1 \end{pmatrix}$.
   - Determinant: $\det = (1)(-1) - (2)(1) = -1 - 2 = -3 \ne 0$.
   - Inverse matrix:
     $$
     \begin{pmatrix} 1 & 2 \\ 1 & -1 \end{pmatrix}^{-1} = \frac{1}{-3} \begin{pmatrix} -1 & -2 \\ -1 & 1 \end{pmatrix} = \begin{pmatrix} \frac{1}{3} & \frac{2}{3} \\ \frac{1}{3} & -\frac{1}{3} \end{pmatrix}
     $$
   - Solving directly:
     $$
     \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} \frac{1}{3} & \frac{2}{3} \\ \frac{1}{3} & -\frac{1}{3} \end{pmatrix} \begin{pmatrix} 5 \\ 1 \end{pmatrix} = \begin{pmatrix} \frac{5}{3} + \frac{2}{3} \\ \frac{5}{3} - \frac{1}{3} \end{pmatrix} = \begin{pmatrix} \frac{7}{3} \\ \frac{4}{3} \end{pmatrix} \quad (\checkmark)
     $$

2. **Cramer's Rule Verification:**
   $$
   a = \frac{\det\begin{pmatrix} 5 & 2 \\ 1 & -1 \end{pmatrix}}{-3} = \frac{-5 - 2}{-3} = \frac{-7}{-3} = \frac{7}{3} \quad (\checkmark)
   $$
   $$
   b = \frac{\det\begin{pmatrix} 1 & 5 \\ 1 & 1 \end{pmatrix}}{-3} = \frac{1 - 5}{-3} = \frac{-4}{-3} = \frac{4}{3} \quad (\checkmark)
   $$
