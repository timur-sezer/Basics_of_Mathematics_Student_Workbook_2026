# Solution to Problem 2: Powers, Roots, and the Domain

## 1. Problem Statement

Given the function:
$$
f(x) = 2\sqrt{x} - \frac{3}{x^2} + x^{3/2}
$$

1. Rewrite the function using rational and negative exponents (powers of $x$).
2. Determine the maximal domain of definition $\mathcal{D}_f$.
3. Compute the derivative $f'(x)$ using the power rule.
4. Determine the domain of the derivative $\mathcal{D}_{f'}$ and compare it with $\mathcal{D}_f$.

---

## 2. Theoretical Background and Concepts

1. **Exponent Rules for Radicals and Reciprocals:**
   For real $x > 0$:
   - $\sqrt[m]{x^k} = x^{k/m}$, so $\sqrt{x} = x^{1/2}$ and $x^{3/2} = \sqrt{x^3} = (\sqrt{x})^3$.
   - $\frac{1}{x^k} = x^{-k}$, so $\frac{1}{x^2} = x^{-2}$.

2. **Domain of Functions Involving Radicals and Denominators:**
   - Even roots (such as square roots $\sqrt{x}$) require a non-negative radicand: $x \ge 0$.
   - Fractional exponents with even denominators ($x^{1/2}, x^{3/2}$) are defined for $x \ge 0$ in the real numbers.
   - Denominators must never be zero: $\frac{1}{x^2} \implies x \neq 0$.
   - The domain of a sum of functions is the intersection of their individual domains.

3. **Generalized Power Rule:**
   For any real exponent $\alpha \in \mathbb{R}$:
   $$
   \frac{d}{dx}[x^\alpha] = \alpha x^{\alpha - 1} \quad \text{for } x > 0
   $$

4. **Relationship Between $\mathcal{D}_f$ and $\mathcal{D}_{f'}$:**
   A function can only be differentiable where it is defined, so $\mathcal{D}_{f'} \subseteq \mathcal{D}_f$. Furthermore, boundary points or points with vertical tangents where the difference quotient blows up to $\pm \infty$ (such as $x = 0$ for $\sqrt{x}$) are excluded from $\mathcal{D}_{f'}$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Rewrite $f(x)$ Using Powers

We express each term in the standard form $a x^\alpha$:
1. $2\sqrt{x} = 2 x^{1/2}$
2. $-\frac{3}{x^2} = -3 x^{-2}$
3. $x^{3/2}$ is already in power form: $x^{3/2}$

Combining the terms:
$$
f(x) = 2x^{1/2} - 3x^{-2} + x^{3/2}
$$

---

### Step 2: Determine the Domain $\mathcal{D}_f$

We analyze the conditions required for each individual term in the real numbers $\mathbb{R}$:
- **Term 1 ($2\sqrt{x} = 2x^{1/2}$):** The square root requires $x \ge 0$. Domain: $[0, \infty)$.
- **Term 2 ($-\frac{3}{x^2} = -3x^{-2}$):** The denominator cannot be zero: $x^2 \neq 0 \iff x \neq 0$. Domain: $\mathbb{R} \setminus \{0\} = (-\infty, 0) \cup (0, \infty)$.
- **Term 3 ($x^{3/2}$):** Equivalent to $(\sqrt{x})^3$, requiring $x \ge 0$. Domain: $[0, \infty)$.

The domain of $f$ is the intersection of these sets:
$$
\mathcal{D}_f = [0, \infty) \cap (\mathbb{R} \setminus \{0\}) \cap [0, \infty) = (0, \infty)
$$

In inequality notation:
$$
\mathcal{D}_f = \{x \in \mathbb{R} : x > 0\}
$$

---

### Step 3: Compute the Derivative $f'(x)$

Applying linearity and the power rule $\frac{d}{dx}[x^\alpha] = \alpha x^{\alpha - 1}$:
$$
f'(x) = 2 \frac{d}{dx}[x^{1/2}] - 3 \frac{d}{dx}[x^{-2}] + \frac{d}{dx}[x^{3/2}]
$$

Differentiating each term:
- First term:
  $$
  2 \cdot \left(\frac{1}{2} x^{\frac{1}{2} - 1}\right) = 2 \cdot \frac{1}{2} x^{-1/2} = x^{-1/2} = \frac{1}{\sqrt{x}}
  $$
- Second term:
  $$
  -3 \cdot \left(-2 x^{-2 - 1}\right) = -3 \cdot (-2) x^{-3} = 6x^{-3} = \frac{6}{x^3}
  $$
- Third term:
  $$
  \frac{3}{2} x^{\frac{3}{2} - 1} = \frac{3}{2} x^{1/2} = \frac{3}{2}\sqrt{x}
  $$

Combining the derivatives:
$$
f'(x) = x^{-1/2} + 6x^{-3} + \frac{3}{2}x^{1/2}
$$

Writing in radical and fraction notation:
$$
f'(x) = \frac{1}{\sqrt{x}} + \frac{6}{x^3} + \frac{3\sqrt{x}}{2}
$$

A common denominator can also be found: with common denominator $2x^3$:
$$
f'(x) = \frac{2x^{5/2} + 12 + 3x^{7/2}}{2x^3} = \frac{3x^3\sqrt{x} + 2x^2\sqrt{x} + 12}{2x^3}
$$

---

### Step 4: Compare the Domains $\mathcal{D}_f$ and $\mathcal{D}_{f'}$

Let us examine the domain of $f'(x) = \frac{1}{\sqrt{x}} + \frac{6}{x^3} + \frac{3}{2}\sqrt{x}$:
- $\frac{1}{\sqrt{x}}$ requires $x > 0$ (since the radical is in the denominator).
- $\frac{6}{x^3}$ requires $x \neq 0$.
- $\frac{3}{2}\sqrt{x}$ requires $x \ge 0$.

Taking the intersection:
$$
\mathcal{D}_{f'} = (0, \infty)
$$

**Domain Comparison:**
$$
\mathcal{D}_f = (0, \infty) \quad \text{and} \quad \mathcal{D}_{f'} = (0, \infty) \implies \mathcal{D}_{f'} = \mathcal{D}_f
$$

**Analytical Insight:**
In many elementary problems involving square roots, such as $g(x) = \sqrt{x}$, the domain of the function is $[0, \infty)$ while the domain of its derivative $g'(x) = \frac{1}{2\sqrt{x}}$ is strictly $(0, \infty)$, because the tangent line becomes vertical as $x \to 0^+$ ($g'(x) \to +\infty$), causing non-differentiability at the boundary point $x = 0$.

However, in this function $f(x)$, the presence of the rational term $-\frac{3}{x^2}$ **already excluded** the boundary point $x = 0$ from the domain of $f$ in the first place. Consequently, every point in the domain of $f(x)$ is an interior point of $(0, \infty)$ where each constituent power function is differentiable. Therefore, the domain of the function and the domain of its derivative are completely identical: $\mathcal{D}_{f'} = \mathcal{D}_f = (0, \infty)$.

---

## 4. Verification and Consistency Checks

1. **Evaluation at a Test Point ($x = 1$):**
   - Function value:
     $$
     f(1) = 2\sqrt{1} - \frac{3}{1^2} + 1^{3/2} = 2(1) - 3(1) + 1 = 0
     $$
   - Derivative value:
     $$
     f'(1) = \frac{1}{\sqrt{1}} + \frac{6}{1^3} + \frac{3}{2}\sqrt{1} = 1 + 6 + 1.5 = 8.5 = \frac{17}{2}
     $$

2. **Numerical Difference Quotient Verification at $x = 1$:**
   Compute the symmetric difference quotient with $h = 10^{-4}$:
   - $x + h = 1.0001$:
     $$
     f(1.0001) = 2\sqrt{1.0001} - \frac{3}{(1.0001)^2} + (1.0001)^{1.5} \approx 0.000850021
     $$
   - $x - h = 0.9999$:
     $$
     f(0.9999) = 2\sqrt{0.9999} - \frac{3}{(0.9999)^2} + (0.9999)^{1.5} \approx -0.000849979
     $$
   - Symmetric difference quotient:
     $$
     \frac{f(1.0001) - f(0.9999)}{2 \times 10^{-4}} = \frac{0.001700000}{0.0002} = 8.50000
     $$
   This matches $f'(1) = 8.5$ perfectly.

3. **Behavior near $x \to 0^+$:**
   As $x \to 0^+$:
   $$
   f(x) \approx -\frac{3}{x^2} \to -\infty
   $$
   $$
   f'(x) \approx \frac{6}{x^3} \to +\infty
   $$
   This indicates a steep upward slope as the curve emerges from the vertical asymptote at $x = 0$, consistent with $f'(x) > 0$ for all $x > 0$.
