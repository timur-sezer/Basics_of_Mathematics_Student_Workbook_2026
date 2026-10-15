# Solution to Problem 4: Area Between Curves

## 1. Problem Statement

Find the exact area of the finite planar region bounded between the graphs of:
$$
y = x \qquad \text{and} \qquad y = x^2
$$

1. Determine all points of intersection between the line and the parabola.
2. Rigorously establish and justify which function lies strictly above the other across the interval bounded by the intersection points.
3. Formulate the definite integral for the enclosed area using the upper-minus-lower principle:
   $$
   A = \int_a^b \Big(y_{\text{upper}}(x) - y_{\text{lower}}(x)\Big) \, dx
   $$
4. Compute the exact value of the area.
5. Provide a geometric verification connecting the result with Archimedes' quadrature of the parabola.

---

## 2. Theoretical Background and Concepts

1. **Area Between Two Continuous Curves:**
   Let $f(x)$ and $g(x)$ be continuous functions on $[a, b]$ such that $f(x) \ge g(x)$ for all $x \in [a, b]$.
   The physical area of the region bounded above by $y = f(x)$, below by $y = g(x)$, and on the sides by $x = a$ and $x = b$ is:
   $$
   A = \int_a^b [f(x) - g(x)] \, dx
   $$

2. **Importance of Function Ordering:**
   Because physical area is strictly non-negative ($A > 0$), subtracting in the reverse order ($g(x) - f(x)$) produces a negative area. Establishing which curve is $y_{\text{upper}}$ and which is $y_{\text{lower}}$ through inequality analysis or test points is mandatory prior to integration.

3. **Archimedes' Quadrature of the Parabola:**
   Archimedes proved in 250 BC that the area of a parabolic segment enclosed by a chord is exactly:
   $$
   A = \frac{4}{3} \times \text{Area}(\triangle_{\text{inscribed}})
   $$
   where the inscribed triangle shares the chord as its base and has its third vertex at the point on the parabola where the tangent is parallel to the chord.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Find the Points of Intersection

To locate the boundaries of the enclosed region, set the two functions equal:
$$
x = x^2
$$
Rearrange into standard polynomial form:
$$
x^2 - x = 0 \iff x(x - 1) = 0
$$

The real solutions are:
$$
x_1 = 0, \qquad x_2 = 1
$$

Find the corresponding $y$-coordinates:
- For $x_1 = 0$: $y_1 = 0^2 = 0 \implies \mathbf{P_1(0, 0)}$
- For $x_2 = 1$: $y_2 = 1^2 = 1 \implies \mathbf{P_2(1, 1)}$

The integration limits are the $x$-coordinates of these intersection points:
$$
a = 0, \qquad b = 1
$$

---

### Step 2: Determine Which Curve Is Greater on $(0, 1)$

We must determine the relative order of $y_1 = x$ and $y_2 = x^2$ for $x \in (0, 1)$:

1. **Algebraic Justification:**
   For any real number $x \in (0, 1)$:
   $$
   0 < x < 1
   $$
   Multiply the inequality $x < 1$ by the strictly positive quantity $x > 0$:
   $$
   x \cdot x < 1 \cdot x \implies x^2 < x
   $$
   Equivalently:
   $$
   x - x^2 = x(1 - x) > 0 \quad \text{since } x > 0 \text{ and } 1 - x > 0
   $$

2. **Test Point Verification:**
   Choose midpoint $x = \frac{1}{2} \in (0, 1)$:
   - Line: $y_{\text{line}}\left(\frac{1}{2}\right) = \frac{1}{2} = 0.5$
   - Parabola: $y_{\text{parabola}}\left(\frac{1}{2}\right) = \left(\frac{1}{2}\right)^2 = \frac{1}{4} = 0.25$
   Since $0.5 > 0.25$, the line lies strictly above the parabola on $(0, 1)$.

Therefore:
$$
y_{\text{upper}} = x \qquad \text{and} \qquad y_{\text{lower}} = x^2
$$

---

### Step 3: Formulate and Evaluate the Integral

Set up the area integral:
$$
A = \int_0^1 \Big(y_{\text{upper}} - y_{\text{lower}}\Big) \, dx = \int_0^1 (x - x^2) \, dx
$$

1. Find the antiderivative:
   $$
   \int (x - x^2) \, dx = \frac{x^2}{2} - \frac{x^3}{3}
   $$

2. Apply the Fundamental Theorem of Calculus:
   $$
   A = \left[\frac{x^2}{2} - \frac{x^3}{3}\right]_0^1
   $$

3. Evaluate at the limits:
   - At $x = 1$:
     $$
     \frac{1^2}{2} - \frac{1^3}{3} = \frac{1}{2} - \frac{1}{3} = \frac{3 - 2}{6} = \frac{1}{6}
     $$
   - At $x = 0$:
     $$
     \frac{0^2}{2} - \frac{0^3}{3} = 0
     $$

4. Compute the difference:
   $$
   A = \frac{1}{6} - 0 = \frac{1}{6}
   $$

The exact area of the enclosed region is:
$$
\mathbf{A = \frac{1}{6} \approx 0.1667}
$$

---

## 4. Verification and Consistency Checks

1. **Decomposition Check (Subtractive Areas):**
   The area between the two curves equals the area under the line minus the area under the parabola on $[0, 1]$:
   - Area under $y = x$ on $[0, 1]$ (right triangle of base 1, height 1):
     $$
     A_{\text{triangle}} = \int_0^1 x \, dx = \left[\frac{x^2}{2}\right]_0^1 = \frac{1}{2} = \frac{3}{6}
     $$
   - Area under $y = x^2$ on $[0, 1]$:
     $$
     A_{\text{parabola}} = \int_0^1 x^2 \, dx = \left[\frac{x^3}{3}\right]_0^1 = \frac{1}{3} = \frac{2}{6}
     $$
   - Difference:
     $$
     A = A_{\text{triangle}} - A_{\text{parabola}} = \frac{3}{6} - \frac{2}{6} = \frac{1}{6} \quad (\checkmark)
     $$

2. **Archimedes' Quadrature Formula Check:**
   - The chord connecting $(0, 0)$ to $(1, 1)$ has slope $m = 1$.
   - The tangent to $y = x^2$ is parallel to the chord when $\frac{d}{dx}[x^2] = 2x = 1 \implies x = \frac{1}{2}$.
   - The vertex of the parabolic segment is at $\left(\frac{1}{2}, \frac{1}{4}\right)$.
   - The vertical distance from the chord $y = x$ to the parabola at $x = 1/2$ is:
     $$
     d_{\text{vert}} = \frac{1}{2} - \frac{1}{4} = \frac{1}{4}
     $$
   - The inscribed triangle with vertices $(0, 0)$, $(1, 1)$, and $\left(\frac{1}{2}, \frac{1}{4}\right)$ has area:
     $$
     \text{Area}(\triangle) = \frac{1}{2} \left| 0(1 - 1/4) + 1(1/4 - 0) + \frac{1}{2}(0 - 1) \right| = \frac{1}{2} \left| \frac{1}{4} - \frac{1}{2} \right| = \frac{1}{2} \left| -\frac{1}{4} \right| = \frac{1}{8}
     $$
   - Applying Archimedes' classical theorem:
     $$
     A = \frac{4}{3} \times \text{Area}(\triangle) = \frac{4}{3} \times \frac{1}{8} = \frac{4}{24} = \frac{1}{6} \quad (\checkmark)
     $$
   Archimedes' theorem completely confirms the calculus solution.
