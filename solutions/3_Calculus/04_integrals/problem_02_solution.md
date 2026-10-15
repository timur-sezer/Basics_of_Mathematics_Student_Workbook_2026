# Solution to Problem 2: Powers, Roots, and the Domain

## 1. Problem Statement

Compute the indefinite integral:
$$
\int \left(2\sqrt{x} + \frac{3}{x^2} - x^{1/3}\right) \, dx
$$

1. Rewrite each term of the integrand as a power of $x$ in the form $a x^\alpha$.
2. Determine the maximal domain of definition $\mathcal{D}_f$ of the integrand in the real numbers.
3. Compute the antiderivative using the generalized power rule for integration.
4. Verify the result by differentiation on $\mathcal{D}_f$.

---

## 2. Theoretical Background and Concepts

1. **Exponent Conversion:**
   For $x > 0$:
   - $\sqrt{x} = x^{1/2}$
   - $\frac{1}{x^n} = x^{-n}$, so $\frac{3}{x^2} = 3x^{-2}$
   - $\sqrt[3]{x} = x^{1/3}$

2. **The Generalized Power Rule for Integration:**
   For any real constant $\alpha \neq -1$:
   $$
   \int x^\alpha \, dx = \frac{x^{\alpha + 1}}{\alpha + 1} + C
   $$

3. **Domain Constraints and Antiderivatives:**
   An antiderivative exists only on the intervals where the integrand is defined and continuous.
   - Even radicals ($\sqrt{x} = x^{1/2}$) require non-negative radicands: $x \ge 0$.
   - Denominators ($\frac{3}{x^2}$) cannot be zero: $x \neq 0$.
   - The domain of the sum is the intersection of the domains of the individual components.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Rewrite the Integrand Using Exponents

Convert each term to standard power notation $x^\alpha$:
1. $2\sqrt{x} = 2x^{1/2}$
2. $\frac{3}{x^2} = 3x^{-2}$
3. $-x^{1/3} = -x^{1/3}$

The integral is rewritten as:
$$
\int \left(2x^{1/2} + 3x^{-2} - x^{1/3}\right) \, dx
$$

---

### Step 2: Determine the Domain $\mathcal{D}_f$

We inspect the domain of each term:
- **Term 1 ($2\sqrt{x}$):** The square root requires $x \ge 0$. Domain: $[0, \infty)$.
- **Term 2 ($\frac{3}{x^2}$):** The denominator requires $x^2 \neq 0 \iff x \neq 0$. Domain: $\mathbb{R} \setminus \{0\}$.
- **Term 3 ($-x^{1/3}$):** Cube root is defined for all $x \in \mathbb{R}$. Domain: $(-\infty, \infty)$.

Taking the intersection of all three requirements:
$$
\mathcal{D}_f = [0, \infty) \cap (\mathbb{R} \setminus \{0\}) \cap \mathbb{R} = (0, \infty)
$$
In inequality notation:
$$
\mathcal{D}_f = \{x \in \mathbb{R} : x > 0\}
$$

---

### Step 3: Compute the Indefinite Integral

Apply the power rule $\int x^\alpha \, dx = \frac{x^{\alpha + 1}}{\alpha + 1}$ to each term:

1. **First Term:**
   $$
   \int 2x^{1/2} \, dx = 2 \cdot \frac{x^{\frac{1}{2} + 1}}{\frac{1}{2} + 1} = 2 \cdot \frac{x^{3/2}}{3/2} = 2 \cdot \left(\frac{2}{3}\right) x^{3/2} = \frac{4}{3} x^{3/2}
   $$

2. **Second Term:**
   $$
   \int 3x^{-2} \, dx = 3 \cdot \frac{x^{-2 + 1}}{-2 + 1} = 3 \cdot \frac{x^{-1}}{-1} = -3x^{-1} = -\frac{3}{x}
   $$

3. **Third Term:**
   $$
   \int -x^{1/3} \, dx = -\frac{x^{\frac{1}{3} + 1}}{\frac{1}{3} + 1} = -\frac{x^{4/3}}{4/3} = -\left(\frac{3}{4}\right) x^{4/3} = -\frac{3}{4} x^{4/3}
   $$

Combining the three results and appending the arbitrary constant of integration $C$:
$$
F(x) = \frac{4}{3} x^{3/2} - 3x^{-1} - \frac{3}{4} x^{4/3} + C
$$

In radical notation:
$$
F(x) = \frac{4}{3} x\sqrt{x} - \frac{3}{x} - \frac{3}{4} x\sqrt[3]{x} + C \qquad \text{for } x \in (0, \infty)
$$

---

### Step 4: Verification by Differentiation

Differentiate $F(x) = \frac{4}{3}x^{3/2} - 3x^{-1} - \frac{3}{4}x^{4/3} + C$ using the power rule for derivatives:
$$
F'(x) = \frac{4}{3} \frac{d}{dx}[x^{3/2}] - 3 \frac{d}{dx}[x^{-1}] - \frac{3}{4} \frac{d}{dx}[x^{4/3}] + \frac{d}{dx}[C]
$$

Compute the individual derivatives:
- $\frac{4}{3} \cdot \left(\frac{3}{2} x^{\frac{3}{2} - 1}\right) = \frac{4}{3} \cdot \frac{3}{2} x^{1/2} = 2x^{1/2} = 2\sqrt{x}$
- $-3 \cdot \left(-1 x^{-1 - 1}\right) = -3(-x^{-2}) = +3x^{-2} = \frac{3}{x^2}$
- $-\frac{3}{4} \cdot \left(\frac{4}{3} x^{\frac{4}{3} - 1}\right) = -\frac{3}{4} \cdot \frac{4}{3} x^{1/3} = -x^{1/3}$
- $\frac{d}{dx}[C] = 0$

Summing the results:
$$
F'(x) = 2\sqrt{x} + \frac{3}{x^2} - x^{1/3} = f(x)
$$
The derivative matches the original integrand identically on $(0, \infty)$.

---

## 4. Verification and Consistency Checks

1. **Definite Integral Evaluation on $[1, 4]$:**
   Evaluate $\int_1^4 \left(2\sqrt{x} + \frac{3}{x^2} - x^{1/3}\right) \, dx$ using the antiderivative with $C = 0$:
   - At $x = 4$:
     $$
     F(4) = \frac{4}{3}(4^{3/2}) - \frac{3}{4} - \frac{3}{4}(4^{4/3}) = \frac{4}{3}(8) - \frac{3}{4} - \frac{3}{4}(4\sqrt[3]{4}) = \frac{32}{3} - \frac{3}{4} - 3\sqrt[3]{4} = \frac{119}{12} - 3\sqrt[3]{4} \approx 9.9167 - 4.7622 = 5.1545
     $$
   - At $x = 1$:
     $$
     F(1) = \frac{4}{3}(1) - \frac{3}{1} - \frac{3}{4}(1) = \frac{4}{3} - 3 - \frac{3}{4} = \frac{16 - 36 - 9}{12} = -\frac{29}{12} \approx -2.4167
     $$
   - Definite integral value:
     $$
     F(4) - F(1) = \left(\frac{119}{12} - 3\sqrt[3]{4}\right) - \left(-\frac{29}{12}\right) = \frac{148}{12} - 3\sqrt[3]{4} = \frac{37}{3} - 3\sqrt[3]{4} \approx 12.3333 - 4.7622 = 7.5711
     $$

2. **Numerical Midpoint Sanity Check on $[1, 4]$:**
   Use 3 subintervals $[1, 2], [2, 3], [3, 4]$ with $\Delta x = 1$:
   - Midpoints: $1.5, 2.5, 3.5$.
   - $f(1.5) = 2\sqrt{1.5} + 3/(1.5)^2 - (1.5)^{1/3} \approx 2(1.2247) + 1.3333 - 1.1447 = 2.4495 + 1.3333 - 1.1447 = 2.6381$.
   - $f(2.5) = 2\sqrt{2.5} + 3/(2.5)^2 - (2.5)^{1/3} \approx 2(1.5811) + 0.48 - 1.3572 = 3.1623 + 0.48 - 1.3572 = 2.2851$.
   - $f(3.5) = 2\sqrt{3.5} + 3/(3.5)^2 - (3.5)^{1/3} \approx 2(1.8708) + 0.2449 - 1.5183 = 3.7417 + 0.2449 - 1.5183 = 2.4683$.
   - Approximate sum:
     $$
     (2.6381 + 2.2851 + 2.4683) \times 1 = 7.3915 \approx 7.57
     $$
   The Riemann sum closely approximates the exact result $7.5711$, verifying the antiderivative.
