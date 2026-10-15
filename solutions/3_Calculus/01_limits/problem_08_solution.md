# Solution to Exercise 8: A Square Root in a Function Limit

## 1. Problem Statement

Compute the limit of the algebraic function as $x \to 4$:
$$
\lim_{x \to 4} \frac{\sqrt{x} - 2}{x - 4}
$$

1. Rationalize the numerator by multiplying by the appropriate conjugate expression.
2. Evaluate the limit in the simplified form.
3. Compare the core mathematical idea with Exercise 3 (which involved a sequence with a square root).

---

## 2. Theoretical Background and Concepts

1. **Indeterminate Form $\frac{0}{0}$ Involving Radicals:**
   Direct substitution of $x = 4$ yields:
   $$
   \frac{\sqrt{4} - 2}{4 - 4} = \frac{2 - 2}{0} = \frac{0}{0}
   $$
   Because the expression is indeterminate, we cannot apply the quotient rule directly.

2. **Rationalization Principle:**
   Using the algebraic identity $(A - B)(A + B) = A^2 - B^2$ with $A = \sqrt{x}$ and $B = 2$:
   $$
   (\sqrt{x} - 2)(\sqrt{x} + 2) = (\sqrt{x})^2 - 2^2 = x - 4
   $$
   Multiplying and dividing by the conjugate $(\sqrt{x} + 2)$ creates the factor $(x - 4)$ in the numerator, which cancels the $(x - 4)$ in the denominator for all $x \ne 4$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Multiply and Divide by the Conjugate of the Numerator

The conjugate of $\sqrt{x} - 2$ is $\sqrt{x} + 2$.
Multiply the fraction by $\frac{\sqrt{x} + 2}{\sqrt{x} + 2} = 1$ (valid for all $x \ge 0$):
$$
\frac{\sqrt{x} - 2}{x - 4} = \frac{(\sqrt{x} - 2)(\sqrt{x} + 2)}{(x - 4)(\sqrt{x} + 2)}
$$

---

### Step 2: Expand the Numerator

Apply the difference of squares in the numerator:
$$
(\sqrt{x} - 2)(\sqrt{x} + 2) = (\sqrt{x})^2 - 2^2 = x - 4
$$

Substitute this back into the fraction:
$$
= \frac{x - 4}{(x - 4)(\sqrt{x} + 2)}
$$

---

### Step 3: Cancel the Common Factor $(x - 4)$

In evaluating the limit as $x \to 4$, we examine values in a punctured neighborhood $x \ne 4$.
Since $x \ne 4$, $x - 4 \ne 0$. We cancel $(x - 4)$:
$$
= \frac{1}{\sqrt{x} + 2} \quad \text{for all } x \in [0, \infty) \setminus \{4\}
$$

---

### Step 4: Evaluate the Limit

Because the function $g(x) = \frac{1}{\sqrt{x} + 2}$ is continuous at $x = 4$ and its denominator is non-zero ($\sqrt{4} + 2 = 4 \ne 0$):
$$
\lim_{x \to 4} \frac{\sqrt{x} - 2}{x - 4} = \lim_{x \to 4} \frac{1}{\sqrt{x} + 2} = \frac{1}{\sqrt{4} + 2} = \frac{1}{2 + 2} = \frac{1}{4} = 0.25
$$

---

### Step 5: Comparison with Exercise 3

1. **The Shared Core Mechanism:**
   Both problems use the **exact same algebraic tool**: multiplying and dividing by the conjugate expression $A + B$ to leverage $(A - B)(A + B) = A^2 - B^2$.
2. **Transfer Across Contexts:**
   - In **Exercise 3**, the conjugate was applied to an **$\infty - \infty$ sequence limit at infinity**:
     $$
     \sqrt{n^2 + 5n} - n = \frac{5n}{\sqrt{n^2 + 5n} + n} \to \frac{5}{2}
     $$
     Here, conjugation converted an intractable subtraction of infinite quantities into a well-behaved quotient of linear expressions.
   - In **Exercise 8**, the conjugate is applied to a **$\frac{0}{0}$ function limit at a finite point**:
     $$
     \frac{\sqrt{x} - 2}{x - 4} = \frac{x - 4}{(x - 4)(\sqrt{x} + 2)} \to \frac{1}{4}
     $$
     Here, conjugation manufactured the vanishing factor $(x - 4)$ in the numerator, enabling cancellation.
3. **Conclusion:**
   The algebraic method of conjugation is universal across calculus; it resolves both $\infty - \infty$ and $\frac{0}{0}$ indeterminate forms by replacing differences of radicals with non-zero polynomial factors.

---

## 4. Verification and Consistency Checks

1. **Numerical Values Approaching $x = 4$:**
   - From the left:
     - $x = 3.9$: $f(3.9) = \frac{\sqrt{3.9} - 2}{3.9 - 4} \approx \frac{1.974842 - 2}{-0.1} = \frac{-0.025158}{-0.1} = 0.25158$
     - $x = 3.99$: $f(3.99) \approx 0.25016$
     - $x = 3.999$: $f(3.999) \approx 0.25002$
   - From the right:
     - $x = 4.1$: $f(4.1) = \frac{\sqrt{4.1} - 2}{4.1 - 4} \approx \frac{2.024846 - 2}{0.1} = \frac{0.024846}{0.1} = 0.24846$
     - $x = 4.01$: $f(4.01) \approx 0.24984$
     - $x = 4.001$: $f(4.001) \approx 0.24998$
   Both sides converge to $0.2500 = \frac{1}{4}$.

2. **Derivative Definition Check:**
   By definition, the limit $\lim_{x \to 4} \frac{\sqrt{x} - 2}{x - 4} = \lim_{x \to 4} \frac{g(x) - g(4)}{x - 4}$ is precisely the derivative of $g(x) = \sqrt{x} = x^{1/2}$ at $x = 4$:
   $$
   g'(x) = \frac{1}{2\sqrt{x}} \implies g'(4) = \frac{1}{2\sqrt{4}} = \frac{1}{2(2)} = \frac{1}{4} \quad (\checkmark)
   $$
   The derivative confirms the limit.
