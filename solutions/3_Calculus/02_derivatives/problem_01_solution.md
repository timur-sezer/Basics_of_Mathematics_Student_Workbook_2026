# Solution to Problem 1: Derivative of a Polynomial and the Slope of a Tangent Line

## 1. Problem Statement

Given the polynomial function:
$$
f(x) = 3x^5 - 2x^3 + 7x - 4
$$

1. Find the derivative $f'(x)$ using basic differentiation rules.
2. Compute the values of the derivative at $x = 0$ and $x = 1$: $f'(0)$ and $f'(1)$.
3. Determine the algebraic sign of each computed value.
4. Explain the geometric significance of these values regarding the slope and behavior of the tangent line to the graph of $f(x)$ at the corresponding points.

---

## 2. Theoretical Background and Concepts

1. **The Power Rule for Differentiation:**
   For any real constant $n \in \mathbb{R}$:
   $$
   \frac{d}{dx}[x^n] = n x^{n-1}
   $$

2. **Linearity of the Derivative (Constant Multiple and Sum/Difference Rules):**
   For differentiable functions $u(x), v(x)$ and constants $c_1, c_2 \in \mathbb{R}$:
   $$
   \frac{d}{dx}[c_1 u(x) \pm c_2 v(x)] = c_1 \frac{d}{dx}[u(x)] \pm c_2 \frac{d}{dx}[v(x)]
   $$
   The derivative of any constant $c \in \mathbb{R}$ is zero: $\frac{d}{dx}[c] = 0$.

3. **Geometric Interpretation of the Derivative:**
   The derivative $f'(x_0)$ evaluates the instantaneous rate of change of $f(x)$ at $x = x_0$. Geometrically, $f'(x_0)$ is the slope $m$ of the tangent line to the curve $y = f(x)$ at the point $(x_0, f(x_0))$:
   $$
   m = \tan \theta = f'(x_0)
   $$
   where $\theta$ is the inclination angle of the tangent line with respect to the positive $x$-axis.
   - **$f'(x_0) > 0$:** The tangent line has a positive slope (slopes upward from left to right), indicating that the function is strictly increasing in an open neighborhood around $x_0$.
   - **$f'(x_0) < 0$:** The tangent line has a negative slope (slopes downward from left to right), indicating that the function is strictly decreasing in an open neighborhood around $x_0$.
   - **$f'(x_0) = 0$:** The tangent line is horizontal ($m = 0$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Differentiate $f(x)$ Term-by-Term

The function is a polynomial:
$$
f(x) = 3x^5 - 2x^3 + 7x - 4
$$

Applying the linearity property:
$$
f'(x) = 3 \frac{d}{dx}[x^5] - 2 \frac{d}{dx}[x^3] + 7 \frac{d}{dx}[x^1] - \frac{d}{dx}[4]
$$

Applying the power rule to each power of $x$:
- $\frac{d}{dx}[x^5] = 5x^4$
- $\frac{d}{dx}[x^3] = 3x^2$
- $\frac{d}{dx}[x^1] = 1x^0 = 1$
- $\frac{d}{dx}[4] = 0$

Multiplying by the respective coefficients:
$$
f'(x) = 3(5x^4) - 2(3x^2) + 7(1) - 0 = 15x^4 - 6x^2 + 7
$$

Thus, the derivative function is:
$$
f'(x) = 15x^4 - 6x^2 + 7
$$

---

### Step 2: Compute $f'(0)$ and Geometric Interpretation

Substitute $x = 0$ into $f'(x)$:
$$
f'(0) = 15(0)^4 - 6(0)^2 + 7 = 0 - 0 + 7 = 7
$$

- **Sign:** $f'(0) = +7 > 0$ (strictly positive).
- **Geometric Interpretation:**
  - The function value at $x = 0$ is $f(0) = 3(0)^5 - 2(0)^3 + 7(0) - 4 = -4$, giving the $y$-intercept $(0, -4)$.
  - The slope of the tangent line to the curve at $(0, -4)$ is $m = 7$.
  - The tangent line equation is $y - (-4) = 7(x - 0) \implies y = 7x - 4$.
  - The positive sign means the tangent line rises steeply from left to right with inclination angle $\theta = \arctan(7) \approx 81.87^\circ$.
  - The function $f(x)$ is strictly increasing at $x = 0$.

---

### Step 3: Compute $f'(1)$ and Geometric Interpretation

Substitute $x = 1$ into $f'(x)$:
$$
f'(1) = 15(1)^4 - 6(1)^2 + 7 = 15(1) - 6(1) + 7 = 15 - 6 + 7 = 16
$$

- **Sign:** $f'(1) = +16 > 0$ (strictly positive).
- **Geometric Interpretation:**
  - The function value at $x = 1$ is $f(1) = 3(1)^5 - 2(1)^3 + 7(1) - 4 = 3 - 2 + 7 - 4 = 4$, so the point of tangency is $(1, 4)$.
  - The slope of the tangent line at $(1, 4)$ is $m = 16$.
  - The tangent line equation is $y - 4 = 16(x - 1) \implies y = 16x - 12$.
  - Since $16 > 7$, the curve is rising more than twice as steeply at $x = 1$ compared to $x = 0$, with an inclination angle of $\theta = \arctan(16) \approx 86.42^\circ$.
  - The function is strictly increasing at $x = 1$.

---

## 4. Verification and Consistency Checks

1. **Global Sign Analysis of $f'(x)$:**
   Notice that $f'(x) = 15x^4 - 6x^2 + 7$ is quadratic in $u = x^2$ (with $u \ge 0$):
   $$
   g(u) = 15u^2 - 6u + 7
   $$
   The discriminant of this quadratic is:
   $$
   \Delta = (-6)^2 - 4(15)(7) = 36 - 420 = -384 < 0
   $$
   Since the leading coefficient $15 > 0$ and $\Delta < 0$, the quadratic $g(u)$ has no real roots and is strictly positive for all $u \in \mathbb{R}$.
   Completing the square:
   $$
   f'(x) = 15\left(x^2 - \frac{1}{5}\right)^2 + 7 - \frac{15}{25} = 15\left(x^2 - \frac{1}{5}\right)^2 + \frac{32}{5} \ge \frac{32}{5} = 6.4 > 0 \quad \forall x \in \mathbb{R}
   $$
   Therefore, the slope of the tangent line is **strictly positive everywhere** on $\mathbb{R}$, which is fully consistent with $f'(0) = 7 > 0$ and $f'(1) = 16 > 0$.

2. **Difference Quotient Limit Check at $x = 0$:**
   $$
   f'(0) = \lim_{h \to 0} \frac{f(h) - f(0)}{h} = \lim_{h \to 0} \frac{(3h^5 - 2h^3 + 7h - 4) - (-4)}{h} = \lim_{h \to 0} (3h^4 - 2h^2 + 7) = 7
   $$
   This independently confirms $f'(0) = 7$.
