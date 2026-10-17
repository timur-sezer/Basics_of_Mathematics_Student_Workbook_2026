# Solution to Problem 1: A Cubic Polynomial

## 1. Problem Statement

Analyze the monotonicity and local extrema of the cubic polynomial:
$$
f(x) = x^3 - 3x^2 + 2
$$

1. Determine the domain and compute the first derivative $f'(x)$.
2. Identify all critical (stationary) points by solving $f'(x) = 0$.
3. Construct a sign chart for $f'(x)$ and determine the intervals on which the function is strictly increasing or strictly decreasing.
4. Classify the local extrema using the First and Second Derivative Tests, computing the exact coordinates $(x, y)$.
5. Analyze concavity and determine the inflection point.
6. Provide an ASCII sketch of the graph indicating the critical points, inflection point, and intercepts.

---

## 2. Theoretical Background and Concepts

1. **Stationary Points and Critical Points:**
   For a differentiable function on an open interval, the critical points are the solutions to:
   $$
   f'(x) = 0
   $$

2. **Monotonicity (The First Derivative Rule):**
   - If $f'(x) > 0$ on an interval $(a, b)$, then $f(x)$ is **strictly increasing** on $[a, b]$.
   - If $f'(x) < 0$ on an interval $(a, b)$, then $f(x)$ is **strictly decreasing** on $[a, b]$.

3. **The First Derivative Test for Local Extrema:**
   Let $c$ be a critical point ($f'(c) = 0$):
   - If $f'(x)$ changes sign from **positive to negative** at $c$, then $f(c)$ is a **strict local maximum**.
   - If $f'(x)$ changes sign from **negative to positive** at $c$, then $f(c)$ is a **strict local minimum**.
   - If $f'(x)$ does not change sign across $c$, this rules out a strict turning extremum in this test, but does not by itself prove an inflection point; establishing an inflection point requires verifying a change of concavity ($f''(x)$ changing sign across $c$).

4. **Curvature and Inflection Points (Second Derivative):**
   - If $f''(x) > 0$, the graph is **concave upward** ($\cup$).
   - If $f''(x) < 0$, the graph is **concave downward** ($\cap$).
   - A point $(x_0, f(x_0))$ where $f''(x_0) = 0$ and $f''(x)$ changes sign is an **inflection point**.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and First Derivative

The function is a polynomial, so its domain is all real numbers:
$$
\mathcal{D}_f = \mathbb{R}
$$

Differentiating term-by-term using the power and constant rules:
$$
f'(x) = \frac{d}{dx}[x^3] - 3\frac{d}{dx}[x^2] + \frac{d}{dx}[2] = 3x^2 - 6x
$$

Factoring out the greatest common factor $3x$:
$$
f'(x) = 3x(x - 2)
$$

---

### Step 2: Find the Critical Points

Set $f'(x) = 0$:
$$
3x(x - 2) = 0 \implies x_1 = 0 \quad \text{or} \quad x_2 = 2
$$

The critical points on the real axis are $x = 0$ and $x = 2$.

---

### Step 3: Sign Chart and Monotonicity Intervals

The two critical points divide the real line into three open intervals:
1. $(-\infty, 0)$
2. $(0, 2)$
3. $(2, \infty)$

We test the sign of $f'(x) = 3x(x - 2)$ in each interval:

- **Interval $(-\infty, 0)$:**
  Choose test point $x = -1$:
  $$
  f'(-1) = 3(-1)(-1 - 2) = -3(-3) = +9 > 0
  $$
  $f'(x) > 0 \implies f(x)$ is **strictly increasing** on $(-\infty, 0]$.

- **Interval $(0, 2)$:**
  Choose test point $x = 1$:
  $$
  f'(1) = 3(1)(1 - 2) = 3(-1) = -3 < 0
  $$
  $f'(x) < 0 \implies f(x)$ is **strictly decreasing** on $[0, 2]$.

- **Interval $(2, \infty)$:**
  Choose test point $x = 3$:
  $$
  f'(3) = 3(3)(3 - 2) = 9(1) = +9 > 0
  $$
  $f'(x) > 0 \implies f(x)$ is **strictly increasing** on $[2, \infty)$.

**Summary Table:**

| Interval | $(-\infty, 0)$ | $x = 0$ | $(0, 2)$ | $x = 2$ | $(2, \infty)$ |
|:---|:---:|:---:|:---:|:---:|:---:|
| **Sign of $f'(x)$** | $+$ | $0$ | $-$ | $0$ | $+$ |
| **Behavior of $f(x)$** | $\nearrow$ Increasing | **Local Max** | $\searrow$ Decreasing | **Local Min** | $\nearrow$ Increasing |

---

### Step 4: Coordinates and Character of Local Extrema

1. **Local Maximum at $x = 0$:**
   Since $f'(x)$ transitions from positive to negative, $x = 0$ is a strict local maximum.
   $$
   y_1 = f(0) = 0^3 - 3(0)^2 + 2 = 2
   $$
   The local maximum is at:
   $$
   \mathbf{M(0, 2)}
   $$

2. **Local Minimum at $x = 2$:**
   Since $f'(x)$ transitions from negative to positive, $x = 2$ is a strict local minimum.
   $$
   y_2 = f(2) = 2^3 - 3(2^2) + 2 = 8 - 12 + 2 = -2
   $$
   The local minimum is at:
   $$
   \mathbf{m(2, -2)}
   $$

---

### Step 5: Second Derivative, Concavity, and Inflection Point

Differentiate $f'(x) = 3x^2 - 6x$:
$$
f''(x) = 6x - 6 = 6(x - 1)
$$
Setting $f''(x) = 0$ gives $x = 1$.
- For $x < 1$: $f''(x) < 0 \implies f(x)$ is **concave downward** ($\cap$).
- For $x > 1$: $f''(x) > 0 \implies f(x)$ is **concave upward** ($\cup$).

At $x = 1$, the concavity reverses, and the function value is:
$$
f(1) = 1^3 - 3(1^2) + 2 = 0
$$
Thus, the point of inflection is:
$$
\mathbf{I(1, 0)}
$$
Notice that $I(1, 0)$ is precisely the midpoint of the segment connecting the local maximum $(0, 2)$ and local minimum $(2, -2)$:
$$
\left(\frac{0 + 2}{2}, \frac{2 + (-2)}{2}\right) = (1, 0)
$$
Every cubic polynomial is point-symmetric with respect to its unique inflection point.

---

### Step 6: Zeros of the Function and Graphical Sketch

To locate the $x$-intercepts:
$$
x^3 - 3x^2 + 2 = 0
$$
Since $f(1) = 0$, $x - 1$ is a factor. By polynomial division:
$$
x^3 - 3x^2 + 2 = (x - 1)(x^2 - 2x - 2) = 0
$$
Roots of $x^2 - 2x - 2 = 0$:
$$
x = \frac{2 \pm \sqrt{4 + 8}}{2} = 1 \pm \sqrt{3} \approx 1 \pm 1.732
$$
The three $x$-intercepts are:
$$
x_1 = 1 - \sqrt{3} \approx -0.732, \qquad x_2 = 1, \qquad x_3 = 1 + \sqrt{3} \approx 2.732
$$

**ASCII Graph Sketch:**
```text
                     y
                     ^
         3           |
                     * M(0, 2) [Local Maximum on y-axis]
         2         / | \
                 /   |   \
         1     /     |     \
   ----------*-------+------*-------*-------> x
      (1-√3, 0)      |    I(1,0)    | (1+√3, 0)
     [≈ -0.732]      |              | [≈ 2.732]
        -1   |       |               \     /
             |       |                \   /
        -2   |       +------------------* m(2, -2) [Local Minimum]
             |       |
        -3   v       |
   (rises from -inf) v
```
*Labels:* Local maximum $M(0, 2)$ lies on the $y$-axis; left branch rises from $-\infty$ through $x$-intercept $(1-\sqrt{3}, 0) \approx (-0.732, 0)$ to $M(0, 2)$; curve decreases through inflection point $I(1, 0)$ to local minimum $m(2, -2)$; right branch rises through $x$-intercept $(1+\sqrt{3}, 0) \approx (2.732, 0)$ toward $+\infty$.

---

## 4. Verification and Consistency Checks

1. **Second Derivative Test on Critical Points:**
   - At $x = 0$: $f''(0) = 6(0) - 6 = -6 < 0 \implies$ strict local maximum ($\checkmark$).
   - At $x = 2$: $f''(2) = 6(2) - 6 = +6 > 0 \implies$ strict local minimum ($\checkmark$).

2. **End-Behavior (Global Limits):**
   - Leading term is $x^3$:
     $$
     \lim_{x \to -\infty} f(x) = \lim_{x \to -\infty} x^3 = -\infty
     $$
     $$
     \lim_{x \to +\infty} f(x) = \lim_{x \to +\infty} x^3 = +\infty
     $$
   - The curve rises from $-\infty$ in quadrant III, reaches local maximum $(0, 2)$, drops through inflection point $(1, 0)$ to local minimum $(2, -2)$, and climbs to $+\infty$ in quadrant I.
   This matches all signs and intermediate values.
