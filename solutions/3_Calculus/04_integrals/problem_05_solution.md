# Solution to Problem 5: The Same Substitution in a Different Context

## 1. Problem Statement

Compute the indefinite integral:
$$
\int x e^{x^2} \, dx
$$

1. Compare the mathematical structure of this integrand with the integrand from Problem 4 ($\int 2x(x^2 + 1)^4 \, dx$).
2. Explain what fundamental structural property they share despite belonging to different families of functions (algebraic power vs. transcendental exponential).
3. Execute the substitution and compute the exact antiderivative.
4. Verify the result by differentiation.

---

## 2. Theoretical Background and Concepts

1. **Structural Pattern Recognition in Substitution:**
   The technique of $u$-substitution does not depend on the specific transcendental or algebraic nature of the outer function $f$. It depends strictly on the **relational structure**:
   $$
   \int f(g(x)) \cdot g'(x) \, dx
   $$
   Whenever the integrand contains an inner expression $g(x)$ whose derivative $g'(x)$ appears as a factor multiplying $dx$ (up to an allowable non-zero constant multiple), substitution is applicable:
   $$
   u = g(x) \implies du = g'(x) \, dx
   $$

2. **Constant Factor Adjustment:**
   If the differential inside the integrand differs from $du$ by a non-zero multiplicative constant $k \neq 0$:
   $$
   g'(x) \, dx = \frac{1}{k} du
   $$
   By the linearity of integration, constant factors can be factored outside the integral:
   $$
   \int f(g(x)) \cdot \left(\frac{1}{k} g'(x)\right) dx = \frac{1}{k} \int f(u) \, du
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Structural Comparison with Problem 4

Let us place the two integrands side-by-side:

| Problem | Integrand | Inner Function $g(x)$ | Derivative $g'(x)$ | Outer Function $f(u)$ |
|:---|:---|:---:|:---:|:---:|
| **Problem 4** | $2x(x^2 + 1)^4$ | $u = x^2 + 1$ | $2x$ | Power: $f(u) = u^4$ |
| **Problem 5** | $x e^{x^2}$ | $u = x^2$ | $2x$ | Exponential: $f(u) = e^u$ |

**What is Common:**
1. In both problems, the inner function is a **quadratic polynomial in $x$** ($x^2$ or $x^2 + 1$).
2. In both problems, the derivative of the quadratic argument is a **linear monomial** ($2x$).
3. In both problems, a linear factor of $x$ is present outside the composite function, ready to form the differential $du$.
4. The difference between the two problems is purely cosmetic: the outer envelope changes from a 4th-power polynomial to a natural exponential, and Problem 5 is missing the constant factor of $2$, which is effortlessly accommodated by dividing $du$ by $2$.

---

### Step 2: Set Up the Substitution

Let the new variable be the quadratic exponent:
$$
u = x^2
$$

Differentiate to find the differential $du$:
$$
du = \frac{d}{dx}[x^2] \, dx = 2x \, dx
$$

Solve for the factor $x \, dx$ appearing in the integral:
$$
x \, dx = \frac{1}{2} du
$$

---

### Step 3: Transform and Evaluate the Integral

Substitute $x^2 = u$ and $x \, dx = \frac{1}{2} du$:
$$
\int x e^{x^2} \, dx = \int e^{x^2} \cdot (x \, dx) = \int e^u \cdot \left(\frac{1}{2} du\right)
$$

Factor out the constant factor $\frac{1}{2}$:
$$
= \frac{1}{2} \int e^u \, du
$$

Since the natural exponential function is its own antiderivative ($\int e^u \, du = e^u + C$):
$$
= \frac{1}{2} e^u + C
$$

---

### Step 4: Back-Substitution

Replace $u$ with $x^2$:
$$
F(x) = \frac{1}{2} e^{x^2} + C
$$

Thus:
$$
\int x e^{x^2} \, dx = \frac{1}{2} e^{x^2} + C
$$

---

### Step 5: Verification by Differentiation

Differentiate the resulting antiderivative using the chain rule:
$$
F'(x) = \frac{d}{dx}\left[\frac{1}{2} e^{x^2} + C\right] = \frac{1}{2} \frac{d}{dx}[e^{x^2}] + 0
$$

Using $\frac{d}{dx}[e^{u(x)}] = e^{u(x)} \cdot u'(x)$:
$$
F'(x) = \frac{1}{2} \cdot \left(e^{x^2} \cdot \frac{d}{dx}[x^2]\right) = \frac{1}{2} \cdot e^{x^2} \cdot (2x)
$$
Cancel the factor of $2$:
$$
F'(x) = x e^{x^2}
$$
The derivative exactly recovers the original integrand $f(x)$.

---

## 4. Verification and Consistency Checks

1. **Definite Integral Evaluation on $[0, \sqrt{\ln 2}]$:**
   - **Using $F(x)$:**
     $$
     \int_0^{\sqrt{\ln 2}} x e^{x^2} \, dx = \left[\frac{1}{2} e^{x^2}\right]_0^{\sqrt{\ln 2}} = \frac{1}{2} e^{(\sqrt{\ln 2})^2} - \frac{1}{2} e^0 = \frac{1}{2} e^{\ln 2} - \frac{1}{2}(1) = \frac{1}{2}(2) - \frac{1}{2} = 1 - 0.5 = 0.5
     $$
   - **Using $u$-limits:**
     - Lower limit: $u(0) = 0^2 = 0$.
     - Upper limit: $u(\sqrt{\ln 2}) = (\sqrt{\ln 2})^2 = \ln 2$.
     $$
     \frac{1}{2} \int_0^{\ln 2} e^u \, du = \frac{1}{2} [e^u]_0^{\ln 2} = \frac{1}{2}(e^{\ln 2} - e^0) = \frac{1}{2}(2 - 1) = 0.5
     $$
   Both methods yield $0.5$ identically.

2. **Taylor Series Integration Verification:**
   Expand the integrand in Maclaurin series:
   $$
   e^{x^2} = 1 + x^2 + \frac{x^4}{2} + \frac{x^6}{6} + \dots
   $$
   Multiply by $x$:
   $$
   x e^{x^2} = x + x^3 + \frac{x^5}{2} + \frac{x^7}{6} + \dots
   $$
   Integrate term-by-term:
   $$
   \int x e^{x^2} \, dx = \frac{x^2}{2} + \frac{x^4}{4} + \frac{x^6}{12} + \frac{x^8}{48} + \dots + C
   $$
   Now expand our solution $\frac{1}{2}e^{x^2}$:
   $$
   \frac{1}{2} e^{x^2} = \frac{1}{2}\left(1 + x^2 + \frac{x^4}{2} + \frac{x^6}{6} + \dots\right) = \frac{1}{2} + \frac{x^2}{2} + \frac{x^4}{4} + \frac{x^6}{12} + \dots
   $$
   Absorbing the constant $\frac{1}{2}$ into $C$, the power series match term-by-term, confirming total analytical correctness.
