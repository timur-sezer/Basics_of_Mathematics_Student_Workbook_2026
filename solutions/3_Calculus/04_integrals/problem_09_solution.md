# Solution to Problem 9: Definite Integral and Geometric Area

## 1. Problem Statement

1. Compute the exact value of the definite integral:
   $$
   I = \int_{-1}^{2} x \, dx
   $$
   using the Fundamental Theorem of Calculus.
2. Partition the region into parts below and above the $x$-axis, computing the geometric area of each part separately using elementary Euclidean geometry.
3. Contrast the value of the definite integral with the total geometric area.
4. Explain the conceptual difference between **signed accumulation (the definite integral)** and **geometric area**.

---

## 2. Theoretical Background and Concepts

1. **The Fundamental Theorem of Calculus (Newton-Leibniz Formula):**
   If $f(x)$ is continuous on $[a, b]$ and $F(x)$ is any antiderivative of $f(x)$, then:
   $$
   \int_a^b f(x) \, dx = F(b) - F(a) = \Big[F(x)\Big]_a^b
   $$

2. **The Definite Integral as Net Signed Area:**
   Riemann sums approximate an integral by summing rectangular elements $f(x_k^*) \Delta x$:
   - Where $f(x) > 0$, the function value is positive, contributing **positive area** ($+A$).
   - Where $f(x) < 0$, the function value is negative, contributing **negative area** ($-A$).
   Consequently, the definite integral measures the **net signed balance**:
   $$
   \int_a^b f(x) \, dx = A_{\text{above}} - A_{\text{below}}
   $$

3. **Total Geometric Area:**
   Geometric area is by definition a strictly non-negative physical quantity measuring the two-dimensional surface enclosed between the curve and the $x$-axis. It is computed by integrating the absolute value of the function:
   $$
   A_{\text{total}} = \int_a^b |f(x)| \, dx = A_{\text{above}} + A_{\text{below}}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Analytical Evaluation of the Definite Integral

1. The integrand is $f(x) = x$.
2. The standard antiderivative is:
   $$
   F(x) = \frac{x^2}{2}
   $$
3. Apply the Newton-Leibniz formula from $a = -1$ to $b = 2$:
   $$
   \int_{-1}^2 x \, dx = \left[\frac{x^2}{2}\right]_{-1}^2 = \frac{2^2}{2} - \frac{(-1)^2}{2} = \frac{4}{2} - \frac{1}{2} = 2 - 0.5 = 1.5 = \frac{3}{2}
   $$

The value of the definite integral is:
$$
\mathbf{I = \frac{3}{2} = 1.5}
$$

---

### Step 2: Separate Geometric Area Calculations

The graph of $y = x$ crosses the $x$-axis at $x = 0$. We split the domain $[-1, 2]$ into two sub-intervals: $[-1, 0]$ and $[0, 2]$.

#### Region 1: Below the $x$-axis on $[-1, 0]$
- On $[-1, 0]$, $y = x \le 0$. The region lies entirely below the $x$-axis.
- The boundary lines form a right triangle with vertices:
  $$
  (-1, 0), \quad (0, 0), \quad (-1, -1)
  $$
- Dimensions of the triangle:
  - Base length: $b_1 = |0 - (-1)| = 1$
  - Height length: $h_1 = |0 - (-1)| = 1$
- Geometric Area $A_1$:
  $$
  A_1 = \frac{1}{2} \cdot b_1 \cdot h_1 = \frac{1}{2}(1)(1) = \frac{1}{2} = 0.5
  $$
- Definite integral on this sub-interval:
  $$
  \int_{-1}^0 x \, dx = \left[\frac{x^2}{2}\right]_{-1}^0 = 0 - \frac{(-1)^2}{2} = -\frac{1}{2} = -0.5 = -A_1
  $$
  The integral attaches a **negative sign** to the area below the axis.

#### Region 2: Above the $x$-axis on $[0, 2]$
- On $[0, 2]$, $y = x \ge 0$. The region lies entirely above the $x$-axis.
- The boundary lines form a right triangle with vertices:
  $$
  (0, 0), \quad (2, 0), \quad (2, 2)
  $$
- Dimensions of the triangle:
  - Base length: $b_2 = 2 - 0 = 2$
  - Height length: $h_2 = 2 - 0 = 2$
- Geometric Area $A_2$:
  $$
  A_2 = \frac{1}{2} \cdot b_2 \cdot h_2 = \frac{1}{2}(2)(2) = 2.0
  $$
- Definite integral on this sub-interval:
  $$
  \int_0^2 x \, dx = \left[\frac{x^2}{2}\right]_0^2 = \frac{2^2}{2} - 0 = 2.0 = +A_2
  $$
  The integral attaches a **positive sign** to the area above the axis.

---

### Step 3: Comparison Between Integral and Total Area

1. **The Definite Integral (Net Signed Area):**
   $$
   \int_{-1}^2 x \, dx = \int_{-1}^0 x \, dx + \int_0^2 x \, dx = -A_1 + A_2 = -0.5 + 2.0 = 1.5
   $$

2. **Total Geometric Area Enclosed ($A_{\text{total}}$):**
   $$
   A_{\text{total}} = A_1 + A_2 = 0.5 + 2.0 = 2.5
   $$
   In integral form:
   $$
   A_{\text{total}} = \int_{-1}^2 |x| \, dx = \int_{-1}^0 (-x) \, dx + \int_0^2 x \, dx = 0.5 + 2.0 = 2.5
   $$

Notice that:
$$
\int_{-1}^2 x \, dx = 1.5 \neq 2.5 = \int_{-1}^2 |x| \, dx
$$

---

### Step 4: Explanation of the Difference

```text
       y
       ^
   2   |               * (2, 2)
       |             * |
   1   |           *   |   Area A2 = +2.0 (Above axis)
-------+---------*-----+---------> x
  -1   |        0      2
   | * |
  -1 * | Area A1 = 0.5 (Below axis, counts as -0.5)
```

1. **Why They Differ:**
   - **The Definite Integral is a Net Accumulation:** It sums oriented quantities. If $f(t)$ represents net cash flow (deposits minus withdrawals) or velocity (forward minus backward motion), the integral gives the **net change** in balance or net displacement. Depositing \$2 and withdrawing \$0.50 leaves a net change of +\$1.50.
   - **Geometric Area is a Gross Magnitude:** Area measures total physical surface area or total distance traveled, regardless of direction. Covering both triangular plots of land with turf requires $0.5 + 2.0 = 2.5$ square units of material.

2. **Condition for Equivalence:**
   The definite integral $\int_a^b f(x) \, dx$ equals the total geometric area if and only if $f(x) \ge 0$ for all $x \in [a, b]$. Whenever the function changes sign, the definite integral computes the cancellation $A_{\text{above}} - A_{\text{below}}$.

---

## 4. Verification and Consistency Checks

1. **Summary Table:**

| Metric | Mathematical Expression | Formula | Value |
|:---|:---|:---:|:---:|
| **Area Below Axis** | $A_1 = \text{Area}(\triangle_1)$ | $\frac{1}{2}(1)(1)$ | $0.5$ |
| **Area Above Axis** | $A_2 = \text{Area}(\triangle_2)$ | $\frac{1}{2}(2)(2)$ | $2.0$ |
| **Definite Integral** | $\int_{-1}^2 x \, dx$ | $A_2 - A_1$ | **$1.5$** |
| **Total Geometric Area** | $\int_{-1}^2 \|x\| \, dx$ | $A_2 + A_1$ | **$2.5$** |

2. **Physical Kinematics Analogy Check:**
   Suppose an object moves along a line with velocity $v(t) = t$ meters per second from $t = -1$ to $t = 2$:
   - Net displacement $\Delta s = \int_{-1}^2 v(t) \, dt = 1.5\text{ m}$ (the object ends up $1.5\text{ m}$ to the right of its initial position).
   - Total distance traveled $d = \int_{-1}^2 |v(t)| \, dt = 2.5\text{ m}$ (the object moved $0.5\text{ m}$ to the left, then reversed and moved $2.0\text{ m}$ to the right).
   The kinematic analogy completely confirms the mathematical calculation.
