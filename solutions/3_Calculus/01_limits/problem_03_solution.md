# Solution to Exercise 3: A Square Root and Removing an Indeterminate Form

## 1. Problem Statement

Compute the limit of the sequence:
$$
\lim_{n \to \infty} \left(\sqrt{n^2 + 5n} - n\right)
$$

1. Identify the indeterminate form that arises upon direct inspection.
2. Use algebraic multiplication by the conjugate expression to transform the sequence.
3. Evaluate the limit and explain why the conjugate transformation completely resolves the indeterminate difficulty.

---

## 2. Theoretical Background and Concepts

1. **The Indeterminate Form $\infty - \infty$:**
   As $n \to \infty$, both $\sqrt{n^2 + 5n} \to \infty$ and $n \to \infty$.
   The difference of two quantities that both grow without bound is an **indeterminate form of type $\infty - \infty$**. One cannot subtract infinities because the result depends entirely on the subtle difference in their subdominant asymptotic growth rates.

2. **Rationalization via the Algebraic Conjugate:**
   For any two terms $A$ and $B$, the difference of squares identity states:
   $$
   (A - B)(A + B) = A^2 - B^2 \implies A - B = \frac{A^2 - B^2}{A + B}
   $$
   When $A = \sqrt{n^2 + 5n}$ and $B = n$, multiplying by the conjugate $\sqrt{n^2 + 5n} + n$ eliminates the radical in the numerator:
   $$
   A^2 - B^2 = (\sqrt{n^2 + 5n})^2 - n^2 = (n^2 + 5n) - n^2 = 5n
   $$
   This converts the subtractive indeterminate form $\infty - \infty$ into an additive quotient $\frac{\infty}{\infty}$, which can then be evaluated by factoring out dominant powers.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Multiply and Divide by the Conjugate Expression

Multiply the expression by $\frac{\sqrt{n^2 + 5n} + n}{\sqrt{n^2 + 5n} + n} = 1$:
$$
\sqrt{n^2 + 5n} - n = \frac{\left(\sqrt{n^2 + 5n} - n\right)\left(\sqrt{n^2 + 5n} + n\right)}{\sqrt{n^2 + 5n} + n}
$$

Apply the difference of squares $(A - B)(A + B) = A^2 - B^2$ in the numerator:
$$
= \frac{\left(\sqrt{n^2 + 5n}\right)^2 - n^2}{\sqrt{n^2 + 5n} + n} = \frac{n^2 + 5n - n^2}{\sqrt{n^2 + 5n} + n} = \frac{5n}{\sqrt{n^2 + 5n} + n}
$$

---

### Step 2: Factor Out the Dominant Power $n$ from the Denominator

For $n > 0$, factor $n^2$ out from inside the square root:
$$
\sqrt{n^2 + 5n} = \sqrt{n^2 \left(1 + \frac{5}{n}\right)} = \sqrt{n^2} \sqrt{1 + \frac{5}{n}} = n \sqrt{1 + \frac{5}{n}}
$$

Substitute back into the fraction:
$$
\frac{5n}{\sqrt{n^2 + 5n} + n} = \frac{5n}{n \sqrt{1 + \frac{5}{n}} + n} = \frac{5n}{n \left(\sqrt{1 + \frac{5}{n}} + 1\right)}
$$

Cancel the common factor of $n$ ($n \ge 1$):
$$
= \frac{5}{\sqrt{1 + \frac{5}{n}} + 1}
$$

---

### Step 3: Compute the Limit

As $n \to \infty$, the term $\frac{5}{n} \to 0$.
By the continuity of the square root function:
$$
\lim_{n \to \infty} \sqrt{1 + \frac{5}{n}} = \sqrt{1 + 0} = 1
$$

Evaluate the quotient:
$$
\lim_{n \to \infty} \left(\sqrt{n^2 + 5n} - n\right) = \frac{5}{1 + 1} = \frac{5}{2} = 2.5
$$

---

### Step 4: Why the Conjugate Transformation Resolves the Difficulty

1. **Elimination of Catastrophic Cancellation:**
   Directly subtracting $n$ from $\sqrt{n^2 + 5n}$ cancels the dominant $n^2$ term invisibly behind the radical sign, leaving behind an ambiguous $\infty - \infty$ residual. Conjugation forces the difference of squares, algebraically canceling $n^2 - n^2 = 0$ in the numerator and exposing the true first-order linear difference $5n$.
2. **Transition from Subtraction to Addition:**
   In the denominator, the subtraction $A - B$ becomes an addition $A + B$. Since $\sqrt{n^2 + 5n} + n \sim 2n$, the denominator grows predictably without any internal cancellation, converting an ill-conditioned subtraction into a stable quotient of linear terms $\frac{5n}{2n} = \frac{5}{2}$.

---

## 4. Verification and Consistency Checks

1. **Numerical Sequence Values:**
   - For $n = 1$: $a_1 = \sqrt{1 + 5} - 1 = \sqrt{6} - 1 \approx 2.4495 - 1 = 1.4495$
   - For $n = 10$: $a_{10} = \sqrt{100 + 50} - 10 = \sqrt{150} - 10 \approx 12.2474 - 10 = 2.2474$
   - For $n = 100$: $a_{100} = \sqrt{10000 + 500} - 100 = \sqrt{10500} - 100 \approx 102.4695 - 100 = 2.4695$
   - For $n = 1000$: $a_{1000} = \sqrt{10^6 + 5000} - 1000 \approx 1002.4969 - 1000 = 2.4969$
   - For $n = 10000$: $a_{10000} \approx 2.49969$
   The sequence values monotonically increase towards $2.5000$.

2. **Taylor / Binomial Series Verification:**
   Using the binomial series $\sqrt{1 + u} = 1 + \frac{1}{2}u - \frac{1}{8}u^2 + \dots$ with $u = \frac{5}{n}$:
   $$
   \sqrt{n^2 + 5n} = n \sqrt{1 + \frac{5}{n}} = n \left( 1 + \frac{1}{2}\left(\frac{5}{n}\right) - \frac{1}{8}\left(\frac{5}{n}\right)^2 + \mathcal{O}\left(\frac{1}{n^3}\right) \right)
   $$
   $$
   = n + \frac{5}{2} - \frac{25}{8n} + \mathcal{O}\left(\frac{1}{n^2}\right)
   $$
   Subtracting $n$:
   $$
   \sqrt{n^2 + 5n} - n = \frac{5}{2} - \frac{25}{8n} + \mathcal{O}\left(\frac{1}{n^2}\right)
   $$
   Taking the limit as $n \to \infty$ confirms:
   $$
   \lim_{n \to \infty} \left(\sqrt{n^2 + 5n} - n\right) = \frac{5}{2} = 2.5 \quad (\checkmark)
   $$
