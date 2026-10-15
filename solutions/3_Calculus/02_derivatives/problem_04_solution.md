# Solution to Problem 4: A Quotient and Domain Control

## 1. Problem Statement

Given the rational function:
$$
f(x) = \frac{x^2 + 1}{x - 1}
$$

1. Determine the maximal domain of definition $\mathcal{D}_f$.
2. Compute the derivative $f'(x)$ using the quotient rule.
3. Simplify the resulting expression algebraically.
4. Explain why the restriction $x \neq 1$ remains critically important throughout the differential calculus of this function.

---

## 2. Theoretical Background and Concepts

1. **The Quotient Rule:**
   If $u(x)$ and $v(x)$ are differentiable functions, then their quotient $\frac{u(x)}{v(x)}$ is differentiable at all points where $v(x) \neq 0$, and its derivative is given by:
   $$
   \left(\frac{u}{v}\right)' = \frac{u' v - u v'}{v^2}
   $$
   *Memory Aid / Sign Rule:* The minus sign attaches to the term where the denominator is differentiated ($u v'$).

2. **Domain of a Rational Function:**
   A rational function $\frac{P(x)}{Q(x)}$ is defined for all real numbers where the polynomial denominator is non-zero:
   $$
   \mathcal{D}_f = \{x \in \mathbb{R} : Q(x) \neq 0\}
   $$

3. **Prerequisite for Differentiability:**
   A function $f(x)$ can be differentiable at a point $x_0$ if and only if $f$ is defined in an open neighborhood containing $x_0$. If $x_0 \notin \mathcal{D}_f$, the derivative $f'(x_0)$ cannot exist by definition, as the difference quotient $\frac{f(x_0 + h) - f(x_0)}{h}$ is undefined.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Determine the Domain $\mathcal{D}_f$

The function is a quotient of two polynomials:
- Numerator: $P(x) = x^2 + 1$, defined for all $x \in \mathbb{R}$.
- Denominator: $Q(x) = x - 1$, defined for all $x \in \mathbb{R}$.

Division by zero is undefined, so we require:
$$
x - 1 \neq 0 \iff x \neq 1
$$

Therefore, the domain of $f(x)$ is:
$$
\mathcal{D}_f = \mathbb{R} \setminus \{1\} = (-\infty, 1) \cup (1, \infty)
$$

---

### Step 2: Set Up the Quotient Rule

Assign the numerator and denominator:
- $u(x) = x^2 + 1 \implies u'(x) = 2x$
- $v(x) = x - 1 \implies v'(x) = 1$

Applying the quotient rule formula:
$$
f'(x) = \frac{u'(x) v(x) - u(x) v'(x)}{[v(x)]^2} = \frac{(2x)(x - 1) - (x^2 + 1)(1)}{(x - 1)^2}
$$

---

### Step 3: Expand and Simplify the Numerator

1. Expand the terms in the numerator:
   $$
   (2x)(x - 1) = 2x^2 - 2x
   $$
   $$
   (x^2 + 1)(1) = x^2 + 1
   $$
2. Subtract the second term from the first:
   $$
   \text{Numerator} = (2x^2 - 2x) - (x^2 + 1) = 2x^2 - 2x - x^2 - 1 = x^2 - 2x - 1
   $$
3. Assemble the simplified derivative:
   $$
   f'(x) = \frac{x^2 - 2x - 1}{(x - 1)^2}
   $$

*(Optional Factoring)* The roots of the numerator $x^2 - 2x - 1 = 0$ are found via completing the square:
$$
(x - 1)^2 - 2 = 0 \implies x = 1 \pm \sqrt{2}
$$
Thus, the derivative can also be expressed in factored form as:
$$
f'(x) = \frac{(x - (1 - \sqrt{2}))(x - (1 + \sqrt{2}))}{(x - 1)^2}
$$

---

### Step 4: Why the Restriction $x \neq 1$ Remains Important

1. **Inheritance of Domain Restrictions:**
   The domain of the derivative is:
   $$
   \mathcal{D}_{f'} = \{x \in \mathcal{D}_f : f'(x) \text{ exists}\}
   $$
   Since $x = 1 \notin \mathcal{D}_f$, it cannot belong to $\mathcal{D}_{f'}$. Looking at the formula $f'(x) = \frac{x^2 - 2x - 1}{(x - 1)^2}$, substituting $x = 1$ would cause division by zero in the derivative as well:
   $$
   \frac{1^2 - 2(1) - 1}{(1 - 1)^2} = \frac{-2}{0^+} \to -\infty
   $$

2. **Geometric Significance (Vertical Asymptote):**
   The point $x = 1$ represents a vertical asymptote of the curve $y = f(x)$:
   $$
   \lim_{x \to 1^-} \frac{x^2 + 1}{x - 1} = -\infty, \qquad \lim_{x \to 1^+} \frac{x^2 + 1}{x - 1} = +\infty
   $$
   At a vertical asymptote, the graph breaks into two disjoint branches. There is no point on the graph at $x = 1$, and therefore no tangent line can exist.

3. **Sign Analysis and Monotonicity Intervals:**
   When analyzing where $f(x)$ is increasing or decreasing by solving $f'(x) > 0$ or $f'(x) < 0$, the domain partition point $x = 1$ **must not be ignored**:
   - The sign of $f'(x)$ is determined by the numerator $x^2 - 2x - 1$ because the denominator $(x - 1)^2 > 0$ for all $x \in \mathcal{D}_f$.
   - The critical points are $x_1 = 1 - \sqrt{2} \approx -0.414$ and $x_2 = 1 + \sqrt{2} \approx 2.414$.
   - The sign of $f'(x)$ divides the domain into four intervals:
     - On $(-\infty, 1 - \sqrt{2})$: $f'(x) > 0$ (increasing).
     - On $(1 - \sqrt{2}, 1)$: $f'(x) < 0$ (decreasing).
     - On $(1, 1 + \sqrt{2})$: $f'(x) < 0$ (decreasing).
     - On $(1 + \sqrt{2}, \infty)$: $f'(x) > 0$ (increasing).
   - If one carelessly treated $f(x)$ as defined on the union $(1 - \sqrt{2}, 1 + \sqrt{2})$, one might erroneously conclude that $f(x)$ decreases continuously from $x_1$ to $x_2$. In reality, the graph jumps from $-\infty$ to $+\infty$ across the asymptote $x = 1$. Keeping track of $x \neq 1$ prevents this fatal error.

---

## 4. Verification and Consistency Checks

1. **Alternative Differentiation via Algebraic Decomposition:**
   Perform polynomial long division on $f(x)$:
   $$
   \frac{x^2 + 1}{x - 1} = \frac{(x^2 - 1) + 2}{x - 1} = \frac{(x - 1)(x + 1) + 2}{x - 1} = x + 1 + \frac{2}{x - 1} = x + 1 + 2(x - 1)^{-1}
   $$
   Now differentiate using the sum and power rules directly:
   $$
   f'(x) = \frac{d}{dx}[x] + \frac{d}{dx}[1] + 2 \frac{d}{dx}[(x - 1)^{-1}] = 1 + 0 + 2 \cdot (-1)(x - 1)^{-2} = 1 - \frac{2}{(x - 1)^2}
   $$
   Place over a common denominator:
   $$
   f'(x) = \frac{(x - 1)^2 - 2}{(x - 1)^2} = \frac{x^2 - 2x + 1 - 2}{(x - 1)^2} = \frac{x^2 - 2x - 1}{(x - 1)^2}
   $$
   This matches the quotient rule result identically.

2. **Numerical Value Check at $x = 0$:**
   - Function value: $f(0) = \frac{0^2 + 1}{0 - 1} = -1$.
   - Derivative value: $f'(0) = \frac{0^2 - 2(0) - 1}{(0 - 1)^2} = \frac{-1}{1} = -1$.
   - Difference quotient with $h = 0.001$:
     $$
     \frac{f(0.001) - f(0)}{0.001} = \frac{\frac{(0.001)^2 + 1}{0.001 - 1} - (-1)}{0.001} = \frac{\frac{1.000001}{-0.999} + 1}{0.001} \approx \frac{-1.001002 + 1}{0.001} = -1.002 \approx -1
     $$
   The check confirms $f'(0) = -1$.
