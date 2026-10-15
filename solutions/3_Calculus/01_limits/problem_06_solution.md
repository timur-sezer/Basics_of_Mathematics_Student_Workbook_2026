# Solution to Exercise 6: From a Sequence to a Function — Limit at Infinity

## 1. Problem Statement

Compute the limit of the rational function at infinity:
$$
\lim_{x \to \infty} \frac{3x^2 - x + 1}{5x^2 + 4x - 2}
$$

1. Evaluate the limit using algebraic reduction.
2. Compare the computational method with the sequence limit in Exercise 1.
3. Explain what fundamentally changes when transitioning from a discrete integer index $n \in \mathbb{N}$ to a continuous real variable $x \in \mathbb{R}$, and what remains algebraically and conceptually identical.

---

## 2. Theoretical Background and Concepts

1. **Limit of a Function at Infinity:**
   Let $f: (a, \infty) \to \mathbb{R}$. We write $\lim_{x \to \infty} f(x) = L$ if for every $\varepsilon > 0$, there exists a real threshold $M > 0$ such that for all $x > M$:
   $$
   |f(x) - L| < \varepsilon
   $$

2. **Heine's Characterization of Function Limits:**
   Eduard Heine's theorem states that $\lim_{x \to \infty} f(x) = L$ if and only if for **every** sequence $(x_n)_{n=1}^\infty$ of real numbers such that $\lim_{n \to \infty} x_n = \infty$, the corresponding image sequence satisfies:
   $$
   \lim_{n \to \infty} f(x_n) = L
   $$
   This establishes a direct bridge between the discrete limits of sequences and continuous limits of functions.

3. **Invariance of Algebraic Operations:**
   Limit theorems for sums, products, and quotients hold identically for functions as they do for sequences. In particular, factoring out the highest power of the variable resolves indeterminate forms of type $\frac{\infty}{\infty}$ in both settings.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Factor Out the Dominant Power $x^2$

The highest power of $x$ in both the numerator $P(x) = 3x^2 - x + 1$ and denominator $Q(x) = 5x^2 + 4x - 2$ is $x^2$.
Factor $x^2$ out of both expressions for $x > 0$:
$$
\frac{3x^2 - x + 1}{5x^2 + 4x - 2} = \frac{x^2 \left(3 - \frac{1}{x} + \frac{1}{x^2}\right)}{x^2 \left(5 + \frac{4}{x} - \frac{2}{x^2}\right)}
$$

Cancel the non-zero factor $x^2$:
$$
= \frac{3 - \frac{1}{x} + \frac{1}{x^2}}{5 + \frac{4}{x} - \frac{2}{x^2}}
$$

---

### Step 2: Evaluate the Limit of Each Component

Using the basic rational function limit $\lim_{x \to \infty} \frac{1}{x^k} = 0$ for any $k > 0$:
- In the numerator:
  $$
  \lim_{x \to \infty} \left(3 - \frac{1}{x} + \frac{1}{x^2}\right) = 3 - 0 + 0 = 3
  $$
- In the denominator:
  $$
  \lim_{x \to \infty} \left(5 + \frac{4}{x} - \frac{2}{x^2}\right) = 5 + 0 - 0 = 5
  $$

---

### Step 3: Apply the Quotient Rule

Since the denominator limit is non-zero ($5 \ne 0$):
$$
\lim_{x \to \infty} \frac{3x^2 - x + 1}{5x^2 + 4x - 2} = \frac{\lim_{x \to \infty} \left(3 - \frac{1}{x} + \frac{1}{x^2}\right)}{\lim_{x \to \infty} \left(5 + \frac{4}{x} - \frac{2}{x^2}\right)} = \frac{3}{5} = 0.6
$$

Geometrically, the horizontal line $y = \frac{3}{5}$ is a **horizontal asymptote** of the function as $x \to \infty$.

---

### Step 4: Comparison Between Sequences and Functions

#### 1. What Remains the Same:
- **Algebraic Technique:** The procedure of identifying the dominant term of highest degree, factoring it out, canceling common powers, and utilizing the property that negative powers vanish ($\frac{1}{n^p} \to 0$ and $\frac{1}{x^p} \to 0$) is completely identical.
- **Limit Laws:** The algebraic rules for limits of sums, differences, products, and quotients are formally identical.
- **Asymptotic Equivalence:** In both cases, only the ratio of the leading coefficients $\frac{a_k}{b_k}$ determines the final limit.

#### 2. What Changes:
- **Domain Structure:**
  - In a sequence, the argument $n \in \mathbb{N} = \{1, 2, 3, \dots\}$ is **discrete**. There are gaps between values, and $n$ can only step through integers.
  - In a function, the argument $x \in \mathbb{R}$ is **continuous**. It traverses all uncountably many real values between any two integers, including irrationals.
- **Scope of the Condition:**
  - Proving a function limit $\lim_{x \to \infty} f(x) = L$ is a strictly stronger statement than proving a sequence limit $\lim_{n \to \infty} f(n) = L$.
  - A sequence limit checks values only at integer points. A function could potentially oscillate wildly between integers (for example, $g(x) = \sin(2\pi x)$ satisfies $g(n) = 0$ for all integers $n \in \mathbb{N}$, so $\lim_{n \to \infty} g(n) = 0$, but the continuous limit $\lim_{x \to \infty} g(x)$ does not exist).
  - By Heine's theorem, establishing the function limit $\lim_{x \to \infty} f(x) = \frac{3}{5}$ automatically guarantees that **any** sequence sampled from the function must converge to $\frac{3}{5}$.

---

## 4. Verification and Consistency Checks

1. **Numerical Check at Increasing Values of $x$:**
   - $x = 10$:
     $$
     f(10) = \frac{3(100) - 10 + 1}{5(100) + 40 - 2} = \frac{291}{538} \approx 0.54089
     $$
   - $x = 100$:
     $$
     f(100) = \frac{3(10000) - 100 + 1}{5(10000) + 400 - 2} = \frac{29901}{50398} \approx 0.59330
     $$
   - $x = 1000$:
     $$
     f(1000) = \frac{3(10^6) - 1000 + 1}{5(10^6) + 4000 - 2} = \frac{2999001}{5003998} \approx 0.59932
     $$
   - $x = 10000$:
     $$
     f(10000) \approx 0.59993
     $$
   The values steadily approach $\frac{3}{5} = 0.60000$.

2. **Residual Error Decay Rate:**
   Compute the difference $f(x) - \frac{3}{5}$:
   $$
   f(x) - \frac{3}{5} = \frac{3x^2 - x + 1}{5x^2 + 4x - 2} - \frac{3}{5} = \frac{5(3x^2 - x + 1) - 3(5x^2 + 4x - 2)}{5(5x^2 + 4x - 2)}
   $$
   $$
   = \frac{(15x^2 - 5x + 5) - (15x^2 + 12x - 6)}{25x^2 + 20x - 10} = \frac{-17x + 11}{25x^2 + 20x - 10}
   $$
   As $x \to \infty$, the error decays as $\mathcal{O}\left(\frac{1}{x}\right)$:
   $$
   \lim_{x \to \infty} \left(f(x) - \frac{3}{5}\right) = \lim_{x \to \infty} \frac{-17x}{25x^2} = 0 \quad (\checkmark)
   $$
