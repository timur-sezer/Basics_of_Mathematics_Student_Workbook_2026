# Solution to Problem 8: Two Exponential Functions

## 1. Problem Statement

Given the exponential function:
$$
f(x) = e^{2x - 3} + 5^x
$$

1. Compute the derivative $f'(x)$.
2. Explain the mathematical origin of the constant factor $2$ in the derivative of the first term.
3. Explain the mathematical origin of the factor $\ln 5$ in the derivative of the second term.
4. Contrast the two distinct mechanisms (chain rule on the argument versus base change) that produce these additional multiplicative factors.

---

## 2. Theoretical Background and Concepts

1. **The Natural Exponential Function:**
   The function $e^x$ is the unique exponential function whose instantaneous rate of change equals its value everywhere:
   $$
   \frac{d}{dx}[e^x] = e^x
   $$
   Equivalently, its tangent line at $x = 0$ has slope $\lim_{h \to 0} \frac{e^h - 1}{h} = 1$.

2. **The Chain Rule for Exponentials:**
   When the exponent is a differentiable function $u(x)$:
   $$
   \frac{d}{dx}[e^{u(x)}] = e^{u(x)} \cdot u'(x)
   $$

3. **General Exponential Functions ($a^x$ where $a > 0, a \neq 1$):**
   Using the fundamental identity $a = e^{\ln a}$, any general exponential $a^x$ can be expressed in terms of the natural base $e$:
   $$
   a^x = \left(e^{\ln a}\right)^x = e^{x \ln a}
   $$
   Applying the chain rule with inner function $w(x) = x \ln a$:
   $$
   \frac{d}{dx}[a^x] = \frac{d}{dx}[e^{x \ln a}] = e^{x \ln a} \cdot \frac{d}{dx}[x \ln a] = a^x \cdot \ln a
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Differentiate the First Term $e^{2x - 3}$

1. Recognize the composition $g(u) = e^u$ where $u(x) = 2x - 3$.
2. The outer derivative is:
   $$
   \frac{dg}{du} = e^u = e^{2x - 3}
   $$
3. The inner derivative is:
   $$
   \frac{du}{dx} = \frac{d}{dx}[2x - 3] = 2
   $$
4. By the chain rule:
   $$
   \frac{d}{dx}[e^{2x - 3}] = e^{2x - 3} \cdot 2 = 2e^{2x - 3}
   $$

---

### Step 2: Differentiate the Second Term $5^x$

1. Recognize that the base is $a = 5 \neq e$.
2. Rewrite $5^x$ using natural logarithms:
   $$
   5^x = e^{x \ln 5}
   $$
3. Differentiate using the chain rule with inner function $v(x) = x \ln 5$ (where $\ln 5$ is a constant):
   $$
   \frac{d}{dx}[5^x] = \frac{d}{dx}[e^{x \ln 5}] = e^{x \ln 5} \cdot \frac{d}{dx}[x \ln 5] = 5^x \cdot \ln 5
   $$

---

### Step 3: Combine to Obtain the Complete Derivative

Applying the sum rule:
$$
f'(x) = \frac{d}{dx}[e^{2x - 3}] + \frac{d}{dx}[5^x] = 2e^{2x - 3} + 5^x \ln 5
$$

---

### Step 4: Comparison of the Two Distinct Mechanisms

The two additional factors arise from two entirely different mathematical sources:

1. **Origin of the Factor $2$ (Inner Function in the Argument):**
   - The base is the standard natural base $e$, which requires no logarithmic scaling factor because $\ln e = 1$.
   - The factor $2$ appears because the exponent is **not a simple $x$**, but a linear function $u(x) = 2x - 3$.
   - As $x$ increases at rate $1$, the exponent $u$ increases twice as fast ($\frac{du}{dx} = 2$). By the chain rule, this speed-up factor of $2$ multiplies the entire rate of change.

2. **Origin of the Factor $\ln 5$ (Base Conversion):**
   - The exponent is the simplest possible linear function $x$, whose derivative is simply $1$.
   - The factor $\ln 5 \approx 1.6094$ appears because the **base is $5$ rather than $e$**.
   - Since $5 > e \approx 2.718$, powers of $5$ grow intrinsically faster than powers of $e$. At $x = 0$, the curve $y = 5^x$ passes through $(0, 1)$ with slope $\ln 5 > 1$. The multiplier $\ln 5$ is the natural conversion factor required to relate growth in base $5$ to the fundamental calculus unit of exponential growth, base $e$.

| Feature | Term 1: $e^{2x - 3}$ | Term 2: $5^x$ |
|:---|:---|:---|
| **Base** | Natural ($e$) | Non-natural ($5$) |
| **Exponent** | Composite ($2x - 3$) | Elementary ($x$) |
| **Source of Extra Factor** | Chain rule on inner function | Conversion to natural base |
| **Extra Factor** | $2 = \frac{d}{dx}[2x - 3]$ | $\ln 5 = \ln(\text{base})$ |

---

## 4. Verification and Consistency Checks

1. **Value Check at $x = 0$:**
   - Function value:
     $$
     f(0) = e^{2(0) - 3} + 5^0 = e^{-3} + 1 \approx 0.049787 + 1 = 1.049787
     $$
   - Derivative value:
     $$
     f'(0) = 2e^{2(0) - 3} + 5^0 \ln 5 = 2e^{-3} + \ln 5 \approx 2(0.049787) + 1.609438 = 0.099574 + 1.609438 = 1.709012
     $$

2. **Difference Quotient Verification at $x = 0$:**
   Let $h = 10^{-4} = 0.0001$:
   - $f(h) = e^{2(0.0001) - 3} + 5^{0.0001} = e^{-2.9998} + 5^{0.0001}$
   - $e^{-2.9998} \approx e^{-3} \cdot e^{0.0002} \approx 0.04978707 \cdot (1 + 0.0002) \approx 0.04979703$
   - $5^{0.0001} = e^{0.0001 \ln 5} \approx 1 + 0.0001(1.609438) = 1.00016094$
   - $f(h) \approx 1.04995797$
   - Difference quotient:
     $$
     \frac{f(h) - f(0)}{h} \approx \frac{1.04995797 - 1.04978707}{0.0001} = \frac{0.00017090}{0.0001} \approx 1.7090
     $$
   This matches the theoretical $f'(0) \approx 1.709012$ to 5 significant digits.

3. **Global Positivity:**
   Because $e^u > 0$ and $5^x > 0$ for all real $x$, and both coefficients $2 > 0$ and $\ln 5 > 0$, we have:
   $$
   f'(x) = 2e^{2x - 3} + 5^x \ln 5 > 0 \quad \forall x \in \mathbb{R}
   $$
   The function $f(x)$ is strictly increasing on the entire real line $\mathbb{R}$.
