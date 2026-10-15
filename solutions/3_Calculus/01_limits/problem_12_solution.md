# Solution to Exercise 12: Exponential Function Limit

## 1. Problem Statement

Compute the limit of the function as $x \to 0$:
$$
\lim_{x \to 0} (1 + 3x)^{1/x}
$$

1. Connect the limit with the fundamental limit defining Euler's number $e$ from Exercise 5.
2. Show the algebraic substitution and exponent manipulation that reduces this limit to the standard form.
3. Determine the exact value of the limit.

---

## 2. Theoretical Background and Concepts

1. **The Fundamental Limit for $e$ in Continuous Form:**
   As established in Exercise 5, the discrete sequence limit is $\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e$.
   Making the substitution $u = \frac{1}{n}$, as $n \to \infty$, $u \to 0^+$.
   More generally, for any real variable approaching zero from either direction:
   $$
   \lim_{u \to 0} (1 + u)^{1/u} = e
   $$

2. **Exponentiation Power Rule for Limits:**
   If $\lim_{x \to c} f(x) = A > 0$ and $g(x)$ is continuous, then:
   $$
   \lim_{x \to c} [f(x)]^k = \left[\lim_{x \to c} f(x)\right]^k
   $$
   Specifically, if the exponent can be decomposed as $\frac{1}{x} = \frac{k}{u}$ where $u \to 0$, we can express the function as $\left[(1 + u)^{1/u}\right]^k$.

3. **Logarithmic Method:**
   Alternatively, using the natural logarithm and continuity of the exponential function:
   $$
   L = \lim_{x \to 0} (1 + 3x)^{1/x} \iff \ln L = \lim_{x \to 0} \ln\left((1 + 3x)^{1/x}\right) = \lim_{x \to 0} \frac{\ln(1 + 3x)}{x}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Indeterminate Form

Evaluate the base and the exponent as $x \to 0$:
- Base: $\lim_{x \to 0} (1 + 3x) = 1 + 0 = 1$
- Exponent: As $x \to 0$, $\frac{1}{x} \to \pm\infty$

The expression has the classical **indeterminate form $1^\infty$**.

---

### Step 2: Method A — Reduction to the Standard Base Form $(1 + u)^{1/u}$

We desire the base to contain a single additive variable $u$, with the exponent being the exact reciprocal $\frac{1}{u}$.

1. **Define the Substitution Variable:**
   Let:
   $$
   u = 3x
   $$
   As $x \to 0$, we have $u \to 0$.

2. **Express the Exponent $\frac{1}{x}$ in Terms of $u$:**
   Since $u = 3x$, we have $x = \frac{u}{3}$.
   Therefore:
   $$
   \frac{1}{x} = \frac{1}{u/3} = \frac{3}{u} = 3 \cdot \frac{1}{u}
   $$

3. **Rewrite the Expression:**
   $$
   (1 + 3x)^{1/x} = (1 + u)^{3/u} = \left[ (1 + u)^{1/u} \right]^3
   $$

4. **Evaluate the Limit:**
   Since the outer power function $t \mapsto t^3$ is continuous for all $t \in \mathbb{R}$:
   $$
   \lim_{x \to 0} (1 + 3x)^{1/x} = \lim_{u \to 0} \left[ (1 + u)^{1/u} \right]^3 = \left[ \lim_{u \to 0} (1 + u)^{1/u} \right]^3
   $$
   By the fundamental limit $\lim_{u \to 0} (1 + u)^{1/u} = e$:
   $$
   = e^3
   $$

Thus, the exact value is:
$$
\lim_{x \to 0} (1 + 3x)^{1/x} = e^3 \approx 20.085537
$$

---

### Step 3: Method B — The Natural Logarithm Transformation

1. Let $y = (1 + 3x)^{1/x}$.
2. Take the natural logarithm of both sides:
   $$
   \ln y = \ln\left((1 + 3x)^{1/x}\right) = \frac{1}{x} \ln(1 + 3x) = \frac{\ln(1 + 3x)}{x}
   $$
3. Multiply and divide by $3$ to match the argument:
   $$
   \ln y = 3 \cdot \frac{\ln(1 + 3x)}{3x}
   $$
4. Use the standard logarithmic limit $\lim_{u \to 0} \frac{\ln(1 + u)}{u} = 1$ with $u = 3x$:
   $$
   \lim_{x \to 0} \ln y = 3 \lim_{u \to 0} \frac{\ln(1 + u)}{u} = 3 \cdot 1 = 3
   $$
5. Exponentiate back to recover the limit:
   $$
   \lim_{x \to 0} y = e^{\lim_{x \to 0} \ln y} = e^3 \quad (\checkmark)
   $$

Both methods yield the exact same result $e^3$.

---

## 4. Verification and Consistency Checks

1. **Numerical Evaluation of Approaching Values:**

| Approaching from Left ($x < 0$) | Value $(1 + 3x)^{1/x}$ | Approaching from Right ($x > 0$) | Value $(1 + 3x)^{1/x}$ |
| :---: | :---: | :---: | :---: |
| $x = -0.1$ | $(1 - 0.3)^{-10} = (0.7)^{-10} \approx 35.40$ | $x = 0.1$ | $(1 + 0.3)^{10} = (1.3)^{10} \approx 13.79$ |
| $x = -0.01$ | $(0.97)^{-100} \approx 20.938$ | $x = 0.01$ | $(1.03)^{100} \approx 19.219$ |
| $x = -0.001$ | $(0.997)^{-1000} \approx 20.169$ | $x = 0.001$ | $(1.003)^{1000} \approx 20.024$ |
| $x = -0.0001$ | $(0.9997)^{-10000} \approx 20.094$ | $x = 0.0001$ | $(1.0003)^{10000} \approx 20.077$ |
| $x \to 0^-$ | $\to 20.0855$ | $x \to 0^+$ | $\to 20.0855$ |

The numerical values approach $e^3 \approx 20.085537$ symmetrically from both sides.

2. **General Formula Check:**
   For any constants $a, b \in \mathbb{R}$:
   $$
   \lim_{x \to 0} (1 + ax)^{b/x} = e^{ab}
   $$
   Setting $a = 3$ and $b = 1$ immediately gives $e^{3 \cdot 1} = e^3 \quad (\checkmark)$.
