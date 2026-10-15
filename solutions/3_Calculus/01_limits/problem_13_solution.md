# Solution to Exercise 13: Fundamental Trigonometric Limit

## 1. Problem Statement

Given the fundamental trigonometric limit:
$$
\lim_{u \to 0} \frac{\sin u}{u} = 1
$$

compute the following two limits:
$$
L_1 = \lim_{x \to 0} \frac{\sin 5x}{x}, \qquad L_2 = \lim_{x \to 0} \frac{\sin 2x}{\sin 3x}
$$

In each case, explicitly demonstrate the algebraic transformations used to reduce the given expression to the fundamental limit pattern.

---

## 2. Theoretical Background and Concepts

1. **The Fundamental Trigonometric Limit:**
   Geometrically derived from the unit circle using the Squeeze Theorem:
   $$
   \cos u < \frac{\sin u}{u} < 1 \quad \text{for } 0 < |u| < \frac{\pi}{2}
   $$
   Taking the limit as $u \to 0$ yields:
   $$
   \lim_{u \to 0} \frac{\sin u}{u} = 1
   $$
   This identity establishes that $\sin u$ and $u$ are asymptotically equivalent ($\sin u \sim u$) as $u \to 0$.

2. **Argument Matching Principle:**
   To apply $\lim_{u \to 0} \frac{\sin u}{u} = 1$, the expression in the denominator must **exactly match the argument of the sine function** in the numerator. If the argument is $kx$, we must construct $kx$ in the denominator:
   $$
   \frac{\sin kx}{x} = k \cdot \frac{\sin kx}{kx}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Evaluation of $L_1 = \lim_{x \to 0} \frac{\sin 5x}{x}$

1. **Identify the Indeterminate Form:**
   Direct substitution gives $\frac{\sin 0}{0} = \frac{0}{0}$.

2. **Match the Argument in the Denominator:**
   The argument of the sine function is $5x$, but the denominator is $x$.
   Multiply and divide by $5$:
   $$
   \frac{\sin 5x}{x} = 5 \cdot \frac{\sin 5x}{5x}
   $$

3. **Perform the Substitution:**
   Let $u = 5x$.
   As $x \to 0$, we have $u \to 0$.
   Rewrite the limit:
   $$
   L_1 = \lim_{x \to 0} \left(5 \cdot \frac{\sin 5x}{5x}\right) = 5 \cdot \lim_{u \to 0} \frac{\sin u}{u}
   $$

4. **Evaluate:**
   Using the fundamental limit $\lim_{u \to 0} \frac{\sin u}{u} = 1$:
   $$
   L_1 = 5 \cdot 1 = 5
   $$

---

### Step 2: Evaluation of $L_2 = \lim_{x \to 0} \frac{\sin 2x}{\sin 3x}$

1. **Identify the Indeterminate Form:**
   Direct substitution gives $\frac{\sin 0}{\sin 0} = \frac{0}{0}$.

2. **Introduce the Linear Variable $x$:**
   Divide both the numerator and the denominator by $x$ (valid for $x \ne 0$):
   $$
   \frac{\sin 2x}{\sin 3x} = \frac{\frac{\sin 2x}{x}}{\frac{\sin 3x}{x}}
   $$

3. **Normalize Each Trigonometric Ratio to the Fundamental Pattern:**
   - In the numerator, multiply and divide by $2$:
     $$
     \frac{\sin 2x}{x} = 2 \cdot \frac{\sin 2x}{2x}
     $$
   - In the denominator, multiply and divide by $3$:
     $$
     \frac{\sin 3x}{x} = 3 \cdot \frac{\sin 3x}{3x}
     $$

4. **Combine the Expressions:**
   $$
   \frac{\sin 2x}{\sin 3x} = \frac{2 \cdot \frac{\sin 2x}{2x}}{3 \cdot \frac{\sin 3x}{3x}} = \frac{2}{3} \cdot \frac{\frac{\sin 2x}{2x}}{\frac{\sin 3x}{3x}}
   $$

5. **Evaluate the Limit:**
   As $x \to 0$, both $2x \to 0$ and $3x \to 0$. By the fundamental limit:
   $$
   \lim_{x \to 0} \frac{\sin 2x}{2x} = 1, \qquad \lim_{x \to 0} \frac{\sin 3x}{3x} = 1
   $$
   By the quotient rule for limits:
   $$
   L_2 = \frac{2}{3} \cdot \frac{\lim_{x \to 0} \frac{\sin 2x}{2x}}{\lim_{x \to 0} \frac{\sin 3x}{3x}} = \frac{2}{3} \cdot \frac{1}{1} = \frac{2}{3}
   $$

---

## 4. Verification and Consistency Checks

1. **Numerical Verification for $L_1$:**
   - $x = 0.1$: $\frac{\sin(0.5)}{0.1} \approx \frac{0.479426}{0.1} = 4.79426$
   - $x = 0.01$: $\frac{\sin(0.05)}{0.01} \approx \frac{0.049979}{0.01} = 4.99792$
   - $x = 0.001$: $\frac{\sin(0.005)}{0.001} \approx \frac{0.00499998}{0.001} = 4.99998$
   The sequence of values converges to $5.0000$.

2. **Numerical Verification for $L_2$:**
   - $x = 0.1$: $\frac{\sin(0.2)}{\sin(0.3)} \approx \frac{0.198669}{0.295520} \approx 0.67227$
   - $x = 0.01$: $\frac{\sin(0.02)}{\sin(0.03)} \approx \frac{0.0199987}{0.0299955} \approx 0.66672$
   - $x = 0.001$: $\frac{\sin(0.002)}{\sin(0.003)} \approx \frac{0.001999999}{0.002999996} \approx 0.666667$
   The sequence of values converges to $\frac{2}{3} \approx 0.666667$.

3. **Taylor Series Expansion Verification:**
   Using the Maclaurin series $\sin u = u - \frac{u^3}{6} + \mathcal{O}(u^5)$:
   - For $L_1$:
     $$
     \frac{\sin 5x}{x} = \frac{5x - \frac{(5x)^3}{6} + \dots}{x} = 5 - \frac{125}{6}x^2 + \dots \xrightarrow{x \to 0} 5 \quad (\checkmark)
     $$
   - For $L_2$:
     $$
     \frac{\sin 2x}{\sin 3x} = \frac{2x - \frac{8}{6}x^3 + \dots}{3x - \frac{27}{6}x^3 + \dots} = \frac{x\left(2 - \frac{4}{3}x^2 + \dots\right)}{x\left(3 - \frac{9}{2}x^2 + \dots\right)} = \frac{2 - \frac{4}{3}x^2 + \dots}{3 - \frac{9}{2}x^2 + \dots} \xrightarrow{x \to 0} \frac{2}{3} \quad (\checkmark)
     $$
