# Solution to Problem 9: An Oblique Asymptote

## 1. Problem Statement

Analyze the asymptotes of the rational function:
$$
f(x) = \frac{x^2 + 1}{x - 1}
$$

1. Determine the domain $\mathcal{D}_f$ and identify any vertical asymptotes.
2. Perform polynomial division to express $f(x)$ in the form $f(x) = (mx + b) + \frac{R}{x - 1}$.
3. Rigorously establish the equation of the oblique (slant) asymptote.
4. Explain why the remainder term vanishes for large $|x|$ and explain the geometric meaning of its sign as $x \to +\infty$ and $x \to -\infty$.
5. Verify the oblique asymptote using the standard limit formulas for slope $m$ and intercept $b$.

---

## 2. Theoretical Background and Concepts

1. **Condition for an Oblique Asymptote:**
   A rational function $\frac{P(x)}{Q(x)}$ possesses an oblique asymptote if and only if the degree of the numerator is exactly one higher than the degree of the denominator:
   $$
   \deg(P) = \deg(Q) + 1
   $$

2. **Definition of an Asymptote:**
   A straight line $y = mx + b$ is an asymptote of $y = f(x)$ as $x \to \infty$ (or $x \to -\infty$) if and only if the vertical distance between the curve and the line approaches zero:
   $$
   \lim_{x \to \pm\infty} [f(x) - (mx + b)] = 0
   $$

3. **General Limit Formulas for Oblique Asymptotes:**
   If the limits exist as finite real numbers:
   $$
   m = \lim_{x \to \pm\infty} \frac{f(x)}{x}
   $$
   $$
   b = \lim_{x \to \pm\infty} [f(x) - mx]
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and Vertical Asymptote

1. **Domain:**
   Setting the denominator to zero:
   $$
   x - 1 = 0 \iff x = 1
   $$
   $$
   \mathcal{D}_f = \mathbb{R} \setminus \{1\} = (-\infty, 1) \cup (1, \infty)
   $$

2. **Vertical Asymptote at $x = 1$:**
   Evaluate the one-sided limits as $x \to 1$:
   - As $x \to 1^-$ ($x < 1$): Numerator $x^2 + 1 \to 2$, Denominator $x - 1 \to 0^-$.
     $$
     \lim_{x \to 1^-} \frac{x^2 + 1}{x - 1} = \frac{2}{0^-} = -\infty
     $$
   - As $x \to 1^+$ ($x > 1$): Numerator $x^2 + 1 \to 2$, Denominator $x - 1 \to 0^+$.
     $$
     \lim_{x \to 1^+} \frac{x^2 + 1}{x - 1} = \frac{2}{0^+} = +\infty
     $$
   The vertical line **$x = 1$** is a vertical asymptote.

---

### Step 2: Polynomial Division

Perform polynomial division of the numerator $x^2 + 1$ by the denominator $x - 1$:
$$
\begin{array}{r@{\quad}l}
  x + 1 & \text{(Quotient)} \\[-2pt]
  x - 1 \enclose{longdiv}{x^2 + 0x + 1} & \\[-2pt]
  \underline{-(x^2 - x)\phantom{+1}} & \\[-2pt]
  x + 1 & \\[-2pt]
  \underline{-(x - 1)} & \\[-2pt]
  2 & \text{(Remainder)}
\end{array}
$$

Alternatively, by synthetic manipulation:
$$
\frac{x^2 + 1}{x - 1} = \frac{(x^2 - 1) + 2}{x - 1} = \frac{(x - 1)(x + 1) + 2}{x - 1} = x + 1 + \frac{2}{x - 1}
$$

Thus, the decomposed form is:
$$
f(x) = (x + 1) + \frac{2}{x - 1}
$$

---

### Step 3: Identification of the Oblique Asymptote

From the decomposed form, consider the linear function:
$$
y = x + 1
$$
Subtract this linear function from $f(x)$:
$$
f(x) - (x + 1) = \frac{2}{x - 1}
$$

Take the limit as $x \to \pm\infty$:
$$
\lim_{x \to +\infty} [f(x) - (x + 1)] = \lim_{x \to +\infty} \frac{2}{x - 1} = 0
$$
$$
\lim_{x \to -\infty} [f(x) - (x + 1)] = \lim_{x \to -\infty} \frac{2}{x - 1} = 0
$$

By definition, the line:
$$
\mathbf{y = x + 1}
$$
is the **oblique (slant) asymptote** of $f(x)$ in both the positive and negative directions.

---

### Step 4: Why the Remainder Term Vanishes and Its Geometric Meaning

1. **Why the Term Vanishes:**
   In the remainder term $\frac{2}{x - 1}$, the numerator is fixed at $2$, while the denominator $|x - 1|$ grows arbitrarily large as $|x| \to \infty$.
   $$
   \lim_{|x| \to \infty} \left|\frac{2}{x - 1}\right| = \frac{2}{\infty} = 0
   $$
   As a consequence, the linear part $x + 1$ becomes the overwhelmingly dominant term governing the value of $f(x)$, while the rational remainder $\frac{2}{x - 1}$ shrinks to an imperceptible correction.

2. **Geometric Significance of the Sign of the Remainder:**
   The difference $d(x) = f(x) - (x + 1) = \frac{2}{x - 1}$ represents the signed vertical displacement from the asymptote to the curve:
   - **For $x > 1$ (including $x \to +\infty$):**
     $$
     x - 1 > 0 \implies \frac{2}{x - 1} > 0 \implies f(x) > x + 1
     $$
     The curve $y = f(x)$ lies **strictly above** the asymptote $y = x + 1$, approaching it from above.
   - **For $x < 1$ (including $x \to -\infty$):**
     $$
     x - 1 < 0 \implies \frac{2}{x - 1} < 0 \implies f(x) < x + 1
     $$
     The curve $y = f(x)$ lies **strictly below** the asymptote $y = x + 1$, approaching it from below.
   - Because the remainder $\frac{2}{x - 1} \neq 0$ for all real $x$, the curve **never intersects** its oblique asymptote.

---

## 4. Verification and Consistency Checks

1. **General Limit Formulas Verification:**
   - **Slope $m$:**
     $$
     m = \lim_{x \to \infty} \frac{f(x)}{x} = \lim_{x \to \infty} \frac{x^2 + 1}{x(x - 1)} = \lim_{x \to \infty} \frac{x^2 + 1}{x^2 - x} = \lim_{x \to \infty} \frac{1 + 1/x^2}{1 - 1/x} = 1
     $$
   - **$y$-Intercept $b$:**
     $$
     b = \lim_{x \to \infty} [f(x) - mx] = \lim_{x \to \infty} \left[\frac{x^2 + 1}{x - 1} - x\right] = \lim_{x \to \infty} \frac{x^2 + 1 - x(x - 1)}{x - 1}
     $$
     $$
     b = \lim_{x \to \infty} \frac{x^2 + 1 - x^2 + x}{x - 1} = \lim_{x \to \infty} \frac{x + 1}{x - 1} = 1
     $$
   The line is $y = mx + b = 1x + 1 = x + 1$, confirming the polynomial division result.

2. **Numerical Distance Verification:**
   | $x$ | $f(x) = \frac{x^2+1}{x-1}$ | Asymptote $y = x + 1$ | Vertical Distance $\frac{2}{x-1}$ | Position |
   |:---|:---:|:---:|:---:|:---|
   | $-100$ | $-98.980198$ | $-99.000000$ | $-0.019802$ | Below asymptote |
   | $-10$ | $-9.181818$ | $-9.000000$ | $-0.181818$ | Below asymptote |
   | $+10$ | $+11.222222$ | $+11.000000$ | $+0.222222$ | Above asymptote |
   | $+100$ | $+101.020202$ | $+101.000000$ | $+0.020202$ | Above asymptote |
   | $+1000$ | $+1001.002002$ | $+1001.000000$ | $+0.002002$ | Above asymptote |

   The vertical distance shrinks precisely as $\frac{2}{x-1}$, confirming convergence.
