# Solution to Problem 13: A Logarithm and an Asymptote

## 1. Problem Statement

Perform a complete, rigorous function analysis of:
$$
f(x) = \frac{\ln x}{x}, \qquad x > 0
$$

1. Specify the domain $\mathcal{D}_f$ and find the unique zero of the function.
2. Compute the first derivative $f'(x)$ and locate the exact coordinates and nature of the global maximum.
3. Investigate the asymptotic behavior at both boundaries of the domain ($x \to 0^+$ and $x \to +\infty$).
4. Compute the second derivative $f''(x)$, determine the intervals of concavity, and locate the inflection point.
5. Identify the essential mathematical components necessary to produce a geometrically accurate sketch.

---

## 2. Theoretical Background and Concepts

1. **Relative Growth Rates of Logarithms and Linear Powers:**
   The logarithmic function grows more slowly than any positive power of $x$:
   $$
   \lim_{x \to \infty} \frac{\ln x}{x^p} = 0 \quad \text{for any } p > 0
   $$
   This ensures that $f(x) = \frac{\ln x}{x}$ approaches zero asymptotically as $x \to \infty$.

2. **The Famous Inequality Between $e^\pi$ and $\pi^e$:**
   Because $f(x) = \frac{\ln x}{x}$ attains its unique global maximum at $x = e$:
   $$
   f(e) > f(\pi) \implies \frac{\ln e}{e} > \frac{\ln \pi}{\pi} \implies \pi \ln e > e \ln \pi \implies \ln(e^\pi) > \ln(\pi^e) \implies e^\pi > \pi^e
   $$

3. **Asymptotic Convergence with Invariant Sign:**
   When a curve approaches a horizontal asymptote $y = 0$ from above while strictly decreasing, it must possess an **inflection point** to convert its downward concavity into upward concavity, preventing it from piercing the horizontal asymptote.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and Intercepts

1. **Domain:**
   The natural logarithm $\ln x$ requires $x > 0$, and the denominator requires $x \neq 0$.
   $$
   \mathcal{D}_f = (0, \infty) = \{x \in \mathbb{R} : x > 0\}
   $$

2. **Intercepts (Zeros):**
   Set $f(x) = 0$:
   $$
   \frac{\ln x}{x} = 0 \iff \ln x = 0 \iff x = 1
   $$
   The unique $x$-intercept is:
   $$
   \mathbf{(1, 0)}
   $$
   - For $0 < x < 1$: $\ln x < 0 \implies f(x) < 0$ (negative branch).
   - For $x > 1$: $\ln x > 0 \implies f(x) > 0$ (positive branch).
   - There is no $y$-intercept because $x = 0 \notin \mathcal{D}_f$.

---

### Step 2: First Derivative, Monotonicity, and the Global Maximum

1. **Compute $f'(x)$ using the Quotient Rule:**
   $$
   f'(x) = \frac{\frac{d}{dx}[\ln x] \cdot x - \ln x \cdot \frac{d}{dx}[x]}{x^2} = \frac{\left(\frac{1}{x}\right) x - (\ln x)(1)}{x^2} = \frac{1 - \ln x}{x^2}
   $$

2. **Critical Points:**
   Set $f'(x) = 0$ on $(0, \infty)$:
   $$
   \frac{1 - \ln x}{x^2} = 0 \iff 1 - \ln x = 0 \iff \ln x = 1 \iff x = e \approx 2.71828
   $$
   The single critical point is $x = e$.

3. **Sign Chart and Monotonicity:**
   Because $x^2 > 0$ for all $x \in (0, \infty)$, the sign of $f'(x)$ is given by $1 - \ln x$:
   - **For $x \in (0, e)$:** $\ln x < 1 \implies 1 - \ln x > 0 \implies f'(x) > 0$.
     $f(x)$ is **strictly increasing** on $(0, e]$.
   - **At $x = e$:** $f'(e) = 0$ (horizontal tangent line).
   - **For $x \in (e, \infty)$:** $\ln x > 1 \implies 1 - \ln x < 0 \implies f'(x) < 0$.
     $f(x)$ is **strictly decreasing** on $[e, \infty)$.

4. **Character and Value of the Maximum:**
   Because $f'(x)$ transitions from positive to negative at $x = e$, $x = e$ is the **unique strict global maximum**:
   $$
   y_{\max} = f(e) = \frac{\ln e}{e} = \frac{1}{e} \approx 0.367879
   $$
   The peak point is:
   $$
   \mathbf{M\left(e, \frac{1}{e}\right)}
   $$

---

### Step 3: Boundary Limits and Asymptotes

1. **Behavior at the Left Boundary ($x \to 0^+$):**
   $$
   \lim_{x \to 0^+} \frac{\ln x}{x} = \frac{-\infty}{0^+} = (-\infty) \cdot (+\infty) = -\infty
   $$
   The line **$x = 0$** (the $y$-axis) is a **vertical asymptote**. The graph plunges to $-\infty$ as it nears the $y$-axis from the right.

2. **Behavior at the Right Boundary ($x \to +\infty$):**
   This is an indeterminate form of type $\frac{\infty}{\infty}$.
   Applying l'Hôpital's rule:
   $$
   \lim_{x \to +\infty} \frac{\ln x}{x} = \lim_{x \to +\infty} \frac{\frac{d}{dx}[\ln x]}{\frac{d}{dx}[x]} = \lim_{x \to +\infty} \frac{\frac{1}{x}}{1} = \lim_{x \to +\infty} \frac{1}{x} = 0^+
   $$
   The line **$y = 0$** (the positive $x$-axis) is a **horizontal asymptote**.
   The curve approaches $0$ from strictly above because $\ln x > 0$ for all $x > 1$.

---

### Step 4: Second Derivative, Concavity, and Inflection Point

1. **Compute $f''(x)$:**
   Differentiate $f'(x) = \frac{1 - \ln x}{x^2}$ using the quotient rule:
   $$
   f''(x) = \frac{\left(-\frac{1}{x}\right) x^2 - (1 - \ln x)(2x)}{x^4} = \frac{-x - 2x(1 - \ln x)}{x^4} = \frac{-x - 2x + 2x\ln x}{x^4}
   $$
   Factor out $x$ from the numerator:
   $$
   f''(x) = \frac{x(2\ln x - 3)}{x^4} = \frac{2\ln x - 3}{x^3}
   $$

2. **Zeros of $f''(x)$:**
   $$
   2\ln x - 3 = 0 \iff \ln x = \frac{3}{2} \iff x = e^{3/2} = e\sqrt{e} \approx 2.718 \times 1.649 \approx 4.4817
   $$

3. **Intervals of Concavity:**
   Because $x^3 > 0$ on $(0, \infty)$, the sign of $f''(x)$ is governed by $2\ln x - 3$:
   - For $0 < x < e^{3/2}$: $\ln x < 3/2 \implies f''(x) < 0 \implies$ **concave downward** ($\cap$).
   - For $x > e^{3/2}$: $\ln x > 3/2 \implies f''(x) > 0 \implies$ **concave upward** ($\cup$).

4. **Coordinates of the Inflection Point:**
   $$
   y_{\text{inf}} = f\left(e^{3/2}\right) = \frac{\ln\left(e^{3/2}\right)}{e^{3/2}} = \frac{\frac{3}{2}}{e^{3/2}} = \frac{3}{2e\sqrt{e}} \approx 0.334695
   $$
   The unique inflection point is:
   $$
   \mathbf{I\left(e^{3/2}, \frac{3}{2e^{3/2}}\right)} \approx (4.48, 0.335)
   $$

---

### Step 5: Essential Information for an Accurate Sketch

To produce a mathematically faithful sketch without geometric distortion, the following five critical milestones are necessary and sufficient:
1. **Vertical Asymptote at $x = 0$:** The curve drops vertically to $-\infty$ as $x \to 0^+$.
2. **Zero at $(1, 0)$:** The curve crosses the horizontal axis at $x = 1$ with slope $f'(1) = \frac{1 - \ln 1}{1^2} = 1$ ($45^\circ$).
3. **Global Peak at $\left(e, \frac{1}{e}\right) \approx (2.72, 0.37)$:** The curve reaches its absolute maximum where the tangent is horizontal ($m = 0$).
4. **Inflection Transition at $\left(e^{3/2}, \frac{3}{2e^{3/2}}\right) \approx (4.48, 0.33)$:** The curve changes from concave downward to concave upward, beginning to level off.
5. **Horizontal Asymptote at $y = 0$:** The tail slowly decays toward $0^+$ as $x \to \infty$.

**ASCII Graph Sketch:**
```text
            y
            ^
     0.4    |               * M(e ≈ 2.72, 1/e ≈ 0.37)
     0.3    |             *   *
            |            *      * I(e^1.5 ≈ 4.48, 0.33)
     0.2    |           *         *
     0.1    |          *            *  *  *  *  *  *  *  (approaching y = 0 from above)
   ---------+---------*-----------------------------------> x
    0       | (0, 0) (1, 0) 2    3    4    5    6    7
            |        *
    -1      |       *
            |      *
    -2      |     *   f(x) = ln(x) / x
            |    *
            | x = 0 (Vertical Asymptote)
```

---

## 4. Verification and Consistency Checks

1. **Second Derivative Test at the Maximum:**
   $$
   f''(e) = \frac{2\ln e - 3}{e^3} = \frac{2(1) - 3}{e^3} = -\frac{1}{e^3} \approx -0.0498 < 0
   $$
   The second derivative is negative, confirming that $x = e$ is a strict local maximum.

2. **Numerical Value Checks Across the Domain:**
   | $x$ | $\ln x$ | $f(x) = \frac{\ln x}{x}$ | Status |
   |:---|:---:|:---:|:---|
   | $0.1$ | $-2.302585$ | $-23.02585$ | Rapid plunge to $-\infty$ |
   | $0.5$ | $-0.693147$ | $-1.386294$ | Negative branch |
   | **$1.0$** | **$0.000000$** | **$0.000000$** | **$x$-intercept** |
   | $2.0$ | $+0.693147$ | $+0.346574$ | Increasing |
   | **$e \approx 2.718$** | **$1.000000$** | **$+0.367879$** | **Global Maximum** |
   | $\pi \approx 3.142$ | $+1.144730$ | $+0.364356$ | Decreasing ($f(\pi) < f(e)$) |
   | **$e^{1.5} \approx 4.482$** | **$1.500000$** | **$+0.334695$** | **Inflection Point** |
   | $10.0$ | $+2.302585$ | $+0.230259$ | Leveling toward zero |
   | $100.0$ | $+4.605170$ | $+0.046052$ | Approaching horizontal asymptote |

   The numerical table matches all derived extrema, intercepts, and asymptotic behaviors.
