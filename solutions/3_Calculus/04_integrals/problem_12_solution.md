# Solution to Problem 12: Symmetry, Sign, and Absolute Value

## 1. Problem Statement

Compare the following two definite integrals on the symmetric interval $[-2, 2]$:
$$
I_1 = \int_{-2}^{2} x \, dx \qquad \text{and} \qquad I_2 = \int_{-2}^{2} |x| \, dx
$$

1. Before performing any calculation, predict the value of each integral relying exclusively on function symmetry (odd vs. even parity) and geometric sketches.
2. Carry out the analytical evaluation of both integrals using the Fundamental Theorem of Calculus.
3. Explain why the presence of the absolute value operator fundamentally changes the nature of the integral from zero net cancellation to additive reinforcement.

---

## 2. Theoretical Background and Concepts

1. **Symmetric Domains and Parity Theorems:**
   Let $f(x)$ be integrable on a symmetric interval $[-a, a]$:
   - **Odd Function Theorem:**
     If $f(-x) = -f(x)$ for all $x \in [-a, a]$, then:
     $$
     \int_{-a}^a f(x) \, dx = 0
     $$
     Every Riemann sum element $f(x) \Delta x$ at $+x$ is neutralized by an equal and opposite element $f(-x) \Delta x = -f(x) \Delta x$ at $-x$.
   - **Even Function Theorem:**
     If $f(-x) = f(x)$ for all $x \in [-a, a]$, then:
     $$
     \int_{-a}^a f(x) \, dx = 2 \int_0^a f(x) \, dx
     $$
     The area on $[-a, 0]$ is an exact reflection of the area on $[0, a]$, doubling the total accumulation.

2. **The Absolute Value as a Parity Rectifier:**
   The identity function $f(x) = x$ is odd. Applying the absolute value produces $g(x) = |x|$, which is even:
   $$
   g(-x) = |-x| = |x| = g(x)
   $$
   The absolute value rectifies negative outputs by reflecting them into the positive half-plane ($y \ge 0$), converting destructive cancellation into constructive summation.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Geometric and Symmetry Predictions (Prior Analysis)

#### 1. Prediction for $I_1 = \int_{-2}^2 x \, dx$:
- **Parity:** $f(-x) = -x = -f(x) \implies f(x) = x$ is an **odd function**.
- **Geometry:**
  - On $[-2, 0]$, the curve lies below the $x$-axis, forming a right triangle with base $2$ and height $2$. Its signed area is:
    $$
    A_1 = -\frac{1}{2}(2)(2) = -2
    $$
  - On $[0, 2]$, the curve lies above the $x$-axis, forming an identical right triangle with base $2$ and height $2$. Its signed area is:
    $$
    A_2 = +\frac{1}{2}(2)(2) = +2
    $$
- **Prediction:** By point symmetry across the origin $(0, 0)$, the negative area below the axis cancels the positive area above the axis exactly:
  $$
  I_1 = -2 + 2 = 0
  $$

#### 2. Prediction for $I_2 = \int_{-2}^2 |x| \, dx$:
- **Parity:** $g(-x) = |-x| = |x| = g(x) \implies g(x) = |x|$ is an **even function**.
- **Geometry:**
  - The graph of $y = |x|$ is a symmetric "V-shape" with vertex at $(0, 0)$.
  - The negative branch on $[-2, 0]$ is reflected above the $x$-axis. Both the left and right halves form identical positive right triangles, each with base $2$ and height $2$:
    $$
    \text{Area}_{\text{left}} = \frac{1}{2}(2)(2) = 2, \qquad \text{Area}_{\text{right}} = \frac{1}{2}(2)(2) = 2
    $$
- **Prediction:** The two positive areas reinforce each other constructively:
  $$
  I_2 = 2 + 2 = 4
  $$

#### 3. Required Geometric Sketches Prior to Analytical Calculation:

```text
Plot 1: Graph of f(x) = x on [-2, 2] (Odd Function: Net Signed Area = 0)
                              y
                              ^
         2                    |           * (2, 2)
                              |         / |
         1                    |       /   |  Area = +2
                              |     /     |
   ---------------+-----------*-----------+------------------> x
                 -2         |(0, 0)       2
                           /  |
        -1             /      |  Area = -2
                     /        |
        -2        *           |
               (-2, -2)       v
```

```text
Plot 2: Graph of g(x) = |x| on [-2, 2] (Even Function: Total Area = 4)
                              y
                              ^
         2        * (-2, 2)   |           * (2, 2)
                  | \         |         / |
         1        |   \       |       /   |  Area = +2 each
                  |     \     |     /     |
   ---------------+-----------*-----------+------------------> x
                 -2         |(0, 0)       2
                            | Vertex at Origin
                            v
```
*Labels:*
- **Plot 1 ($y = x$):** The line passes directly through the origin $(0, 0)$ at the intersection of the coordinate axes; triangle on $[-2, 0]$ has signed area $-2$; triangle on $[0, 2]$ has signed area $+2$; net integral cancels to $0$.
- **Plot 2 ($y = |x|$):** The single "V" consists of straight segments from $(-2, 2)$ to $(0, 0)$ and from $(0, 0)$ to $(2, 2)$, meeting only at the origin $(0, 0)$ at the intersection of the coordinate axes; point $(-2, 2)$ lies strictly to the left of the $y$-axis and point $(2, 2)$ lies strictly to the right of the $y$-axis, displaying perfect reflectional symmetry across the $y$-axis; both triangles have positive area $+2$, adding to a total of $4$.

---

### Step 2: Analytical Calculation of $I_1 = \int_{-2}^2 x \, dx$

1. Standard antiderivative of $x$:
   $$
   F(x) = \frac{x^2}{2}
   $$
2. Apply the Newton-Leibniz formula on $[-2, 2]$:
   $$
   I_1 = \left[\frac{x^2}{2}\right]_{-2}^2 = \frac{2^2}{2} - \frac{(-2)^2}{2} = \frac{4}{2} - \frac{4}{2} = 2 - 2 = 0
   $$
The analytical calculation confirms $I_1 = 0$.

---

### Step 3: Analytical Calculation of $I_2 = \int_{-2}^2 |x| \, dx$

1. Because $|x|$ is defined piecewise:
   $$
   |x| = \begin{cases} -x, & x < 0 \\ x, & x \ge 0 \end{cases}
   $$
   we split the integral at the transition point $x = 0$:
   $$
   I_2 = \int_{-2}^0 (-x) \, dx + \int_0^2 x \, dx
   $$

2. Evaluate each integral individually:
   - First integral (left branch):
     $$
     \int_{-2}^0 (-x) \, dx = \left[-\frac{x^2}{2}\right]_{-2}^0 = 0 - \left(-\frac{(-2)^2}{2}\right) = 0 - (-2) = +2
     $$
   - Second integral (right branch):
     $$
     \int_0^2 x \, dx = \left[\frac{x^2}{2}\right]_0^2 = \frac{2^2}{2} - 0 = +2
     $$

3. Sum the two integrals:
   $$
   I_2 = 2 + 2 = 4
   $$
Alternatively, applying the Even Function Theorem:
$$
I_2 = 2 \int_0^2 x \, dx = 2 \left[\frac{x^2}{2}\right]_0^2 = 2(2 - 0) = 4
$$
The analytical calculation confirms $I_2 = 4$.

---

### Step 4: Geometric and Physical Explanation of the Difference

As visualized in the sketches in Step 1:

1. **Mathematical Explanation:**
   - In $I_1$, the values $f(x)$ carry signs. Negative function values on $[-2, 0]$ multiply positive step sizes $dx$ to yield negative infinitesimal areas $dA = x \, dx < 0$. These cancel with the equal positive infinitesimal areas on $[0, 2]$, resulting in zero net accumulation.
   - In $I_2$, the absolute value operator forces every height $|x|$ to be non-negative. All elements $dA = |x| \, dx \ge 0$ are positive, transforming cancellation into total geometric area summation.

2. **Physical Kinematics Analogy:**
   If $v(t) = t$ is the velocity of a particle:
   - $I_1 = \int_{-2}^2 v(t) \, dt = 0\text{ m}$: The particle reverses direction and returns to its exact starting point (**displacement = 0**).
   - $I_2 = \int_{-2}^2 |v(t)| \, dt = 4\text{ m}$: The particle traveled 2 meters to the left and 2 meters to the right (**odometer distance = 4 m**).

---

## 4. Verification and Consistency Checks

### Summary Comparison Table

| Property | Integral $I_1 = \int_{-2}^2 x \, dx$ | Integral $I_2 = \int_{-2}^2 \|x\| \, dx$ |
|:---|:---:|:---:|
| **Integrand** | $f(x) = x$ | $g(x) = \|x\|$ |
| **Parity** | Strictly Odd ($f(-x) = -f(x)$) | Strictly Even ($g(-x) = g(x)$) |
| **Symmetry Center / Axis** | Point-symmetric about $(0, 0)$ | Axially symmetric about $y$-axis |
| **Left Half Value $[-2, 0]$** | $-2$ | $+2$ |
| **Right Half Value $[0, 2]$** | $+2$ | $+2$ |
| **Interaction** | Destructive cancellation ($-2 + 2$) | Constructive addition ($+2 + 2$) |
| **Final Integral Value** | **$0$** | **$4$** |

Both symmetry arguments and direct piecewise integration converge on the identical results $I_1 = 0$ and $I_2 = 4$.
