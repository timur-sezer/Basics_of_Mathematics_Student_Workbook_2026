# Solution to Problem 14: Reconstructing Information from the Derivative

## 1. Problem Statement

It is given that the derivative of an unknown differentiable function $f(x)$ is:
$$
f'(x) = (x - 1)(x + 2)
$$

1. Determine the intervals of monotonicity and the exact $x$-coordinates and character of all local extrema of $f(x)$.
2. Analyze the concavity and locate the $x$-coordinate of the inflection point.
3. Produce a qualitative sketch of a possible curve $y = f(x)$ and explain what information remains undetermined without additional initial conditions.
4. For the specific function:
   $$
   g(x) = \frac{x^3}{3} + \frac{x^2}{2} - 2x
   $$
   verify that $g'(x) = (x - 1)(x + 2)$.
5. Compute the exact coordinates of the local extrema, inflection point, and zeros of $g(x)$, and compare this anchored graph with the qualitative sketch.

---

## 2. Theoretical Background and Concepts

1. **Reconstruction of a Function from Its Derivative:**
   The derivative $f'(x)$ dictates the slope and local direction of the function at every point:
   - $f'(x) > 0 \iff f(x)$ is increasing.
   - $f'(x) < 0 \iff f(x)$ is decreasing.
   - $f'(x) = 0$ with a sign change identifies local extrema.

2. **The Constant of Integration ($+C$):**
   By the Corollary to the Mean Value Theorem, if two functions have identical derivatives on an interval, they differ by a constant:
   $$
   f'(x) = g'(x) \implies f(x) = g(x) + C, \qquad C \in \mathbb{R}
   $$
   Therefore, knowing $f'(x)$ completely determines the **shape, slope, curvature, and horizontal locations of all extrema and inflection points**, but leaves the **vertical elevation** (vertical translation) completely free.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Monotonicity and Extrema from $f'(x)$

The derivative is:
$$
f'(x) = (x - 1)(x + 2)
$$
The critical points are the roots of $f'(x) = 0$:
$$
x_1 = -2, \qquad x_2 = 1
$$

These two points partition $\mathbb{R}$ into three intervals:
1. **Interval $(-\infty, -2)$:**
   Test $x = -3$:
   $$
   f'(-3) = (-3 - 1)(-3 + 2) = (-4)(-1) = +4 > 0
   $$
   $f'(x) > 0 \implies f(x)$ is **strictly increasing** on $(-\infty, -2]$.

2. **Interval $(-2, 1)$:**
   Test $x = 0$:
   $$
   f'(0) = (0 - 1)(0 + 2) = (-1)(2) = -2 < 0
   $$
   $f'(x) < 0 \implies f(x)$ is **strictly decreasing** on $[-2, 1]$.

3. **Interval $(1, \infty)$:**
   Test $x = 2$:
   $$
   f'(2) = (2 - 1)(2 + 2) = (1)(4) = +4 > 0
   $$
   $f'(x) > 0 \implies f(x)$ is **strictly increasing** on $[1, \infty)$.

**Classification of Extrema:**
- **At $x = -2$:** $f'(x)$ changes sign from positive to negative $\implies$ **strict local maximum** at $x = -2$.
- **At $x = 1$:** $f'(x)$ changes sign from negative to positive $\implies$ **strict local minimum** at $x = 1$.

---

### Step 2: Concavity and Inflection Point from $f''(x)$

Expand the derivative:
$$
f'(x) = x^2 + x - 2
$$
Differentiate to obtain the second derivative:
$$
f''(x) = \frac{d}{dx}[x^2 + x - 2] = 2x + 1 = 2\left(x + \frac{1}{2}\right)
$$
Setting $f''(x) = 0$:
$$
2x + 1 = 0 \iff x = -\frac{1}{2}
$$
- For $x < -\frac{1}{2}$: $f''(x) < 0 \implies f(x)$ is **concave downward** ($\cap$).
- For $x > -\frac{1}{2}$: $f''(x) > 0 \implies f(x)$ is **concave upward** ($\cup$).
- An **inflection point** occurs at $x = -\frac{1}{2}$, exactly midway between the two critical points:
  $$
  \frac{-2 + 1}{2} = -\frac{1}{2}
  $$

---

### Step 3: Qualitative Sketch of $f(x)$

From the derivative alone, we know the qualitative profile is an **"N-shaped" cubic curve**:
- Rises from $-\infty$ in the lower left.
- Reaches a crest (local maximum) at $x = -2$.
- Drops with downward concavity, passing through an inflection point at $x = -0.5$.
- Continues dropping with upward concavity until reaching a trough (local minimum) at $x = 1$.
- Climbs monotonically to $+\infty$ in the upper right.

*What is undetermined:*
The vertical position $y$ of the entire graph is unknown. The graph could be shifted up or down by any constant $C$ without changing $f'(x)$.

---

### Step 4: Verification for the Specific Function $g(x)$

Given:
$$
g(x) = \frac{x^3}{3} + \frac{x^2}{2} - 2x
$$

Differentiate term-by-term:
$$
g'(x) = \frac{d}{dx}\left[\frac{x^3}{3}\right] + \frac{d}{dx}\left[\frac{x^2}{2}\right] - \frac{d}{dx}[2x] = \frac{3x^2}{3} + \frac{2x}{2} - 2 = x^2 + x - 2
$$
Factor the quadratic:
$$
x^2 + x - 2 = (x - 1)(x + 2)
$$
This verifies that $g'(x) = (x - 1)(x + 2)$ identically.
Thus, $g(x)$ is a specific member of the family of antiderivatives of $f'(x)$, with integration constant $C = 0$.

---

### Step 5: Exact Quantitative Values for $g(x)$

1. **Local Maximum at $x = -2$:**
   $$
   g(-2) = \frac{(-2)^3}{3} + \frac{(-2)^2}{2} - 2(-2) = -\frac{8}{3} + \frac{4}{2} + 4 = -\frac{8}{3} + 6 = \frac{10}{3} \approx 3.333
   $$
   Local maximum: $\mathbf{M\left(-2, \frac{10}{3}\right)}$.

2. **Local Minimum at $x = 1$:**
   $$
   g(1) = \frac{1^3}{3} + \frac{1^2}{2} - 2(1) = \frac{1}{3} + \frac{1}{2} - 2 = \frac{5}{6} - \frac{12}{6} = -\frac{7}{6} \approx -1.167
   $$
   Local minimum: $\mathbf{m\left(1, -\frac{7}{6}\right)}$.

3. **Inflection Point at $x = -1/2$:**
   $$
   g\left(-\frac{1}{2}\right) = \frac{(-1/8)}{3} + \frac{(1/4)}{2} - 2\left(-\frac{1}{2}\right) = -\frac{1}{24} + \frac{1}{8} + 1 = \frac{-1 + 3 + 24}{24} = \frac{26}{24} = \frac{13}{12} \approx 1.083
   $$
   Inflection point: $\mathbf{I\left(-\frac{1}{2}, \frac{13}{12}\right)}$.

4. **Zeros (Intercepts) of $g(x)$:**
   Set $g(x) = 0$:
   $$
   x \left(\frac{x^2}{3} + \frac{x}{2} - 2\right) = 0 \iff \frac{x}{6}(2x^2 + 3x - 12) = 0
   $$
   - Root 1: $x = 0$ (the curve passes through the origin $(0, 0)$).
   - Roots 2 & 3:
     $$
     x = \frac{-3 \pm \sqrt{3^2 - 4(2)(-12)}}{2(2)} = \frac{-3 \pm \sqrt{9 + 96}}{4} = \frac{-3 \pm \sqrt{105}}{4} \approx \frac{-3 \pm 10.247}{4}
     $$
     $$
     x_a = \frac{-3 - 10.247}{4} \approx -3.312, \qquad x_b = \frac{-3 + 10.247}{4} \approx +1.812
     $$

**ASCII Graph of $g(x)$:**
```text
                               y
                               ^
         4                     |
                 * M(-2, 10/3) |
         3      / \            |
               /   \           |
         2    /     \          |
             /       * I(-0.5, 13/12)
         1  /         \        |
   --------*-----------+-------*---------+-------*-------------> x
      (-3.31, 0)       -2    (0, 0)      1   (1.81, 0)   /
        -1                     |          \             /
                               |           * m(1, -7/6)/
        -2                     |
```
*Labels:* Coordinate axes cross at $(0, 0)$; rising branch ascends from $-\infty$ through $x$-intercept $(-3.31, 0)$ to local maximum $M(-2, 10/3)$ strictly to the left of the $y$-axis; curve descends through inflection point $I(-0.5, 13/12)$ (also left of the $y$-axis) and passes through the origin $(0, 0)$ to local minimum $m(1, -7/6)$ strictly to the right of the $y$-axis; rising branch ascends from $m(1, -7/6)$ through $x$-intercept $(1.81, 0)$ to $+\infty$.

---

## 4. Verification and Consistency Checks

1. **Inflection Point Symmetry Verification:**
   In every cubic polynomial, the inflection point is the exact arithmetic mean of the two local extrema:
   - $x$-coordinate:
     $$
     \frac{x_{\max} + x_{\min}}{2} = \frac{-2 + 1}{2} = -\frac{1}{2} \quad (\checkmark)
     $$
   - $y$-coordinate:
     $$
     \frac{y_{\max} + y_{\min}}{2} = \frac{\frac{10}{3} + \left(-\frac{7}{6}\right)}{2} = \frac{\frac{20}{6} - \frac{7}{6}}{2} = \frac{\frac{13}{6}}{2} = \frac{13}{12} \quad (\checkmark)
     $$
   The inflection point $\left(-\frac{1}{2}, \frac{13}{12}\right)$ matches the midpoint formula.

2. **Integration Verification via Fundamental Theorem of Calculus:**
   $$
   \int_{-2}^1 f'(x) \, dx = \int_{-2}^1 (x^2 + x - 2) \, dx = \left[\frac{x^3}{3} + \frac{x^2}{2} - 2x\right]_{-2}^1 = g(1) - g(-2)
   $$
   $$
   g(1) - g(-2) = -\frac{7}{6} - \frac{20}{6} = -\frac{27}{6} = -\frac{9}{2} = -4.5
   $$
   Direct integration:
   $$
   \left(\frac{1}{3} + \frac{1}{2} - 2\right) - \left(-\frac{8}{3} + 2 + 4\right) = -\frac{7}{6} - \frac{10}{3} = -\frac{27}{6} = -4.5
   $$
   This proves that the net vertical drop from the peak to the trough is exactly $4.5$ units.
