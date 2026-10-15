# Solution to Exercise 1: Line Through Two Points

## 1. Problem Statement

Given the two points in the Cartesian plane $\mathbb{R}^2$:
$$
A = (1, 2), \qquad B = (4, -1)
$$

1. Find the equation of the line passing through $A$ and $B$ in **parametric vector form**.
2. Find the equation of the line in **general (implicit) form** $Ax + By + C = 0$.
3. Identify a direction vector $v$ and an example of a normal vector $n$.
4. Check that both points $A$ and $B$ satisfy the general equation obtained.

---

## 2. Theoretical Background and Concepts

1. **Direction Vector and Parametric Form:**
   In $\mathbb{R}^n$, a straight line passing through a point $A$ with non-zero direction vector $v$ is parameterized by:
   $$
   X(t) = A + t v, \quad t \in \mathbb{R}
   $$
   Given two distinct points $A$ and $B$, the vector connecting them serves as a natural direction vector:
   $$
   v = \overrightarrow{AB} = B - A
   $$

2. **Normal Vector and General Form in $\mathbb{R}^2$:**
   In the plane $\mathbb{R}^2$, a line can be characterized by a normal vector $n = (A, B) \ne (0, 0)$ perpendicular to its direction vector $v = (v_x, v_y)$:
   $$
   n \cdot v = 0 \iff A v_x + B v_y = 0
   $$
   A convenient choice is $n = (-v_y, v_x)$ or $(v_y, -v_x)$.
   The general (implicit) equation is obtained by stating that for every point $X(x, y)$ on the line, the vector $\overrightarrow{AX}$ is perpendicular to $n$:
   $$
   n \cdot (X - A) = 0 \iff A(x - x_A) + B(y - y_A) = 0 \iff Ax + By + C = 0
   $$
   where $C = -(A x_A + B y_A)$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Construct the Direction Vector $v$

Subtract point $A$ from point $B$:
$$
v = \overrightarrow{AB} = B - A = \begin{pmatrix} 4 - 1 \\ -1 - 2 \end{pmatrix} = \begin{pmatrix} 3 \\ -3 \end{pmatrix}
$$

Since any non-zero scalar multiple of a direction vector specifies the same line, we may also use the simplified direction vector:
$$
v_0 = \frac{1}{3} v = \begin{pmatrix} 1 \\ -1 \end{pmatrix}
$$

---

### Step 2: Formulate the Parametric Equation

Using initial point $A(1, 2)$ and direction vector $v = (3, -3)$:
$$
\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 1 \\ 2 \end{pmatrix} + t \begin{pmatrix} 3 \\ -3 \end{pmatrix}, \quad t \in \mathbb{R}
$$

In scalar component form:
$$
\begin{cases}
x = 1 + 3t, \\
y = 2 - 3t,
\end{cases}
\quad t \in \mathbb{R}
$$

*(Using the simplified vector $v_0 = (1, -1)$ yields the equivalent parameterization: $x = 1 + s, y = 2 - s$ with $s = 3t$.)*

---

### Step 3: Determine a Normal Vector $n$

A normal vector $n = (n_x, n_y)$ must be orthogonal to $v = (3, -3)$:
$$
n \cdot v = n_x(3) + n_y(-3) = 0 \implies 3(n_x - n_y) = 0 \implies n_x = n_y
$$
Choosing $n_x = 1$ gives $n_y = 1$:
$$
n = \begin{pmatrix} 1 \\ 1 \end{pmatrix}
$$
*(Check: $n \cdot v = (1)(3) + (1)(-3) = 3 - 3 = 0 \checkmark$.)*

---

### Step 4: Derive the General (Implicit) Form

Using normal vector $n = (1, 1)$ and base point $A(1, 2)$:
$$
n \cdot (X - A) = 0
$$
$$
1(x - 1) + 1(y - 2) = 0
$$
$$
x - 1 + y - 2 = 0 \implies x + y - 3 = 0
$$

The general form of the line is:
$$
x + y - 3 = 0 \quad (\text{or } x + y = 3)
$$

---

### Step 5: Verification of Both Points

1. **Substitute point $A(1, 2)$ into the general equation:**
   $$
   x + y - 3 = 1 + 2 - 3 = 3 - 3 = 0 \quad (\checkmark)
   $$
2. **Substitute point $B(4, -1)$ into the general equation:**
   $$
   x + y - 3 = 4 + (-1) - 3 = 4 - 4 = 0 \quad (\checkmark)
   $$

Both points satisfy the equation.

---

## 4. Verification and Consistency Checks

1. **Slope-Intercept Form Check:**
   - From coordinates: slope $m = \frac{y_B - y_A}{x_B - x_A} = \frac{-1 - 2}{4 - 1} = \frac{-3}{3} = -1$.
   - Point-slope equation: $y - 2 = -1(x - 1) \implies y - 2 = -x + 1 \implies x + y - 3 = 0 \quad (\checkmark)$.

2. **Parametric Recovery of Point $B$:**
   In the parametric equations $\begin{cases} x = 1 + 3t \\ y = 2 - 3t \end{cases}$:
   - Setting $t = 0$ yields $(x, y) = (1, 2) = A$.
   - Setting $t = 1$ yields $(x, y) = (1 + 3(1), 2 - 3(1)) = (4, -1) = B \quad (\checkmark)$.
