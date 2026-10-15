# Solution to Problem 10: Definite Integral and Checking the Result

## 1. Problem Statement

Given the definite integral:
$$
I = \int_0^2 (x^2 + 1) \, dx
$$

1. Using the bound $1 \le x^2 + 1 \le 5$ on the interval $[0, 2]$, establish a rigorous lower and upper bound (prior estimate) for the value of the integral before carrying out any exact calculations.
2. Compute the exact value of the integral using the Fundamental Theorem of Calculus.
3. Compare the exact result with the prior estimate.
4. Explain what types of algebraic, arithmetic, and conceptual errors this method of bounding can effectively detect.

---

## 2. Theoretical Background and Concepts

1. **The Bounding (Comparison) Property of the Definite Integral:**
   If a continuous function $f(x)$ is bounded on $[a, b]$ such that:
   $$
   m \le f(x) \le M \quad \forall x \in [a, b]
   $$
   where $m = \min_{[a, b]} f(x)$ and $M = \max_{[a, b]} f(x)$, then integrating the inequality yields:
   $$
   \int_a^b m \, dx \le \int_a^b f(x) \, dx \le \int_a^b M \, dx
   $$
   Since $m$ and $M$ are constants:
   $$
   m(b - a) \le \int_a^b f(x) \, dx \le M(b - a)
   $$

2. **Geometric Interpretation of the Bounds:**
   - The lower bound $m(b - a)$ is the area of the inscribed rectangle of width $(b - a)$ and height equal to the minimum value $m$.
   - The upper bound $M(b - a)$ is the area of the circumscribed rectangle of width $(b - a)$ and height equal to the maximum value $M$.
   - The true area under the curve is strictly trapped between these two geometric rectangles.

3. **Positivity Preservation:**
   If $f(x) \ge 0$ everywhere on $[a, b]$, then $\int_a^b f(x) \, dx \ge 0$. Any computation yielding a negative result for a positive function is immediately identifiable as false.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Prior Estimation of the Integral Range

1. **Extreme Values of the Integrand on $[0, 2]$:**
   Consider $f(x) = x^2 + 1$.
   Differentiating:
   $$
   f'(x) = 2x \ge 0 \quad \forall x \in [0, 2]
   $$
   Because $f'(x) \ge 0$, $f(x)$ is strictly increasing on $[0, 2]$.
   - Minimum occurs at the left endpoint $x = 0$:
     $$
     m = f(0) = 0^2 + 1 = 1
     $$
   - Maximum occurs at the right endpoint $x = 2$:
     $$
     M = f(2) = 2^2 + 1 = 5
     $$
   Thus, for all $x \in [0, 2]$:
   $$
   1 \le x^2 + 1 \le 5
   $$

2. **Calculate the Bounding Interval:**
   The interval length is $b - a = 2 - 0 = 2$.
   Applying the bounding property:
   $$
   1 \cdot (2 - 0) \le \int_0^2 (x^2 + 1) \, dx \le 5 \cdot (2 - 0)
   $$
   $$
   2 \le \int_0^2 (x^2 + 1) \, dx \le 10
   $$

**Prior Prediction:**
The exact value of the integral must lie strictly inside the interval **$[2, 10]$**.

---

### Step 2: Exact Calculation

1. Find the general antiderivative of $f(x) = x^2 + 1$:
   $$
   F(x) = \int (x^2 + 1) \, dx = \frac{x^3}{3} + x
   $$

2. Apply the Fundamental Theorem of Calculus:
   $$
   I = \int_0^2 (x^2 + 1) \, dx = \left[\frac{x^3}{3} + x\right]_0^2
   $$

3. Evaluate at the boundaries:
   - At upper limit $x = 2$:
     $$
     F(2) = \frac{2^3}{3} + 2 = \frac{8}{3} + 2 = \frac{8 + 6}{3} = \frac{14}{3}
     $$
   - At lower limit $x = 0$:
     $$
     F(0) = \frac{0^3}{3} + 0 = 0
     $$

4. Compute the difference:
   $$
   I = F(2) - F(0) = \frac{14}{3} - 0 = \frac{14}{3} = 4\frac{2}{3} \approx 4.6667
   $$

---

### Step 3: Comparison with the Prior Estimate

Check the exact result against the prior bounding inequality:
$$
2 \le \frac{14}{3} \approx 4.67 \le 10 \quad (\checkmark)
$$
The exact value $4.67$ lies well within the predicted bounds $[2, 10]$.
Furthermore, the average height of the function is:
$$
\bar{f} = \frac{1}{b - a} \int_a^b f(x) \, dx = \frac{1}{2} \cdot \frac{14}{3} = \frac{7}{3} \approx 2.33
$$
which lies sensibly between the minimum height $1$ and the maximum height $5$.

---

### Step 4: Types of Errors Detected by Bounding Checks

Establishing bounding rectangles before calculating is one of the most powerful self-check heuristics in applied mathematics. It reliably exposes several major classes of errors:

1. **Sign and Limit Inversion Errors:**
   A common student slip is evaluating $F(a) - F(b)$ instead of $F(b) - F(a)$, producing a negative result: $-\frac{14}{3} \approx -4.67$.
   Since the lower bound is $+2 > 0$, any negative output is instantly flagged as mathematically impossible.

2. **Integration Rule Errors:**
   Suppose a student falsely assumes that the power rule applies to composite expressions without the chain rule, writing:
   $$
   \int (x^2 + 1) \, dx \stackrel{?}{=} \frac{(x^2 + 1)^2}{2}
   $$
   Evaluating this from $0$ to $2$:
   $$
   \frac{(2^2 + 1)^2}{2} - \frac{(0^2 + 1)^2}{2} = \frac{25}{2} - \frac{1}{2} = \frac{24}{2} = 12
   $$
   Since $12 > 10$, this erroneous result exceeds the circumscribed bounding box, immediately warning the student that the integration rule was flawed.

3. **Missing Denominators (Order-of-Magnitude Slips):**
   If a student forgets to divide by $3$ when integrating $x^2$ (writing $\int x^2 \, dx = x^3$), the calculation yields:
   $$
   [x^3 + x]_0^2 = 2^3 + 2 = 8 + 2 = 10
   $$
   Because the function only touches its maximum height $5$ at the single endpoint $x = 2$, the integral must be strictly less than $10$. Obtaining $10$ immediately alerts the student to an overestimation error.

4. **Power Arithmetic Errors:**
   Miscalculating $2^3$ as $6$ instead of $8$ produces $\frac{6}{3} + 2 = 4$. While $4 \in [2, 10]$, comparing with a closer estimate (e.g. trapezoidal $\frac{1 + 5}{2} \times 2 = 6$) reveals inconsistency.

---

## 4. Verification and Consistency Checks

1. **Simpson's Rule Exactness:**
   Simpson's rule is known to be **exact** for all polynomials of degree $\le 3$.
   Using $n = 2$ intervals on $[0, 2]$ with $x_0 = 0, x_1 = 1, x_2 = 2$ and $\Delta x = 1$:
   $$
   S_2 = \frac{\Delta x}{3} \Big[f(0) + 4f(1) + f(2)\Big]
   $$
   Evaluate the heights:
   - $f(0) = 0^2 + 1 = 1$
   - $f(1) = 1^2 + 1 = 2$
   - $f(2) = 2^2 + 1 = 5$
   Substitute:
   $$
   S_2 = \frac{1}{3} \Big[1 + 4(2) + 5\Big] = \frac{1}{3} [1 + 8 + 5] = \frac{14}{3}
   $$
   Simpson's rule produces the exact fraction $\frac{14}{3}$, fully verifying the analytical result.

2. **Geometric Area Diagram:**
```text
       y
       ^
   5   |             * (2, 5)   Upper Bound Box Area = 5 * 2 = 10
   4   |            *|
   3   |           * |
   2   |      *   *  |
   1   |* - - - - - -+          Lower Bound Box Area = 1 * 2 = 2
-------+-------------+---------> x
       0             2
```
The true area $\frac{14}{3} \approx 4.67$ fills slightly less than half of the circumscribed box, consistent with the convex upward curve of a parabola.
