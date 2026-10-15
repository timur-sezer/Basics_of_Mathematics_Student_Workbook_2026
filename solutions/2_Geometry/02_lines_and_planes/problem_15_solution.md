# Solution to Exercise 15: Complete Classification of a Line Relative to a Plane

## 1. Problem Statement

Let a line $L$ and a plane $\Pi$ in $\mathbb{R}^3$ be specified in vector form:
$$
L: X(t) = p + t v, \quad t \in \mathbb{R}
$$
$$
\Pi: n \cdot X = d
$$
where $p$ is a base point on $L$, $v \ne \mathbf{0}$ is the line's direction vector, $n \ne \mathbf{0}$ is the normal vector to $\Pi$, and $d \in \mathbb{R}$ is the plane's constant.

1. State the precise mathematical conditions (in terms of $n, v, p$, and $d$) that distinguish the three possible geometric relationships:
   - **Case I:** Exactly one intersection point ($L$ crosses $\Pi$ transversely).
   - **Case II:** Parallel with no common points ($L \parallel \Pi$ and $L \cap \Pi = \emptyset$).
   - **Case III:** The line is entirely contained within the plane ($L \subset \Pi$, infinitely many common points).
2. Illustrate each of the three cases with a clear, minimal numerical example in $\mathbb{R}^3$.

---

## 2. Theoretical Background and Concepts

1. **Algebraic Substitution:**
   Substituting the parametric representation of $L$ into the implicit equation of $\Pi$ yields:
   $$
   n \cdot (p + t v) = d \iff (n \cdot p) + t (n \cdot v) = d
   $$
   Rearranging into standard linear form in unknown $t$:
   $$
   t (n \cdot v) = d - n \cdot p
   $$

2. **Analysis of the Scalar Equation $a t = b$:**
   Let $a = n \cdot v$ and $b = d - n \cdot p$:
   - If $a \ne 0$: There is a **unique solution** $t^* = \frac{b}{a}$.
   - If $a = 0$ and $b \ne 0$: The equation becomes $0 \cdot t = b \ne 0$, which has **no solution** (contradiction).
   - If $a = 0$ and $b = 0$: The equation becomes $0 \cdot t = 0$, which is satisfied for **all $t \in \mathbb{R}$** (tautology).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Formal Mathematical Classification Criteria

| Case | Geometric Description | Necessary & Sufficient Condition | Solution Set $L \cap \Pi$ |
| :---: | :--- | :---: | :---: |
| **Case I** | **Unique Intersection Point** | $n \cdot v \ne 0$ | Single point $\{p + t^* v\}$ with $t^* = \frac{d - n \cdot p}{n \cdot v}$ |
| **Case II** | **Parallel and Disjoint** | $n \cdot v = 0 \quad \text{and} \quad n \cdot p \ne d$ | Empty set: $\emptyset$ |
| **Case III** | **Line Contained in Plane** | $n \cdot v = 0 \quad \text{and} \quad n \cdot p = d$ | Entire line: $L$ (infinitely many points) |

---

### Step 2: Numerical Illustration of Case I (Unique Intersection)

1. **Choice of Data:**
   - Base point: $p = (0, 0, 1)$
   - Direction vector: $v = (0, 0, 1)$
   - Plane equation: $\Pi: z = 0 \implies n = (0, 0, 1)$ and $d = 0$

2. **Evaluation of Conditions:**
   $$
   n \cdot v = (0)(0) + (0)(0) + (1)(1) = 1 \ne 0
   $$
   Since $n \cdot v \ne 0$, Case I applies.

3. **Solution:**
   $$
   n \cdot p = (0)(0) + (0)(0) + (1)(1) = 1
   $$
   $$
   t^* = \frac{d - n \cdot p}{n \cdot v} = \frac{0 - 1}{1} = -1
   $$
   Intersection point:
   $$
   X^* = p + t^* v = \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} + (-1) \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}
   $$
   The line (the $z$-axis) crosses the horizontal plane $z = 0$ perpendicularly at the origin $(0, 0, 0)$.

---

### Step 3: Numerical Illustration of Case II (Parallel and Disjoint)

1. **Choice of Data:**
   - Base point: $p = (0, 0, 1)$
   - Direction vector: $v = (1, 0, 0)$
   - Plane equation: $\Pi: z = 0 \implies n = (0, 0, 1)$ and $d = 0$

2. **Evaluation of Conditions:**
   - Dot product with direction:
     $$
     n \cdot v = (0)(1) + (0)(0) + (1)(0) = 0
     $$
   - Dot product with base point:
     $$
     n \cdot p = (0)(0) + (0)(0) + (1)(1) = 1 \ne d \quad (1 \ne 0)
     $$
   Since $n \cdot v = 0$ and $n \cdot p \ne d$, Case II applies.

3. **Geometric Meaning:**
   The line is the horizontal line at height $z = 1$ parallel to the $x$-axis. It is parallel to the plane $z = 0$ at a constant distance of $1$ unit and never intersects it ($L \cap \Pi = \emptyset$).

---

### Step 4: Numerical Illustration of Case III (Line Contained in Plane)

1. **Choice of Data:**
   - Base point: $p = (0, 0, 0)$
   - Direction vector: $v = (1, 0, 0)$
   - Plane equation: $\Pi: z = 0 \implies n = (0, 0, 1)$ and $d = 0$

2. **Evaluation of Conditions:**
   - Dot product with direction:
     $$
     n \cdot v = (0)(1) + (0)(0) + (1)(0) = 0
     $$
   - Dot product with base point:
     $$
     n \cdot p = (0)(0) + (0)(0) + (1)(0) = 0 = d \quad (0 = 0)
     $$
   Since $n \cdot v = 0$ and $n \cdot p = d$, Case III applies.

3. **Geometric Meaning:**
   The line is the $x$-axis itself ($y = 0, z = 0$). Because the base point lies in the plane and the direction is parallel to the plane, every point on the line satisfies $z = 0$. The line lies entirely within the plane ($L \subset \Pi$).

---

## 4. Verification and Consistency Checks

1. **Algebraic Consistency Summary:**
   The linear equation $t (n \cdot v) = d - n \cdot p$:
   - For Case I example: $t(1) = 0 - 1 \implies t = -1$ (Unique solution $\checkmark$)
   - For Case II example: $t(0) = 0 - 1 \implies 0 = -1$ (Inconsistent $\checkmark$)
   - For Case III example: $t(0) = 0 - 0 \implies 0 = 0$ (Identically true for all $t \in \mathbb{R} \checkmark$)

2. **Rank and Rouché–Capelli Alignment:**
   In matrix form, intersecting a line with a plane is equivalent to solving a $3 \times 3$ linear system (2 plane equations for the line + 1 plane equation for $\Pi$):
   - Case I corresponds to $\operatorname{rank}(A) = \operatorname{rank}[A \mid b] = 3$ (unique solution).
   - Case II corresponds to $\operatorname{rank}(A) = 2 < \operatorname{rank}[A \mid b] = 3$ (inconsistent).
   - Case III corresponds to $\operatorname{rank}(A) = \operatorname{rank}[A \mid b] = 2 < 3$ (1 free variable, line of solutions).
   The vector criteria align with the fundamental theorem of linear systems.
