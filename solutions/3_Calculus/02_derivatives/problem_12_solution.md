# Solution to Problem 12: Several Rules at Once

## 1. Problem Statement

Given the function:
$$
f(x) = (x^2 + 1)^3 e^x
$$

1. Formulate a strategic plan before calculating: explicitly specify which differentiation rule applies to the overall expression and which rule applies internally to individual factors.
2. Compute the derivative $f'(x)$ following this strategic plan.
3. Systematically factor out all common factors to organize and simplify the final result.

---

## 2. Theoretical Background and Concepts

1. **Hierarchy and Order of Differentiation Operations:**
   When an algebraic expression combines multiple mathematical operations (products, powers, quotients, compositions), differentiation must proceed from the **outermost algebraic operation** inward:
   - Identify the top-level operation connecting the major parts of the expression.
   - Apply the corresponding master rule (e.g., Product Rule).
   - In the sub-steps where individual factors are differentiated, invoke secondary rules (e.g., Chain Rule, Power Rule) as needed.

2. **The Product Rule:**
   $$
   \frac{d}{dx}[u(x) v(x)] = u'(x) v(x) + u(x) v'(x)
   $$

3. **The Chain Rule (Power of a Function):**
   For a composite power $[w(x)]^n$:
   $$
   \frac{d}{dx}\left[[w(x)]^n\right] = n [w(x)]^{n-1} \cdot w'(x)
   $$

4. **Factoring Strategy for Composite Exponential Products:**
   Products involving powers and $e^x$ consistently produce expressions with common factors of the form $[w(x)]^{n-1} e^x$. Factoring these immediately prevents tedious polynomial expansion and cleanly reveals the critical points.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Strategic Plan

1. **Global (Master) Rule:**
   The entire expression is structured as a product:
   $$
   f(x) = u(x) \cdot v(x)
   $$
   where:
   - Factor 1: $u(x) = (x^2 + 1)^3$
   - Factor 2: $v(x) = e^x$
   Therefore, the **Product Rule** governs the overall expression.

2. **Local (Subsidiary) Rule:**
   To compute the derivative of the first factor $u(x) = (x^2 + 1)^3$, we observe that it is a composite function: an outer cube applied to an inner quadratic $w(x) = x^2 + 1$.
   Therefore, the **Chain Rule (Generalized Power Rule)** must be applied to differentiate $u(x)$.

3. **Exponential Rule:**
   The second factor $v(x) = e^x$ differentiates to itself: $v'(x) = e^x$.

---

### Step 2: Differentiate the Individual Factors

1. **Differentiate $u(x) = (x^2 + 1)^3$ via the Chain Rule:**
   - Outer function: $g(w) = w^3 \implies g'(w) = 3w^2$
   - Inner function: $w(x) = x^2 + 1 \implies w'(x) = 2x$
   Combining via the chain rule:
   $$
   u'(x) = 3(x^2 + 1)^2 \cdot \frac{d}{dx}[x^2 + 1] = 3(x^2 + 1)^2 \cdot (2x) = 6x(x^2 + 1)^2
   $$

2. **Differentiate $v(x) = e^x$:**
   $$
   v'(x) = e^x
   $$

---

### Step 3: Combine Using the Product Rule

Substitute $u, u', v, v'$ into the product rule $(uv)' = u'v + uv'$:
$$
f'(x) = \left[6x(x^2 + 1)^2\right] e^x + \left[(x^2 + 1)^3\right] e^x
$$

---

### Step 4: Organize and Factor Out Common Factors

Examine both additive terms:
- Term 1: $6x \cdot \mathbf{(x^2 + 1)^2} \cdot \mathbf{e^x}$
- Term 2: $(x^2 + 1) \cdot \mathbf{(x^2 + 1)^2} \cdot \mathbf{e^x}$

1. Factor out the common factors $(x^2 + 1)^2$ and $e^x$:
   $$
   f'(x) = (x^2 + 1)^2 e^x \cdot \Big[ 6x + (x^2 + 1) \Big]
   $$
2. Combine and arrange the remaining polynomial in descending powers of $x$:
   $$
   6x + x^2 + 1 = x^2 + 6x + 1
   $$
3. Write the fully factored, simplified derivative:
   $$
   f'(x) = (x^2 + 1)^2 (x^2 + 6x + 1) e^x
   $$

---

## 4. Verification and Consistency Checks

1. **Critical Points Analysis:**
   The zeros of $f'(x)$ are obtained by setting $f'(x) = 0$:
   $$
   (x^2 + 1)^2 (x^2 + 6x + 1) e^x = 0
   $$
   - $e^x > 0$ for all $x \in \mathbb{R}$ (never zero).
   - $x^2 + 1 \ge 1 > 0$ for all $x \in \mathbb{R}$ (never zero in real numbers).
   - The only real roots come from the quadratic $x^2 + 6x + 1 = 0$:
     $$
     x = \frac{-6 \pm \sqrt{6^2 - 4(1)(1)}}{2} = \frac{-6 \pm \sqrt{32}}{2} = -3 \pm 2\sqrt{2}
     $$
     $$
     x_1 = -3 - 2\sqrt{2} \approx -5.828, \qquad x_2 = -3 + 2\sqrt{2} \approx -0.172
     $$
   Having the derivative in factored form allows instantaneous determination of critical points and signs.

2. **Value Check at $x = 0$:**
   - From original function:
     $$
     f(0) = (0^2 + 1)^3 e^0 = 1^3 \cdot 1 = 1
     $$
   - From factored derivative:
     $$
     f'(0) = (0^2 + 1)^2 (0^2 + 6(0) + 1) e^0 = (1)^2 \cdot (1) \cdot 1 = 1
     $$
   - Direct Taylor verification near $0$:
     $$
     (x^2 + 1)^3 = 1 + 3x^2 + \dots
     $$
     $$
     e^x = 1 + x + \frac{x^2}{2} + \dots
     $$
     $$
     f(x) = (1 + 3x^2 + \dots)(1 + x + \dots) = 1 + x + \mathcal{O}(x^2)
     $$
     The coefficient of $x$ is $1$, confirming $f'(0) = 1$.

3. **Value Check at $x = 1$:**
   - From formula:
     $$
     f'(1) = (1^2 + 1)^2 (1^2 + 6(1) + 1) e^1 = (2)^2 \cdot (8) \cdot e = 4 \cdot 8 \cdot e = 32e \approx 86.983
     $$
   - Unfactored form:
     $$
     u'(1)v(1) + u(1)v'(1) = 6(1)(2)^2 e + (2)^3 e = 24e + 8e = 32e
     $$
   Both expressions give exactly $32e$, confirming algebraic consistency.
