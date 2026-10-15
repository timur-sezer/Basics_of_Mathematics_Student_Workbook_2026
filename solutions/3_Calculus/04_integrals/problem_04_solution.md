# Solution to Problem 4: Substitution as Reversing the Chain Rule

## 1. Problem Statement

Compute the indefinite integral:
$$
\int 2x(x^2 + 1)^4 \, dx
$$

1. Identify a suitable candidate for the substitution variable $u = g(x)$.
2. Compute the differential $du = g'(x) \, dx$ and show that this derivative factor is already present in the integrand.
3. Transform the integral into an elementary power integral in terms of $u$ and compute the antiderivative.
4. Back-substitute $u$ to express the final result in terms of $x$.
5. Verify the result by differentiation, demonstrating explicitly how substitution reverses the chain rule.

---

## 2. Theoretical Background and Concepts

1. **The Chain Rule in Differentiation:**
   If $F(u)$ is an antiderivative of $f(u)$ ($F'(u) = f(u)$), and $u = g(x)$ is a differentiable inner function, then by the chain rule:
   $$
   \frac{d}{dx}[F(g(x))] = F'(g(x)) \cdot g'(x) = f(g(x)) \cdot g'(x)
   $$

2. **Integration by Substitution:**
   Integrating both sides of the chain rule identity yields:
   $$
   \int f(g(x)) \cdot g'(x) \, dx = F(g(x)) + C
   $$
   By setting $u = g(x)$ and $du = g'(x) \, dx$, the integral collapses into:
   $$
   \int f(u) \, du = F(u) + C
   $$
   Substitution is therefore the exact operational inverse of the chain rule.

3. **Recognition Strategy for Substitution:**
   Look for an integrand that can be factored into:
   $$\underbrace{f(g(x))}_{\text{outer}(\text{inner})} \times \underbrace{g'(x) \, dx}_{\text{inner derivative}}$$
   When the derivative of the inside function appears as a multiplicative factor in the differential, substitution simplifies the problem immediately.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Substitution Variable

Examine the structure of the integrand:
$$
\int (x^2 + 1)^4 \cdot (2x) \, dx
$$
- The composite part is $(x^2 + 1)^4$, which is an outer 4th power applied to the inner quadratic base $x^2 + 1$.
- Let the candidate for the new variable be the inner base:
  $$
  u = x^2 + 1
  $$

---

### Step 2: Compute the Differential $du$

Differentiate $u$ with respect to $x$:
$$
\frac{du}{dx} = \frac{d}{dx}[x^2 + 1] = 2x
$$
In differential form:
$$
du = 2x \, dx
$$

Observe that the expression $2x \, dx$ appears **identically and exactly** in the integrand. There is no need for coefficient adjustments.

---

### Step 3: Transform and Evaluate the Integral in $u$

Substitute $x^2 + 1 = u$ and $2x \, dx = du$:
$$
\int 2x(x^2 + 1)^4 \, dx = \int (x^2 + 1)^4 \cdot (2x \, dx) = \int u^4 \, du
$$

Apply the basic power rule for integration:
$$
\int u^4 \, du = \frac{u^{4+1}}{4 + 1} + C = \frac{u^5}{5} + C = \frac{1}{5}u^5 + C
$$

---

### Step 4: Back-Substitution

Replace $u$ with its original definition in terms of $x$, $u = x^2 + 1$:
$$
F(x) = \frac{1}{5}(x^2 + 1)^5 + C
$$

---

### Step 5: Verification by Differentiation (Reversing the Process)

To verify the antiderivative, differentiate $F(x) = \frac{1}{5}(x^2 + 1)^5 + C$ using the chain rule:
$$
F'(x) = \frac{d}{dx}\left[\frac{1}{5}(x^2 + 1)^5 + C\right] = \frac{1}{5} \frac{d}{dx}\left[(x^2 + 1)^5\right] + 0
$$

Applying the chain rule (outer derivative times inner derivative):
- Outer derivative with respect to base: $5(x^2 + 1)^4$
- Inner derivative of base: $\frac{d}{dx}[x^2 + 1] = 2x$

Multiplying together:
$$
F'(x) = \frac{1}{5} \cdot \Big[5(x^2 + 1)^4\Big] \cdot (2x) = 1 \cdot (x^2 + 1)^4 \cdot (2x) = 2x(x^2 + 1)^4
$$

The result matches the original integrand $f(x) = 2x(x^2 + 1)^4$ identically.

---

## 4. Verification and Consistency Checks

1. **Definite Integral Evaluation on $[0, 1]$:**
   Evaluate the definite integral via both variable domains:
   - **In terms of $x$ (using $F(x)$):**
     $$
     \int_0^1 2x(x^2 + 1)^4 \, dx = \left[\frac{1}{5}(x^2 + 1)^5\right]_0^1 = \frac{1}{5}(1^2 + 1)^5 - \frac{1}{5}(0^2 + 1)^5 = \frac{1}{5}(2^5) - \frac{1}{5}(1^5) = \frac{32 - 1}{5} = \frac{31}{5} = 6.2
     $$
   - **In terms of $u$ (transforming limits of integration):**
     - When $x = 0$: $u(0) = 0^2 + 1 = 1$.
     - When $x = 1$: $u(1) = 1^2 + 1 = 2$.
     $$
     \int_1^2 u^4 \, du = \left[\frac{u^5}{5}\right]_1^2 = \frac{2^5 - 1^5}{5} = \frac{32 - 1}{5} = \frac{31}{5} = 6.2
     $$
   Both calculations yield exactly $6.2$, verifying the substitution limits and antiderivative.

2. **Expansion Verification (Alternative Brute-Force Method):**
   Using the binomial theorem:
   $$
   (x^2 + 1)^4 = x^8 + 4x^6 + 6x^4 + 4x^2 + 1
   $$
   Multiplying by $2x$:
   $$
   2x(x^2 + 1)^4 = 2x^9 + 8x^7 + 12x^5 + 8x^3 + 2x
   $$
   Integrating term-by-term:
   $$
   \int (2x^9 + 8x^7 + 12x^5 + 8x^3 + 2x) \, dx = \frac{2x^{10}}{10} + \frac{8x^8}{8} + \frac{12x^6}{6} + \frac{8x^4}{4} + \frac{2x^2}{2} + C
   $$
   $$
   = \frac{1}{5}x^{10} + x^8 + 2x^6 + 2x^4 + x^2 + C
   $$
   Now expand our substitution solution $\frac{1}{5}(x^2 + 1)^5$:
   $$
   \frac{1}{5}(x^2 + 1)^5 = \frac{1}{5}\left(x^{10} + 5x^8 + 10x^6 + 10x^4 + 5x^2 + 1\right) = \frac{1}{5}x^{10} + x^8 + 2x^6 + 2x^4 + x^2 + \frac{1}{5}
   $$
   Absorbing the constant $\frac{1}{5}$ into $C$, the two polynomials are identical! This proves how substitution avoids expanding high-degree polynomials.
