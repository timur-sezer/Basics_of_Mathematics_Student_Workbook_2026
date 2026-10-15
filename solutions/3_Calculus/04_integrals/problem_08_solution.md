# Solution to Problem 8: Choosing the Factors in Integration by Parts

## 1. Problem Statement

Compute the indefinite integral:
$$
\int x \cos x \, dx
$$

1. Prior to calculating, provide a rigorous mathematical justification for why it is advantageous to choose $u = x$ (differentiating $x$) and $dv = \cos x \, dx$ (integrating $\cos x$), rather than the reverse assignment.
2. Demonstrate what happens if the reverse assignment ($u = \cos x, dv = x \, dx$) is attempted.
3. Execute the integration by parts using the optimal choice of factors.
4. Simplify and express the complete family of antiderivatives.
5. Verify the result by differentiation, connecting this problem with Problem 6 from the Derivatives problem set.

---

## 2. Theoretical Background and Concepts

1. **The Integration by Parts Formula:**
   $$
   \int u \, dv = u v - \int v \, du
   $$

2. **The Criteria for Choosing $u$ and $dv$:**
   The goal of integration by parts is to make the secondary integral $\int v \, du$ strictly easier to evaluate than the original integral $\int u \, dv$.
   - **Polynomial / Algebraic factor ($x^n$):** Differentiating reduces the exponent by one ($n x^{n-1}$), eventually eliminating the variable. Integrating increases the exponent to $\frac{x^{n+1}}{n+1}$, worsening the algebraic complexity.
   - **Trigonometric / Exponential factor ($\cos x, \sin x, e^x$):** These functions are cyclically persistent under both differentiation and integration. Integrating $\cos x$ yields $\sin x$, which does not escalate in complexity.
   - **Strategic Rule:** Assign the polynomial to $u$ so that differentiation degrades its degree, and assign the cyclical function to $dv$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Comparison of Factor Assignments

Let us analyze both possible assignments to illustrate why factor selection is the decisive step:

#### Path A: The Optimal Assignment ($u = x, dv = \cos x \, dx$)
- $u = x \implies du = dx$ (the algebraic factor degrades from degree 1 to degree 0, becoming a constant).
- $dv = \cos x \, dx \implies v = \sin x$ (the trigonometric factor remains at the same level of complexity).
- The secondary integral is:
  $$
  \int v \, du = \int \sin x \, dx
  $$
  This is an elementary, standard integral with a known primitive ($-\cos x$).

#### Path B: The Inverted Assignment ($u = \cos x, dv = x \, dx$)
- $u = \cos x \implies du = -\sin x \, dx$.
- $dv = x \, dx \implies v = \int x \, dx = \frac{x^2}{2}$.
- The secondary integral becomes:
  $$
  \int v \, du = \int \left(\frac{x^2}{2}\right)(-\sin x \, dx) = -\frac{1}{2} \int x^2 \sin x \, dx
  $$
- **Diagnosis of Failure:** Instead of simplifying, the power of $x$ has **increased from $x^1$ to $x^2$**! The new integral is significantly harder and further from a solution than the original problem. This demonstrates that integration by parts must never be applied blindly.

---

### Step 2: Computation with the Optimal Choice

Using Path A:
$$
\begin{array}{r@{\quad=\quad}l@{\qquad}r@{\quad=\quad}l}
  u & x & v & \sin x \\
  du & dx & dv & \cos x \, dx
\end{array}
$$

Substitute into $\int u \, dv = u v - \int v \, du$:
$$
\int x \cos x \, dx = (x)(\sin x) - \int (\sin x)(dx)
$$

Evaluate the standard integral $\int \sin x \, dx = -\cos x$:
$$
\int x \cos x \, dx = x \sin x - (-\cos x) + C
$$

Simplify the signs:
$$
F(x) = x \sin x + \cos x + C
$$

---

### Step 3: Verification by Differentiation

Differentiate $F(x) = x \sin x + \cos x + C$ with respect to $x$:
$$
F'(x) = \frac{d}{dx}[x \sin x] + \frac{d}{dx}[\cos x] + \frac{d}{dx}[C]
$$

Apply the product rule to the first term:
$$
\frac{d}{dx}[x \sin x] = \frac{d}{dx}[x] \sin x + x \frac{d}{dx}[\sin x] = 1 \cdot \sin x + x \cos x = \sin x + x \cos x
$$
Differentiate the second and third terms:
$$
\frac{d}{dx}[\cos x] = -\sin x, \qquad \frac{d}{dx}[C] = 0
$$

Sum the components:
$$
F'(x) = (\sin x + x \cos x) - \sin x + 0
$$
$$
F'(x) = \sin x - \sin x + x \cos x = x \cos x
$$

The derivative matches the original integrand $x \cos x$ identically.

*(Remarkable Curriculum Connection)*:
In Problem 6 of the Derivatives problem set, the student was asked to differentiate $f(x) = x \sin x + \cos x$, discovering the cancellation that yielded $f'(x) = x \cos x$. Here in Problem 8 of Integrals, we invert that exact differentiation process via integration by parts, seamlessly uniting the two halves of calculus.

---

## 4. Verification and Consistency Checks

1. **Definite Integral on $\left[0, \frac{\pi}{2}\right]$:**
   Compute $\int_0^{\pi/2} x \cos x \, dx$:
   $$
   \int_0^{\pi/2} x \cos x \, dx = \Big[x \sin x + \cos x\Big]_0^{\pi/2}
   $$
   - At upper limit $x = \frac{\pi}{2}$:
     $$
     F\left(\frac{\pi}{2}\right) = \left(\frac{\pi}{2}\right)\sin\left(\frac{\pi}{2}\right) + \cos\left(\frac{\pi}{2}\right) = \frac{\pi}{2}(1) + 0 = \frac{\pi}{2} \approx 1.570796
     $$
   - At lower limit $x = 0$:
     $$
     F(0) = (0)\sin(0) + \cos(0) = 0 + 1 = 1
     $$
   - Net definite integral:
     $$
     I = \frac{\pi}{2} - 1 \approx 0.570796
     $$

2. **Numerical Midpoint Riemann Sum on $\left[0, \frac{\pi}{2}\right]$:**
   Let $n = 2$ intervals with width $\Delta x = \frac{\pi}{4} \approx 0.7854$:
   - Midpoints: $m_1 = \frac{\pi}{8} \approx 0.3927$, $m_2 = \frac{3\pi}{8} \approx 1.1781$.
   - $f(m_1) = \frac{\pi}{8} \cos(\pi/8) \approx 0.3927 \times 0.92388 \approx 0.36281$.
   - $f(m_2) = \frac{3\pi}{8} \cos(3\pi/8) \approx 1.1781 \times 0.38268 \approx 0.45084$.
   - Riemann sum:
     $$
     M_2 = (0.36281 + 0.45084) \times \frac{\pi}{4} = 0.81365 \times 0.7854 \approx 0.639
     $$
   With $n = 4$ intervals:
   - Midpoints: $\pi/16, 3\pi/16, 5\pi/16, 7\pi/16$.
   - Evaluated sum: $M_4 \approx 0.588 \approx 0.571$.
   The numerical Riemann sums converge directly to $\frac{\pi}{2} - 1$, verifying the solution.
