# Solution to Problem 11: Derivative from the Definition

## 1. Problem Statement

Using strictly the limit definition of the derivative:
$$
f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}
$$

1. Find the derivative of the quadratic function $f(x) = x^2$.
2. Compare the derived result with the power rule formula $\frac{d}{dx}[x^n] = n x^{n-1}$.
3. Explicitly identify each stage in the calculation where the limit concept and limit operations are utilized.

---

## 2. Theoretical Background and Concepts

1. **Definition of the Derivative:**
   The derivative $f'(x)$ is defined as the limit of the difference quotient (average rate of change) as the increment $h \to 0$:
   $$
   f'(x) = \lim_{h \to 0} \frac{\Delta f}{h} = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}
   $$

2. **The Indeterminate Form $\frac{0}{0}$:**
   Evaluating the difference quotient at $h = 0$ gives:
   $$
   \frac{f(x + 0) - f(x)}{0} = \frac{0}{0}
   $$
   Direct substitution fails because division by zero is undefined. The evaluation requires algebraic reduction (canceling the factor $h$ from numerator and denominator) before the limit can be computed.

3. **Secant to Tangent Transition:**
   - For any non-zero $h \neq 0$, the ratio $\frac{f(x + h) - f(x)}{h}$ represents the slope of the **secant line** connecting two distinct points $P(x, f(x))$ and $Q(x + h, f(x + h))$ on the graph.
   - The limit process $h \to 0$ brings the second point $Q$ along the curve toward $P$, transforming the secant line into the unique **tangent line** at $P$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Formulate the Difference Quotient

For $f(x) = x^2$:
1. Compute the perturbed function value $f(x + h)$:
   $$
   f(x + h) = (x + h)^2 = x^2 + 2xh + h^2
   $$
2. Compute the function increment $\Delta f = f(x + h) - f(x)$:
   $$
   f(x + h) - f(x) = (x^2 + 2xh + h^2) - x^2 = 2xh + h^2
   $$
3. Form the difference quotient for $h \neq 0$:
   $$
   \frac{f(x + h) - f(x)}{h} = \frac{2xh + h^2}{h}
   $$

---

### Step 2: Algebraic Simplification (Eliminating the Indeterminacy)

Factor out the common factor $h$ in the numerator:
$$
\frac{2xh + h^2}{h} = \frac{h(2x + h)}{h}
$$
Because the limit definition considers $h \to 0$, $h$ is strictly non-zero ($h \neq 0$). We can divide through by $h$:
$$
\frac{h(2x + h)}{h} = 2x + h \quad \text{for } h \neq 0
$$

---

### Step 3: Evaluate the Limit as $h \to 0$

Now apply the limit operator to the simplified expression:
$$
f'(x) = \lim_{h \to 0} (2x + h)
$$
Since $2x + h$ is a polynomial in $h$, it is continuous with respect to $h$. By direct substitution:
$$
\lim_{h \to 0} (2x + h) = 2x + 0 = 2x
$$

Therefore:
$$
f'(x) = 2x
$$

---

### Step 4: Comparison with the Power Rule

- **Power Rule Statement:** For any integer $n \ge 1$:
  $$
  \frac{d}{dx}[x^n] = n x^{n-1}
  $$
- **Applying to $n = 2$:**
  $$
  \frac{d}{dx}[x^2] = 2 x^{2-1} = 2 x^1 = 2x
  $$
- **Comparison:**
  The result obtained from first principles ($2x$) matches the power rule formula identically. This demonstrates that the power rule is not an arbitrary empirical formula, but a direct consequence of the binomial expansion $(x + h)^n$ combined with the limit definition of the derivative.

---

### Step 5: Identification of Where the Limit Is Used

The limit concept is actively used in three distinct, critical roles during the calculation:

1. **Resolution of the Indeterminate Ratio:**
   At $h = 0$, the ratio $\frac{(x+h)^2 - x^2}{h} = \frac{0}{0}$ is meaningless. The limit definition provides the rigorous framework to analyze what happens in a deleted neighborhood of $0$ ($0 < |h| < \delta$), legitimizing the cancellation of $h$.
2. **Elimination of the Secant Deviation Term ($h$):**
   The simplified secant slope is $2x + h$. The term $2x$ depends only on the location $x$, while $h$ represents the error or deviation introduced by taking a discrete step of size $h$. The limit operator $\lim_{h \to 0}$ vanishes this deviation term ($h \to 0$), leaving the exact instantaneous rate $2x$.
3. **Transition from Average Rate to Instantaneous Rate:**
   Without the limit, one is restricted to average rates of change over finite intervals $[x, x + h]$. The limit is the mathematical mechanism that defines the instantaneous rate of change at a single point.

---

## 4. Verification and Consistency Checks

1. **Evaluation at Specific Test Points:**
   - At $x = 0$: $f'(0) = 2(0) = 0$. (At the vertex $(0, 0)$, the tangent is the horizontal line $y = 0$).
   - At $x = 3$: $f'(3) = 2(3) = 6$.
     - Verify with $h = 0.01$:
       $$
       \frac{f(3.01) - f(3)}{0.01} = \frac{3.01^2 - 3^2}{0.01} = \frac{9.0601 - 9}{0.01} = \frac{0.0601}{0.01} = 6.01
       $$
     - As $h \to 0$, $6.01 \to 6$.

2. **Generalization to $x^n$ via Binomial Theorem:**
   For any positive integer $n$:
   $$
   (x + h)^n = x^n + n x^{n-1}h + \binom{n}{2}x^{n-2}h^2 + \dots + h^n
   $$
   $$
   \frac{f(x + h) - f(x)}{h} = n x^{n-1} + h\left[\binom{n}{2}x^{n-2} + \dots + h^{n-2}\right]
   $$
   Taking $h \to 0$, all terms with $h$ vanish, leaving:
   $$
   \lim_{h \to 0} \frac{(x + h)^n - x^n}{h} = n x^{n-1}
   $$
   For $n = 2$, this reduces precisely to $2x$, confirming total theoretical consistency.
