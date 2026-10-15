# Solution to Exercise 2: A Line in Space

## 1. Problem Statement

Given the parametric equation of a line $L$ in three-dimensional space $\mathbb{R}^3$:
$$
L: (x, y, z) = (2, -1, 3) + t(1, 2, -2), \quad t \in \mathbb{R}
$$

1. Identify a base point $P_0$ lying on the line and state its direction vector $v$.
2. Determine whether the point $P = (4, 3, -1)$ lies on the line $L$.
3. Compute the coordinates of the point on $L$ corresponding to the parameter value $t = -1$.

---

## 2. Theoretical Background and Concepts

1. **Parametric Form of a Line in $\mathbb{R}^3$:**
   In three dimensions, a line cannot be represented by a single linear scalar equation. It is represented either by a system of two intersecting planes or parametrically as a vector function of a real parameter $t$:
   $$
   X(t) = P_0 + t v
   $$
   where:
   - $P_0 = (x_0, y_0, z_0)$ is the position vector of a known base point on the line (at $t = 0$),
   - $v = (v_x, v_y, v_z) \ne (0, 0, 0)$ is the direction vector specifying the orientation of the line in space.

2. **Incidence Criterion (Point on a Line):**
   A point $P(x_P, y_P, z_P)$ lies on the line $L$ if and only if there exists a **single, unique scalar** $t \in \mathbb{R}$ that simultaneously satisfies all three component equations:
   $$
   \begin{cases}
   x_0 + t v_x = x_P \\
   y_0 + t v_y = y_P \\
   z_0 + t v_z = z_P
   \end{cases}
   $$
   If the values of $t$ obtained from individual coordinates are inconsistent, the point does not lie on the line.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Base Point and Direction Vector

Comparing the given equation:
$$
(x, y, z) = (2, -1, 3) + t(1, 2, -2)
$$
with the standard form $X(t) = P_0 + t v$:

- **Base Point:** Setting $t = 0$ gives the point:
  $$
  P_0 = (2, -1, 3)
  $$
- **Direction Vector:** The vector multiplied by parameter $t$ is:
  $$
  v = (1, 2, -2)
  $$

---

### Step 2: Test Whether Point $P(4, 3, -1)$ Lies on Line $L$

Set the coordinates of $P(4, 3, -1)$ equal to the parametric expressions:
$$
\begin{cases}
2 + t = 4, & \text{(Equation 1)} \\
-1 + 2t = 3, & \text{(Equation 2)} \\
3 - 2t = -1. & \text{(Equation 3)}
\end{cases}
$$

1. **Solve for $t$ using Equation 1 ($x$-coordinate):**
   $$
   2 + t = 4 \implies t = 2
   $$

2. **Check consistency in Equation 2 ($y$-coordinate):**
   $$
   -1 + 2(2) = -1 + 4 = 3 \quad (\checkmark \text{Matches } y_P = 3)
   $$

3. **Check consistency in Equation 3 ($z$-coordinate):**
   $$
   3 - 2(2) = 3 - 4 = -1 \quad (\checkmark \text{Matches } z_P = -1)
   $$

Because the single parameter value $t = 2$ satisfies all three coordinate equations simultaneously, **the point $P(4, 3, -1)$ lies on line $L$**.

---

### Step 3: Compute the Point Corresponding to $t = -1$

Substitute $t = -1$ into the parametric equation:
$$
X(-1) = \begin{pmatrix} 2 \\ -1 \\ 3 \end{pmatrix} + (-1) \begin{pmatrix} 1 \\ 2 \\ -2 \end{pmatrix}
$$
Evaluate component by component:
- $x = 2 + (-1)(1) = 2 - 1 = 1$
- $y = -1 + (-1)(2) = -1 - 2 = -3$
- $z = 3 + (-1)(-2) = 3 + 2 = 5$

Thus, the point corresponding to $t = -1$ is:
$$
Q = (1, -3, 5)
$$

---

## 4. Verification and Consistency Checks

1. **Collinearity Check via Cross Product:**
   For point $P(4, 3, -1)$, the displacement vector from $P_0(2, -1, 3)$ is:
   $$
   \overrightarrow{P_0 P} = P - P_0 = (4 - 2, 3 - (-1), -1 - 3) = (2, 4, -4)
   $$
   Notice:
   $$
   \overrightarrow{P_0 P} = \begin{pmatrix} 2 \\ 4 \\ -4 \end{pmatrix} = 2 \begin{pmatrix} 1 \\ 2 \\ -2 \end{pmatrix} = 2v
   $$
   Because $\overrightarrow{P_0 P}$ is a direct scalar multiple of $v$, the vectors are parallel, which guarantees that $P$ lies on the line.

2. **Symmetric Form (Cartesian Canonical Equations):**
   Solving each coordinate equation for $t$:
   $$
   \frac{x - 2}{1} = \frac{y + 1}{2} = \frac{z - 3}{-2} = t
   $$
   - Test $P(4, 3, -1)$:
     $$
     \frac{4 - 2}{1} = \frac{3 + 1}{2} = \frac{-1 - 3}{-2} \implies \frac{2}{1} = \frac{4}{2} = \frac{-4}{-2} = 2 \quad (\checkmark)
     $$
   - Test $Q(1, -3, 5)$:
     $$
     \frac{1 - 2}{1} = \frac{-3 + 1}{2} = \frac{5 - 3}{-2} \implies \frac{-1}{1} = \frac{-2}{2} = \frac{2}{-2} = -1 \quad (\checkmark)
     $$
