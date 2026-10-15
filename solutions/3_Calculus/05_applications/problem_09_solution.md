# Solution to Problem 9: Minimizing the Material Used for a Can

## 1. Problem Statement

A closed right circular cylinder (can) with top and bottom lids has a prescribed fixed volume $V > 0$.

1. State the volume constraint equation relating the base radius $r$ and the height $h$.
2. Eliminate the variable $h$ using the volume constraint.
3. Formulate the total surface area $S$ (material used) as a single-variable function of the radius $r$.
4. Determine the critical point minimizing $S(r)$ and derive the exact mathematical relationship between the height $h$ and the radius $r$ (and diameter $d$).
5. Provide a geometric interpretation of the resulting optimal cylinder proportions and verify that the solution represents an absolute minimum.

---

## 2. Theoretical Background and Concepts

1. **Constrained Optimization via Single-Variable Reduction:**
   When an objective function $f(x, y)$ depends on two geometric variables connected by an equality constraint $g(x, y) = C$, the standard analytical technique is to:
   - Solve the constraint equation explicitly for one variable: $y = \varphi(x)$.
   - Substitute $y$ into the objective function to obtain an unconstrained single-variable function: $F(x) = f(x, \varphi(x))$.
   - Optimize $F(x)$ using standard single-variable calculus ($F'(x) = 0$).

2. **Geometric Formulas for a Closed Cylinder:**
   - Base area (two circular discs): $A_{\text{bases}} = 2 \pi r^2$.
   - Lateral surface area (unrolled rectangle of height $h$ and circumference $2\pi r$): $A_{\text{lat}} = 2\pi r h$.
   - Total surface area:
     $$
     S = 2\pi r^2 + 2\pi r h
     $$
   - Enclosed volume:
     $$
     V = \pi r^2 h
     $$

3. **Convexity on Open Unbounded Domains:**
   If a differentiable function $F(r)$ is defined on $(0, \infty)$ and satisfies $F''(r) > 0$ everywhere, the function is strictly convex (concave upward). Any stationary point where $F'(r^*) = 0$ is guaranteed to be the unique **absolute global minimum**.

---

## 3. Detailed Step-by-Step Solution

### Step 1: The Volume Constraint Equation

Let the cylinder have:
- Base radius $r > 0$
- Height $h > 0$

The volume of a right circular cylinder is the base area times the height:
$$
V = \pi r^2 h
$$
where $V$ is a fixed positive constant ($V = \text{const}$).

---

### Step 2: Eliminate One Variable

Solve the volume constraint for $h$ in terms of $r$ and $V$:
$$
h = \frac{V}{\pi r^2}
$$

---

### Step 3: Express Total Surface Area $S$ as a Function of $r$

The total material required to construct the closed cylinder is the sum of the two circular lids and the lateral wall:
$$
S(r, h) = 2\pi r^2 + 2\pi r h
$$

Substitute $h = \frac{V}{\pi r^2}$ into the surface area equation:
$$
S(r) = 2\pi r^2 + 2\pi r \left(\frac{V}{\pi r^2}\right) = 2\pi r^2 + \frac{2V}{r}
$$

The single-variable objective function is:
$$
S(r) = 2\pi r^2 + 2V r^{-1}, \qquad r \in (0, \infty)
$$

---

### Step 4: Find the Optimal Relation Between $h$ and $r$

1. **Compute the First Derivative $S'(r)$:**
   Differentiate with respect to $r$ (treating $V$ as a constant):
   $$
   S'(r) = \frac{d}{dr}\left[2\pi r^2 + 2V r^{-1}\right] = 4\pi r - 2V r^{-2} = 4\pi r - \frac{2V}{r^2}
   $$

2. **Find the Critical Point:**
   Set $S'(r) = 0$:
   $$
   4\pi r - \frac{2V}{r^2} = 0 \iff 4\pi r = \frac{2V}{r^2} \iff 4\pi r^3 = 2V \iff 2\pi r^3 = V
   $$

3. **Establish the Relation Between $h$ and $r$:**
   Substitute the original constraint $V = \pi r^2 h$ into the optimality condition $2\pi r^3 = V$:
   $$
   2\pi r^3 = \pi r^2 h
   $$
   Since $r > 0$, divide both sides by $\pi r^2$:
   $$
   2r = h \iff \mathbf{h = 2r}
   $$

In terms of the cylinder's diameter $d = 2r$:
$$
\mathbf{h = d}
$$

The material used is minimized when the **height of the cylinder is exactly equal to its diameter** (twice its radius).

4. **Explicit Radius and Height in terms of $V$:**
   From $2\pi r^3 = V$:
   $$
   r^* = \sqrt[3]{\frac{V}{2\pi}}, \qquad h^* = 2\sqrt[3]{\frac{V}{2\pi}} = \sqrt[3]{\frac{4V}{\pi}}
   $$

---

### Step 5: Verification of the Minimum

Compute the second derivative:
$$
S''(r) = \frac{d}{dr}\left[4\pi r - 2V r^{-2}\right] = 4\pi - 2V(-2r^{-3}) = 4\pi + \frac{4V}{r^3}
$$
Because $r > 0$ and $V > 0$:
$$
S''(r) = 4\pi + \frac{4V}{r^3} > 0 \quad \forall r \in (0, \infty)
$$
The second derivative is strictly positive on the entire domain $(0, \infty)$.
Therefore, the function $S(r)$ is **strictly convex**, and the critical point $h = 2r$ represents the unique **absolute global minimum**.

As $r \to 0^+$, $S(r) \approx \frac{2V}{r} \to +\infty$ (an extremely tall, razor-thin needle can has enormous lateral area).
As $r \to +\infty$, $S(r) \approx 2\pi r^2 \to +\infty$ (an ultra-flat, broad pancake can has enormous lid area).
The minimum at $h = 2r$ represents the optimal geometric balance.

---

### Step 6: Geometric Interpretation

```text
         +---------------+
        /               /|
       /               / |
      +---------------+  |
      |   * * * * *   |  |
      | *           * |  |  Height h = 2r
      |*      r      *|  |  Diameter d = 2r
      | *           * |  |
      |   * * * * *   |  |
      +---------------+  +
      |               | /
      |               |/
      +---------------+
```

1. **Square Axial Cross-Section:**
   A vertical cross-section passing through the central axis of the optimal cylinder is a rectangle of width $2r$ and height $h = 2r$.
   Thus, the cross-section is an **exact square** of side length $2r$.

2. **Inscribed Sphere Analogy:**
   A cylinder with $h = 2r$ can be circumscribed around a sphere of radius $r$. The sphere touches the top lid, bottom lid, and the entire circumference of the lateral wall.
   This mirrors Archimedes' celebrated theorem on the sphere and cylinder, where the sphere-cylinder geometry achieves maximal compactness.

---

## 4. Verification and Consistency Checks

1. **Ratio of Base Area to Lateral Area at the Optimum:**
   - Area of the two bases:
     $$
     S_{\text{bases}} = 2\pi r^2
     $$
   - Lateral surface area when $h = 2r$:
     $$
     S_{\text{lat}} = 2\pi r h = 2\pi r(2r) = 4\pi r^2
     $$
   - Total surface area:
     $$
     S_{\min} = 2\pi r^2 + 4\pi r^2 = 6\pi r^2
     $$
   Notice that:
   $$
   \frac{S_{\text{lat}}}{S_{\text{bases}}} = \frac{4\pi r^2}{2\pi r^2} = 2
   $$
   At the optimum, the lateral area is exactly **twice** the area of the two lids combined.

2. **Numerical Sensitivity Check with $V = 1000\text{ cm}^3$ (1 Liter):**
   - Optimal radius:
     $$
     r^* = \sqrt[3]{\frac{1000}{2\pi}} = \sqrt[3]{159.1549} \approx 5.4193\text{ cm}
     $$
   - Optimal height:
     $$
     h^* = 2r^* \approx 10.8385\text{ cm}
     $$
   - Minimum surface area:
     $$
     S(r^*) = 6\pi(5.4193)^2 \approx 6\pi(29.3685) \approx 553.58\text{ cm}^2
     $$
   - Comparison with non-optimal proportions for $V = 1000\text{ cm}^3$:
     - Tall, skinny can ($r = 3\text{ cm} \implies h = 35.37\text{ cm}$):
       $S = 2\pi(9) + 2\pi(3)(35.37) \approx 56.55 + 666.67 = 723.22\text{ cm}^2$ ($+31\%$ more material).
     - Short, flat can ($r = 8\text{ cm} \implies h = 4.97\text{ cm}$):
       $S = 2\pi(64) + 2\pi(8)(4.97) \approx 402.12 + 250.00 = 652.12\text{ cm}^2$ ($+18\%$ more material).
   The optimal can with $h = 2r$ saves the most material.
