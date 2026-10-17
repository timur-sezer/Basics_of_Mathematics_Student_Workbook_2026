# Solution to Problem 6: Average Value of a Function

## 1. Problem Statement

Given the quadratic function:
$$
f(x) = x^2 \qquad \text{on the interval } [0, 3]
$$

1. Compute the exact average (mean) value $f_{\text{avg}}$ of the function on $[0, 3]$.
2. Apply the Mean Value Theorem for Integrals to find a point $c \in [0, 3]$ such that $f(c) = f_{\text{avg}}$.
3. Provide a clear geometric interpretation of the average value and the point $c$, explaining how the area under the curve relates to the area of an equivalent rectangle.

---

## 2. Theoretical Background and Concepts

1. **Definition of the Average Value of a Function:**
   For an integrable function $f(x)$ on a closed interval $[a, b]$, the **average (mean) value** is defined by:
   $$
   f_{\text{avg}} = \frac{1}{b - a} \int_a^b f(x) \, dx
   $$
   This continuous definition generalizes the discrete arithmetic mean:
   $$
   \bar{y} = \frac{1}{n}\sum_{k=1}^n y_k \longrightarrow \frac{1}{b - a} \int_a^b f(x) \, dx
   $$

2. **The Mean Value Theorem for Definite Integrals:**
   If $f(x)$ is continuous on the closed bounded interval $[a, b]$, then there exists at least one point $c \in [a, b]$ such that:
   $$
   f(c) = f_{\text{avg}} = \frac{1}{b - a} \int_a^b f(x) \, dx
   $$
   Equivalently:
   $$
   \int_a^b f(x) \, dx = f(c) \cdot (b - a)
   $$

3. **Geometric Area Leveling Interpretation:**
   The quantity $f_{\text{avg}} \cdot (b - a)$ represents the area of a rectangle of width $(b - a)$ and uniform height $f_{\text{avg}}$.
   The theorem states that the curved area under $y = f(x)$ can be perfectly reshaped into a flat rectangle of the same width and height $f(c)$. The "valley" area where $f(x) < f_{\text{avg}}$ is exactly equal in size to the "mountain" area where $f(x) > f_{\text{avg}}$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Definite Integral

Evaluate the definite integral of $f(x) = x^2$ on $[0, 3]$:
$$
\int_0^3 x^2 \, dx = \left[\frac{x^3}{3}\right]_0^3 = \frac{3^3}{3} - \frac{0^3}{3} = \frac{27}{3} - 0 = 9
$$

The total area under the parabola is:
$$
\text{Total Area} = 9
$$

---

### Step 2: Calculate the Average Value $f_{\text{avg}}$

The interval length is:
$$
b - a = 3 - 0 = 3
$$

Apply the average value formula:
$$
f_{\text{avg}} = \frac{1}{b - a} \int_a^b f(x) \, dx = \frac{1}{3} \times 9 = 3
$$

The average value of $f(x) = x^2$ on $[0, 3]$ is:
$$
\mathbf{f_{\text{avg}} = 3}
$$

---

### Step 3: Find the Point $c \in [0, 3]$ Where $f(c) = f_{\text{avg}}$

We seek $c \in [0, 3]$ such that:
$$
f(c) = 3
$$
Since $f(c) = c^2$:
$$
c^2 = 3 \iff c = \pm\sqrt{3}
$$

We filter by the interval $[0, 3]$:
- $c_1 = -\sqrt{3} \notin [0, 3]$ (rejected).
- $c_2 = +\sqrt{3} \approx 1.732051 \in [0, 3]$ (accepted).

Thus, the unique point is:
$$
\mathbf{c = \sqrt{3} \approx 1.732}
$$

---

### Step 4: Geometric Interpretation

```text
       y
       ^
   9   |                       * (3, 9)
   8   |                      /|
   7   |                     / |
   6   |                    /  |
   5   |                   /   |
   4   |                  /    |
   3 --+ - - - - - - - - *-----+  y = f_avg = 3 [Mean Line]
   2   |                /:     |  (c, 3) = (√3, 3)
   1   |              /  :     |
       |             /   :     |
   ----+*-----------+----+-----+---------> x
       0|           1    :     3
     (0,0)               :
                      c = √3 ≈ 1.732
```
*Labels:* Parabola $y = x^2$ starts at the origin $(0, 0)$; horizontal line $y = f_{\text{avg}} = 3$ represents the mean value height; vertical dashed line $x = c = \sqrt{3} \approx 1.732$ rises from the $x$-axis to intersect the parabola exactly at $(c, 3)$ on the mean line; equivalent rectangle on $[0, 3]$ has base $3$ and height $3$ (Area $= 9$).

1. **The Equivalent Rectangle:**
   Consider a rectangle with base along the $x$-axis from $x = 0$ to $x = 3$ (base length $= 3$) and height equal to $f_{\text{avg}} = 3$.
   Its area is:
   $$
   \text{Area}(\text{Rectangle}) = \text{base} \times \text{height} = 3 \times 3 = 9
   $$
   This area is **identically equal** to the area under the curved parabola:
   $$
   \int_0^3 x^2 \, dx = 9
   $$

2. **The Leveling Principle:**
   - On the sub-interval $[0, \sqrt{3}]$, the curve lies below the mean line ($x^2 < 3$). The "deficit area" between the horizontal line $y = 3$ and the parabola is:
     $$
     \text{Deficit} = \int_0^{\sqrt{3}} (3 - x^2) \, dx = \left[3x - \frac{x^3}{3}\right]_0^{\sqrt{3}} = 3\sqrt{3} - \frac{3\sqrt{3}}{3} = 2\sqrt{3} \approx 3.464
     $$
   - On the sub-interval $[\sqrt{3}, 3]$, the curve rises above the mean line ($x^2 > 3$). The "excess area" between the parabola and the horizontal line $y = 3$ is:
     $$
     \text{Excess} = \int_{\sqrt{3}}^3 (x^2 - 3) \, dx = \left[\frac{x^3}{3} - 3x\right]_{\sqrt{3}}^3 = (9 - 9) - \left(\frac{3\sqrt{3}}{3} - 3\sqrt{3}\right) = 0 - (-2\sqrt{3}) = 2\sqrt{3} \approx 3.464
     $$
   - Notice that:
     $$
     \text{Deficit} = \text{Excess} = 2\sqrt{3}
     $$
   The excess volume above the level line $y = 3$ fills the deficit below it. The point $c = \sqrt{3}$ is the exact balance point where the curve intersects the average height.

---

## 4. Verification and Consistency Checks

1. **Comparison with Endpoint Values:**
   - Minimum value: $f(0) = 0$.
   - Maximum value: $f(3) = 9$.
   - Arithmetic mean of the two endpoints:
     $$
     \frac{f(0) + f(3)}{2} = \frac{0 + 9}{2} = 4.5
     $$
   Notice that the true average value $f_{\text{avg}} = 3$ is **strictly less** than the arithmetic mean of the endpoints ($3 < 4.5$).
   This occurs because $f(x) = x^2$ is **strictly convex (concave upward)**: it lingers near small values for most of the interval ($x^2 \le 1$ on $[0, 1]$) and only surges upward near the right endpoint. The integral average faithfully captures this non-linear distribution, unlike a naive endpoint average.

2. **Point Location Check:**
   $$
   0 < \sqrt{3} \approx 1.732 < 3
   $$
   $c$ lies strictly in the interior of the interval, satisfying the Mean Value Theorem for Integrals.
