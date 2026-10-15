# Solution to Problem 6: When Does a Logarithm Appear from an Integral?

## 1. Problem Statement

Compute the indefinite integral:
$$
\int \frac{2x}{x^2 + 5} \, dx
$$

1. Identify the denominator as a candidate for substitution and calculate its derivative.
2. Compare the numerator with the derivative of the denominator to demonstrate the canonical pattern $\frac{g'(x)}{g(x)}$.
3. Explain why the power rule for integration fails here and why the natural logarithm inevitably appears as the antiderivative.
4. Compute the exact family of antiderivatives and justify why the absolute value signs in $\ln|u|$ can be omitted.
5. Verify the result by differentiation.

---

## 2. Theoretical Background and Concepts

1. **The Logarithmic Integral Rule:**
   For any strictly positive or non-zero differentiable function $g(x)$:
   $$
   \int \frac{g'(x)}{g(x)} \, dx = \ln|g(x)| + C
   $$
   This is the integration counterpart to the chain rule for logarithms:
   $$
   \frac{d}{dx}[\ln|g(x)|] = \frac{g'(x)}{g(x)}
   $$

2. **The Singularity of the Power Rule at $n = -1$:**
   The standard power rule for integration:
   $$
   \int u^n \, du = \frac{u^{n+1}}{n + 1} + C
   $$
   holds for all exponents **except $n = -1$**.
   When $n = -1$, the formula would yield division by zero: $\frac{u^{-1+1}}{-1+1} = \frac{u^0}{0} = \frac{1}{0}$, which is undefined.
   The unique antiderivative of $u^{-1} = \frac{1}{u}$ on its domain of definition is the natural logarithm function:
   $$
   \int \frac{1}{u} \, du = \ln|u| + C
   $$

3. **Positivity of the Argument:**
   While the general antiderivative of $\frac{1}{u}$ requires absolute value bars ($\ln|u|$) to ensure the argument of the logarithm is positive for negative $u$, whenever $g(x) > 0$ strictly for all $x \in \mathbb{R}$, $|g(x)| = g(x)$, and the absolute value bars may be simplified to standard parentheses: $\ln(g(x))$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Denominator and Compute Its Derivative

1. Let the denominator be the candidate substitution variable:
   $$
   u = g(x) = x^2 + 5
   $$

2. Compute the derivative of $g(x)$ with respect to $x$:
   $$
   g'(x) = \frac{d}{dx}[x^2 + 5] = 2x
   $$

3. In differential form:
   $$
   du = 2x \, dx
   $$

---

### Step 2: Compare the Numerator with the Derivative

- The numerator of the integrand is precisely $2x$.
- Multiplying the numerator by $dx$ gives:
  $$
  \text{Numerator} \cdot dx = 2x \, dx = du
  $$
- The entire integrand is an exact manifestation of the canonical pattern:
  $$
  \frac{g'(x)}{g(x)} \, dx
  $$
  The numerator is the exact derivative of the denominator.

---

### Step 3: Why a Logarithm Appears

Rewrite the integral in terms of $u$:
$$
\int \frac{2x}{x^2 + 5} \, dx = \int \frac{1}{x^2 + 5} \cdot (2x \, dx) = \int \frac{1}{u} \, du = \int u^{-1} \, du
$$

- If one attempted to apply the standard power rule $\int u^n \, du = \frac{u^{n+1}}{n+1}$:
  $$
  \int u^{-1} \, du \stackrel{?}{=} \frac{u^{-1+1}}{-1 + 1} = \frac{u^0}{0}
  $$
  The power rule collapses due to division by zero.
- In calculus, the gap left by the power rule at $n = -1$ is filled uniquely by the natural logarithm. Because $\frac{d}{du}[\ln|u|] = \frac{1}{u}$, the antiderivative of $\frac{1}{u}$ is:
  $$
  \int \frac{1}{u} \, du = \ln|u| + C
  $$
- The logarithm appears not by coincidence, but because it is the fundamental mathematical function whose rate of change is inversely proportional to its input.

---

### Step 4: Evaluate and Simplify the Antiderivative

1. Substitute the antiderivative:
   $$
   \int \frac{du}{u} = \ln|u| + C = \ln|x^2 + 5| + C
   $$

2. Analyze the sign of the argument $x^2 + 5$:
   For every real number $x \in \mathbb{R}$:
   $$
   x^2 \ge 0 \implies x^2 + 5 \ge 5 > 0
   $$
   Because the argument $x^2 + 5$ is strictly positive for all $x \in \mathbb{R}$, we have $|x^2 + 5| = x^2 + 5$.
   The absolute value signs are strictly unnecessary.

3. Final expression:
   $$
   F(x) = \ln(x^2 + 5) + C
   $$

---

### Step 5: Verification by Differentiation

Differentiate $F(x) = \ln(x^2 + 5) + C$ using the chain rule:
$$
F'(x) = \frac{d}{dx}[\ln(x^2 + 5) + C] = \frac{1}{x^2 + 5} \cdot \frac{d}{dx}[x^2 + 5] + 0
$$
$$
F'(x) = \frac{1}{x^2 + 5} \cdot (2x) = \frac{2x}{x^2 + 5}
$$
The derivative matches the integrand $f(x) = \frac{2x}{x^2 + 5}$ identically on $\mathbb{R}$.

---

## 4. Verification and Consistency Checks

1. **Definite Integral Evaluation on $[0, 2]$:**
   Evaluate $\int_0^2 \frac{2x}{x^2 + 5} \, dx$:
   - **Using $F(x)$:**
     $$
     \int_0^2 \frac{2x}{x^2 + 5} \, dx = \Big[\ln(x^2 + 5)\Big]_0^2 = \ln(2^2 + 5) - \ln(0^2 + 5) = \ln(9) - \ln(5) = \ln\left(\frac{9}{5}\right) = \ln(1.8) \approx 0.587787
     $$
   - **Using $u$-limits:**
     - At $x = 0$: $u(0) = 0^2 + 5 = 5$.
     - At $x = 2$: $u(2) = 2^2 + 5 = 9$.
     $$
     \int_5^9 \frac{1}{u} \, du = [\ln u]_5^9 = \ln 9 - \ln 5 = \ln(1.8) \approx 0.587787
     $$
   Both methods yield identical values.

2. **Numerical Trapezoidal Rule Check on $[0, 2]$:**
   Let $n = 4$ subintervals with step size $\Delta x = 0.5$:
   - $x_0 = 0 \implies f(0) = 0/5 = 0$
   - $x_1 = 0.5 \implies f(0.5) = 1/(0.25 + 5) = 1/5.25 \approx 0.190476$
   - $x_2 = 1.0 \implies f(1.0) = 2/(1 + 5) = 2/6 \approx 0.333333$
   - $x_3 = 1.5 \implies f(1.5) = 3/(2.25 + 5) = 3/7.25 \approx 0.413793$
   - $x_4 = 2.0 \implies f(2.0) = 4/(4 + 5) = 4/9 \approx 0.444444$
   Trapezoidal approximation:
   $$
   T_4 = 0.5 \times \left(\frac{0 + 0.444444}{2} + 0.190476 + 0.333333 + 0.413793\right) = 0.5 \times (0.222222 + 0.937602) = 0.5 \times 1.159824 = 0.579912
   $$
   The numerical estimate $0.5799$ closely approximates the exact analytical result $\ln(1.8) \approx 0.5878$, verifying the antiderivative.
