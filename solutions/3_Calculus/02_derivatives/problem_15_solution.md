# Solution to Problem 15: The Difference Quotient as a Check of the Derivative

## 1. Problem Statement

1. **Selection:**
   Choose a function from the problem set and an evaluation point $x_0$ where the derivative exists:
   $$
   f(x) = (x^2 + 1) e^x \quad \text{at} \quad x_0 = 0
   $$
2. **Exact Analytical Derivative:**
   Compute the exact theoretical value $f'(x_0)$ using calculus rules.
3. **Finite Difference Computations:**
   Compute the difference quotient:
   $$
   D(h) = \frac{f(x_0 + h) - f(x_0)}{h}
   $$
   for step sizes $h = 1$, $h = 0.1$, and $h = 0.01$ (and their negative counterparts for two-sided completeness).
4. **Comparative and Epistemological Analysis:**
   - Compare the computed numerical approximations with the exact analytical value $f'(x_0)$.
   - Explain why the convergence of the difference quotient is consistent with the definition of the derivative.
   - Explain why a finite number of numerical computations cannot replace a rigorous limit proof.

---

## 2. Theoretical Background and Concepts

1. **The Formal Definition of the Derivative:**
   For a function $f$ defined in an open neighborhood of $x_0$, the derivative $f'(x_0)$ exists and equals $L \in \mathbb{R}$ if and only if:
   $$
   \forall \varepsilon > 0, \; \exists \delta > 0 \; \text{such that} \; 0 < |h| < \delta \implies \left| \frac{f(x_0 + h) - f(x_0)}{h} - L \right| < \varepsilon
   $$

2. **Geometric Significance of the Difference Quotient:**
   The quotient $D(h) = \frac{f(x_0 + h) - f(x_0)}{h}$ is the exact slope of the secant line passing through $P(x_0, f(x_0))$ and $Q(x_0 + h, f(x_0 + h))$.
   As $h \to 0$, the secant lines rotate toward the tangent line whose slope is $f'(x_0)$.

3. **Taylor Series Truncation Error (Order of Approximation):**
   If $f$ is twice continuously differentiable ($C^2$) around $x_0$, Taylor's theorem states:
   $$
   f(x_0 + h) = f(x_0) + f'(x_0) h + \frac{f''(\xi)}{2} h^2 \quad \text{for some } \xi \text{ between } x_0 \text{ and } x_0 + h
   $$
   Dividing the increment by $h$:
   $$
   D(h) = \frac{f(x_0 + h) - f(x_0)}{h} = f'(x_0) + \frac{f''(\xi)}{2} h = f'(x_0) + \mathcal{O}(h)
   $$
   This proves that the difference quotient converges to $f'(x_0)$ with a linear error bound proportional to $h$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Exact Analytical Derivative $f'(0)$

From Problem 3, the derivative of $f(x) = (x^2 + 1)e^x$ is:
$$
f'(x) = (x + 1)^2 e^x
$$
Evaluating at the selected point $x_0 = 0$:
$$
f'(0) = (0 + 1)^2 e^0 = 1^2 \cdot 1 = 1
$$
Also evaluate the base function value:
$$
f(0) = (0^2 + 1) e^0 = 1 \cdot 1 = 1
$$

The exact theoretical derivative is:
$$
f'(0) = 1
$$

---

### Step 2: Formulate the Difference Quotient

For $x_0 = 0$ and $f(0) = 1$, the difference quotient is:
$$
D(h) = \frac{f(h) - f(0)}{h} = \frac{(h^2 + 1)e^h - 1}{h}
$$

---

### Step 3: Compute $D(h)$ for the Required Step Sizes

1. **For $h = 1$:**
   - $f(1) = (1^2 + 1)e^1 = 2e \approx 2(2.71828183) = 5.43656366$
   - Difference quotient:
     $$
     D(1) = \frac{5.43656366 - 1}{1} = 4.43656366
     $$
   - Absolute error: $|D(1) - 1| \approx 3.4366$.

2. **For $h = 0.1$:**
   - $f(0.1) = (0.1^2 + 1)e^{0.1} = (1.01)e^{0.1} \approx 1.01 \times 1.10517092 = 1.11622263$
   - Difference quotient:
     $$
     D(0.1) = \frac{1.11622263 - 1}{0.1} = \frac{0.11622263}{0.1} = 1.1622263
     $$
   - Absolute error: $|D(0.1) - 1| \approx 0.1622$.

3. **For $h = 0.01$:**
   - $f(0.01) = (0.01^2 + 1)e^{0.01} = (1.0001)e^{0.01} \approx 1.0001 \times 1.01005017 = 1.01015117$
   - Difference quotient:
     $$
     D(0.01) = \frac{1.01015117 - 1}{0.01} = \frac{0.01015117}{0.01} = 1.015117
     $$
   - Absolute error: $|D(0.01) - 1| \approx 0.0151$.

4. **Additional Verification: Approaching from the Left ($h < 0$):**
   - For $h = -0.1$:
     $$
     f(-0.1) = ((-0.1)^2 + 1)e^{-0.1} = (1.01)e^{-0.1} \approx 1.01 \times 0.90483742 = 0.91388579
     $$
     $$
     D(-0.1) = \frac{0.91388579 - 1}{-0.1} = \frac{-0.08611421}{-0.1} = 0.861142
     $$
   - For $h = -0.01$:
     $$
     f(-0.01) = (1.0001)e^{-0.01} \approx 1.0001 \times 0.99004983 = 0.99014884
     $$
     $$
     D(-0.01) = \frac{0.99014884 - 1}{-0.01} = 0.985116
     $$

---

### Step 4: Summary Table of Computations

| Step Size $h$ | $f(0 + h)$ | Difference $\Delta f = f(h) - 1$ | Difference Quotient $D(h)$ | Error $|D(h) - 1|$ |
|:---|:---|:---|:---|:---|
| $+1.0$ | $5.436564$ | $+4.436564$ | **$4.436564$** | $3.436564$ |
| $+0.1$ | $1.116223$ | $+0.116223$ | **$1.162226$** | $0.162226$ |
| $+0.01$ | $1.010151$ | $+0.010151$ | **$1.015117$** | $0.015117$ |
| $+0.001$ | $1.001002$ | $+0.001002$ | **$1.001501$** | $0.001501$ |
| $\to 0^+$ | $\to 1$ | $\to 0$ | **$\to 1.000000$** | $\to 0$ |
| $-0.001$ | $0.999001$ | $-0.000999$ | **$0.998501$** | $0.001499$ |
| $-0.01$ | $0.990149$ | $-0.009851$ | **$0.985116$** | $0.014884$ |
| $-0.1$ | $0.913886$ | $-0.086114$ | **$0.861142$** | $0.138858$ |

---

### Step 5: Why Convergence of $D(h)$ Is Consistent with the Derivative

- As $|h|$ decreases by factors of $10$ ($1 \to 0.1 \to 0.01 \to 0.001$), the deviation $|D(h) - 1|$ decreases by approximately the same factor of $10$ ($3.4 \to 0.16 \to 0.015 \to 0.0015$).
- From the left, $D(h)$ approaches $1$ from below ($0.861 \to 0.985 \to 0.9985 \to 1$).
- From the right, $D(h)$ approaches $1$ from above ($1.162 \to 1.015 \to 1.0015 \to 1$).
- This symmetric convergence toward the common number $1$ is completely consistent with the definition $f'(0) = \lim_{h \to 0} D(h) = 1$.

---

### Step 6: Why a Few Computations Do Not Replace a Limit Argument

Despite the numerical table providing compelling evidence, finite computations cannot replace a mathematical limit proof for several fundamental reasons:

1. **The Universal Quantifier $\forall h$ Cannot Be Tested by Sampling:**
   The definition requires that $|D(h) - L| < \varepsilon$ for **every single** $h \in (-\delta, \delta) \setminus \{0\}$. Testing three values ($h = 1, 0.1, 0.01$) checks only 3 points out of an uncountable infinity of points in any open interval.

2. **Vulnerability to High-Frequency Oscillation:**
   Consider the function:
   $$
   g(x) = (x^2 + 1)e^x + x^2 \sin\left(\frac{200\pi}{x}\right) \quad (x \neq 0), \qquad g(0) = 1
   $$
   At the sample points $h = 1, 0.1, 0.01$, the argument $\frac{200\pi}{h}$ is an exact integer multiple of $2\pi$, so the sine term is precisely zero:
   $$
   g(1) = f(1), \quad g(0.1) = f(0.1), \quad g(0.01) = f(0.01)
   $$
   An observer computing only these three values would obtain the **exact same table** as above. While $g$ happens to be differentiable at $0$ because of the $x^2$ factor, if the factor were $x$ instead:
   $$
   k(x) = (x^2 + 1)e^x + x \sin\left(\frac{200\pi}{x}\right)
   $$
   the table at $h = 10^{-n}$ would still be identical, yet $k(x)$ is **not differentiable at $x = 0$ at all**, because between the tested points the difference quotient oscillates wildly between $0$ and $2$. Finite sampling is completely blind to behavior between sample nodes.

3. **Catastrophic Cancellation in Floating-Point Arithmetic:**
   Numerical difference quotients on computers fail when $h$ becomes very small. In 64-bit IEEE 754 floating-point arithmetic:
   - For $h = 10^{-8}$, roundoff error equals truncation error.
   - For $h = 10^{-16}$, $f(0 + h) = f(0)$ due to machine precision limits, so $\frac{f(h) - f(0)}{h} = \frac{0}{10^{-16}} = 0$.
   A computer program computing difference quotients for arbitrarily small $h$ will eventually report that $f'(0) = 0$, an absurd falsehood.

4. **Exactness of Deduction:**
   The analytical derivative $f'(x) = (x + 1)^2 e^x$ is proven through deductive logic from the field axioms and order axioms of the real numbers. It establishes truth with certainty across the entire continuum, which empirical induction can never achieve.

---

## 4. Verification and Consistency Checks

1. **Theoretical Error Constant Verification:**
   Using the Taylor expansion derived in Section 2:
   $$
   D(h) = f'(0) + \frac{f''(0)}{2} h + \mathcal{O}(h^2)
   $$
   Let us compute $f''(0)$:
   $$
   f'(x) = (x^2 + 2x + 1)e^x \implies f''(x) = (2x + 2)e^x + (x^2 + 2x + 1)e^x = (x^2 + 4x + 3)e^x
   $$
   $$
   f''(0) = (0 + 0 + 3)e^0 = 3
   $$
   Therefore, the theoretical asymptotic difference quotient is:
   $$
   D(h) = 1 + \frac{3}{2}h + \mathcal{O}(h^2) = 1 + 1.5h + \mathcal{O}(h^2)
   $$
   - For $h = 0.1$: $D(0.1) \approx 1 + 1.5(0.1) = 1.15$ (Actual: $1.162$, error from higher terms $\approx 0.012$).
   - For $h = 0.01$: $D(0.01) \approx 1 + 1.5(0.01) = 1.015$ (Actual: $1.015117$).
   - For $h = -0.01$: $D(-0.01) \approx 1 - 1.5(0.01) = 0.985$ (Actual: $0.985116$).
   The computed difference quotients match the second-order Taylor prediction to extreme accuracy, confirming both the analytical derivative and the numerical computations.
