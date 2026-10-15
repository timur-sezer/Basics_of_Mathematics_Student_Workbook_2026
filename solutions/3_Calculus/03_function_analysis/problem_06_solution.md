# Solution to Problem 6: A Logarithmic Function

## 1. Problem Statement

Perform a rigorous mathematical analysis of the logarithmic function:
$$
f(x) = \ln x - x + 1
$$

1. Determine the maximal domain of definition $\mathcal{D}_f$.
2. Explain why the analysis must always begin with establishing the domain before computing the derivative.
3. Compute the derivative $f'(x)$ and find all critical points.
4. Determine the intervals of monotonicity and classify the global extremum.
5. Identify all zeros of the function and explain how this analysis establishes the fundamental logarithm inequality $\ln x \le x - 1$.
6. Evaluate the boundary limits as $x \to 0^+$ and $x \to +\infty$.

---

## 2. Theoretical Background and Concepts

1. **Domain Precedence Principle:**
   In differential calculus, a function's derivative $f'(x)$ is an operator defined strictly on the interior of the function's domain $\mathcal{D}_f$:
   $$
   \mathcal{D}_{f'} \subseteq \mathcal{D}_f
   $$
   Formula manipulations done without domain constraints frequently produce "phantom" solutions or invalid intervals where the original function does not exist.

2. **Domain of Logarithmic Functions:**
   The natural logarithm $\ln u$ is defined if and only if $u > 0$ in the real number system $\mathbb{R}$.

3. **Global Extrema on Open Intervals:**
   If a function $f$ has a unique critical point $x_0$ on an interval $I$, and $f'(x) > 0$ for all $x < x_0$ and $f'(x) < 0$ for all $x > x_0$, then $f(x_0)$ is the unique **absolute (global) maximum** of $f$ on $I$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Why the Analysis Must Begin with the Domain

1. **The Trap of Mechanical Differentiation:**
   If one ignores the domain and differentiates mechanically:
   $$
   f'(x) = \frac{1}{x} - 1 = \frac{1 - x}{x}
   $$
   Looking solely at the algebraic fraction $\frac{1 - x}{x}$:
   - At $x = -2$: $\frac{1 - (-2)}{-2} = \frac{3}{-2} = -1.5 < 0$.
   - A careless observer might conclude: *"The derivative is negative for $x < 0$, so the function is decreasing on $(-\infty, 0)$."*
   - This statement is an absurdity: for negative $x$, $\ln x$ is undefined in the real numbers, so $f(x)$ **does not exist** at all on $(-\infty, 0]$.

2. **Domain Enforcement:**
   Establishing $\mathcal{D}_f$ first ensures that all subsequent sign charts, critical points, and limit calculations remain strictly within the legitimate domain of definition.

---

### Step 2: Establish the Domain $\mathcal{D}_f$

The linear term $-x + 1$ is defined for all $x \in \mathbb{R}$.
The logarithmic term $\ln x$ requires $x > 0$.
Taking the intersection:
$$
\mathcal{D}_f = (0, \infty) = \{x \in \mathbb{R} : x > 0\}
$$

---

### Step 3: Compute the Derivative and Find Critical Points

Differentiate $f(x) = \ln x - x + 1$ on $\mathcal{D}_f$:
$$
f'(x) = \frac{d}{dx}[\ln x] - \frac{d}{dx}[x] + \frac{d}{dx}[1] = \frac{1}{x} - 1 + 0 = \frac{1 - x}{x}
$$

Find the critical points by solving $f'(x) = 0$ on $(0, \infty)$:
$$
\frac{1 - x}{x} = 0 \iff 1 - x = 0 \iff x = 1
$$
Since $1 \in (0, \infty)$, $x = 1$ is the unique critical point.

---

### Step 4: Monotonicity and Classification of Extrema

On the domain $(0, \infty)$, the denominator $x$ is strictly positive ($x > 0$).
Therefore, the sign of $f'(x)$ is determined solely by the numerator $1 - x$:

1. **Interval $(0, 1)$:**
   For any $0 < x < 1$, we have $1 - x > 0$.
   $$
   f'(x) = \frac{1 - x}{x} > 0
   $$
   Therefore, $f(x)$ is **strictly increasing** on $(0, 1]$.

2. **Point $x = 1$:**
   $$
   f'(1) = 0
   $$

3. **Interval $(1, \infty)$:**
   For any $x > 1$, we have $1 - x < 0$.
   $$
   f'(x) = \frac{1 - x}{x} < 0
   $$
   Therefore, $f(x)$ is **strictly decreasing** on $[1, \infty)$.

**Classification:**
Because $f'(x)$ switches from positive to negative at $x = 1$, the function attains a **strict global maximum** at $x = 1$:
$$
y_{\max} = f(1) = \ln(1) - 1 + 1 = 0 - 0 = 0
$$
The peak point is:
$$
\mathbf{M(1, 0)}
$$

---

### Step 5: Identification of Zeros and the Logarithm Inequality

1. **Uniqueness of the Zero:**
   - The value at the global maximum is $f(1) = 0$.
   - Because $x = 1$ is a strict global maximum, for all $x \in (0, \infty) \setminus \{1\}$:
     $$
     f(x) < f(1) = 0
     $$
   - Consequently, $f(x)$ can never equal zero anywhere else on $(0, \infty)$.
   - Therefore, **$x = 1$ is the unique zero of $f(x)$**.

2. **Derivation of the Fundamental Inequality:**
   Since $f(x) \le 0$ for all $x > 0$:
   $$
   \ln x - x + 1 \le 0 \iff \ln x \le x - 1 \quad \forall x > 0
   $$
   with equality holding if and only if $x = 1$.
   Geometrically, the tangent line to $y = \ln x$ at the point $(1, 0)$ is $y = x - 1$. The entire curve $y = \ln x$ lies below this tangent line.

---

### Step 6: Boundary Limits and Asymptotes

1. **As $x \to 0^+$:**
   $$
   \lim_{x \to 0^+} f(x) = \lim_{x \to 0^+} (\ln x - x + 1) = (-\infty) - 0 + 1 = -\infty
   $$
   The line **$x = 0$** (the $y$-axis) is a **vertical asymptote**.

2. **As $x \to +\infty$:**
   Factor out $x$:
   $$
   \lim_{x \to +\infty} (\ln x - x + 1) = \lim_{x \to +\infty} x \left(\frac{\ln x}{x} - 1 + \frac{1}{x}\right)
   $$
   Since $\lim_{x \to \infty} \frac{\ln x}{x} = 0$:
   $$
   \lim_{x \to +\infty} x (0 - 1 + 0) = \lim_{x \to +\infty} (-x) = -\infty
   $$

**ASCII Graph Sketch:**
```text
           y
           ^
       1   |                  (1, 0)
- - - -0 - + - - - - - - - - - -* - - - - - - - - - - - - - - - - > x  (x-axis is tangent)
      -1   |                  *   *
      -2   |                *       *
      -3   |              *           *
      -4   |             *              *  f(x) = ln(x) - x + 1
      -5   |            *                 *
           |           *
           | x = 0    *
```

---

## 4. Verification and Consistency Checks

1. **Second Derivative and Convexity Check:**
   $$
   f''(x) = \frac{d}{dx}\left[\frac{1}{x} - 1\right] = -\frac{1}{x^2}
   $$
   For all $x \in (0, \infty)$:
   $$
   f''(x) = -\frac{1}{x^2} < 0
   $$
   The function is **strictly concave downward** ($\cap$) on its entire domain $(0, \infty)$.
   A strictly concave function on an interval can have at most one stationary point, which is guaranteed to be an absolute maximum.
   At $x = 1$: $f''(1) = -1 < 0$, verifying the strict maximum.

2. **Numerical Value Checks:**
   | $x$ | $\ln x$ | $-x + 1$ | $f(x) = \ln x - x + 1$ | Sign of $f(x)$ |
   |:---|:---:|:---:|:---:|:---:|
   | $0.1$ | $-2.302585$ | $+0.9$ | $-1.402585$ | Negative |
   | $0.5$ | $-0.693147$ | $+0.5$ | $-0.193147$ | Negative |
   | **$1.0$** | **$0.000000$** | **$0.0$** | **$0.000000$** | **Zero (Max)** |
   | $2.0$ | $+0.693147$ | $-1.0$ | $-0.306853$ | Negative |
   | $e \approx 2.718$ | $+1.000000$ | $-1.718282$ | $-0.718282$ | Negative |
   | $5.0$ | $+1.609438$ | $-4.0$ | $-2.390562$ | Negative |

   Every numerical point satisfies $f(x) \le 0$, confirming the global maximum at $(1, 0)$ and the uniqueness of the zero.
