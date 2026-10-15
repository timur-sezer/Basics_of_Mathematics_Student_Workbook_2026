# Solution to Exercise 5: The Classical Limit Leading to the Number $e$

## 1. Problem Statement

Compute the classical limit of the sequence:
$$
\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n
$$

1. State the exact mathematical value of this limit.
2. Calculate numerical values of the sequence for several increasing values of $n$ ($n = 1, 2, 5, 10, 100, 1000, 10000$) and observe the trend.
3. Compare the observed numerical progression with the analytical limit.
4. Explain why computing a finite list of values does not constitute a rigorous mathematical proof of convergence or of the limit's value.

---

## 2. Theoretical Background and Concepts

1. **Definition of Euler's Number $e$:**
   The fundamental mathematical constant $e$ (Euler's number) is defined as the limit of the sequence $e_n = \left(1 + \frac{1}{n}\right)^n$ as $n \to \infty$:
   $$
   e := \lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n \approx 2.718281828459045...
   $$
   It is an irrational, transcendental number that serves as the base of the natural logarithm.

2. **The Indeterminate Form $1^\infty$:**
   As $n \to \infty$, the base $1 + \frac{1}{n} \to 1$ while the exponent $n \to \infty$.
   This is an **indeterminate form of type $1^\infty$**:
   - The base trying to equal $1$ pulls the product towards $1$ ($1^n = 1$).
   - The growing number of factors (each slightly greater than $1$) pulls the product towards $+\infty$ (since $c^n \to \infty$ for any fixed $c > 1$).
   - The delicate equilibrium between the shrinking excess $\frac{1}{n}$ and the linearly growing exponent $n$ yields the finite constant $e \approx 2.71828$.

3. **Monotone Convergence Theorem:**
   The sequence $e_n = \left(1 + \frac{1}{n}\right)^n$ is:
   - Strictly monotonically increasing ($e_n < e_{n+1}$ for all $n \ge 1$),
   - Bounded from above by $3$ ($e_n < 3$ for all $n \ge 1$).
   By the Monotone Convergence Theorem, any sequence that is increasing and bounded above is guaranteed to converge to a finite real limit.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Analytical Statement of the Limit

By the formal definition of Euler's number $e$:
$$
\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e
$$
Its numerical expansion to 10 decimal places is:
$$
e = 2.7182818285...
$$

---

### Step 2: Numerical Computations for Increasing $n$

Evaluate the sequence $e_n = \left(1 + \frac{1}{n}\right)^n$ for selected values of $n$:

1. **$n = 1$:**
   $$
   e_1 = \left(1 + \frac{1}{1}\right)^1 = 2^1 = 2.000000
   $$
2. **$n = 2$:**
   $$
   e_2 = \left(1 + \frac{1}{2}\right)^2 = (1.5)^2 = 2.250000
   $$
3. **$n = 5$:**
   $$
   e_5 = \left(1 + \frac{1}{5}\right)^5 = (1.2)^5 = 2.488320
   $$
4. **$n = 10$:**
   $$
   e_{10} = \left(1 + \frac{1}{10}\right)^{10} = (1.1)^{10} \approx 2.593742
   $$
5. **$n = 100$:**
   $$
   e_{100} = \left(1 + \frac{1}{100}\right)^{100} = (1.01)^{100} \approx 2.704814
   $$
6. **$n = 1000$:**
   $$
   e_{1000} = \left(1 + \frac{1}{1000}\right)^{1000} = (1.001)^{1000} \approx 2.716924
   $$
7. **$n = 10000$:**
   $$
   e_{10000} = \left(1 + \frac{1}{10000}\right)^{10000} = (1.0001)^{10000} \approx 2.718146
   $$

---

### Step 3: Comparison with the Analytical Value

| Index $n$ | Base $1 + 1/n$ | Value of $e_n$ | Difference from $e$ ($e - e_n$) | Relative Error |
| :---: | :---: | :---: | :---: | :---: |
| $1$ | $2.0000$ | $2.000000$ | $0.718282$ | $26.42\%$ |
| $2$ | $1.5000$ | $2.250000$ | $0.468282$ | $17.23\%$ |
| $5$ | $1.2000$ | $2.488320$ | $0.229962$ | $8.46\%$ |
| $10$ | $1.1000$ | $2.593742$ | $0.124540$ | $4.58\%$ |
| $100$ | $1.0100$ | $2.704814$ | $0.013468$ | $0.50\%$ |
| $1000$ | $1.0010$ | $2.716924$ | $0.001358$ | $0.05\%$ |
| $10000$ | $1.0001$ | $2.718146$ | $0.000136$ | $0.005\%$ |
| $\infty$ | $1.0000$ | $e \approx 2.718282$ | $0$ | $0\%$ |

The numerical progression shows that $e_n$ increases monotonically towards $e$, with the error decaying asymptotically as $\frac{e}{2n} \approx \frac{1.359}{n}$.

---

### Step 4: Why Numerical Observations Do Not Constitute a Proof

A finite table of computed values cannot serve as a mathematical proof for several reasons:

1. **Finite vs. Infinite Scope:**
   A calculation only verifies the property for finitely many chosen integers (e.g., $7$ values). It says nothing about what happens at $n = 10^{20}$ or $n = 10^{100}$. A sequence might appear to stabilize and then diverge or oscillate for astronomically large $n$.
2. **Deceptive Numerical Patterns:**
   - Consider the sequence $x_n = \left(1 + \frac{1}{n}\right)^n + \frac{\sin(n)}{1000}$. For $n \le 10$, its values closely track $e$, yet it oscillates and does not converge to $e$.
   - Consider the harmonic series $H_n = \sum_{k=1}^n \frac{1}{k}$. For $n = 1000$, $H_n \approx 7.485$; for $n = 10^6$, $H_n \approx 14.39$. It grows so slowly that a table of values might suggest it converges to a number around $15$ or $20$, whereas it actually diverges to $+\infty$.
3. **Rigorous Analytical Requirements:**
   To prove convergence, one must prove:
   - **Monotonicity:** $e_n < e_{n+1}$ for *all* $n \in \mathbb{N}$ (e.g., via Bernoulli's inequality or AM-GM inequality).
   - **Boundedness:** $e_n \le \sum_{k=0}^n \frac{1}{k!} < 1 + 1 + \sum_{k=2}^n \frac{1}{2^{k-1}} < 3$ for *all* $n$.
   Only the application of the Monotone Convergence Theorem guarantees the existence of the limit.

---

## 4. Verification and Consistency Checks

1. **Binomial Expansion Check:**
   By the Binomial Theorem:
   $$
   e_n = \left(1 + \frac{1}{n}\right)^n = \sum_{k=0}^n \binom{n}{k} \frac{1}{n^k} = 1 + 1 + \sum_{k=2}^n \frac{1}{k!} \left(1 - \frac{1}{n}\right)\left(1 - \frac{2}{n}\right)\dots\left(1 - \frac{k-1}{n}\right)
   $$
   As $n \to \infty$, each bracketed factor $\left(1 - \frac{j}{n}\right) \to 1$.
   Thus:
   $$
   \lim_{n \to \infty} e_n = \sum_{k=0}^\infty \frac{1}{k!} = 1 + 1 + \frac{1}{2} + \frac{1}{6} + \frac{1}{24} + \frac{1}{120} + \dots = e \quad (\checkmark)
   $$

2. **Logarithmic Asymptotics Check:**
   $$
   \ln(e_n) = n \ln\left(1 + \frac{1}{n}\right) = n \left( \frac{1}{n} - \frac{1}{2n^2} + \mathcal{O}\left(\frac{1}{n^3}\right) \right) = 1 - \frac{1}{2n} + \mathcal{O}\left(\frac{1}{n^2}\right)
   $$
   Taking the exponential:
   $$
   e_n = e^{1 - \frac{1}{2n} + \dots} = e \left(1 - \frac{1}{2n} + \dots\right) = e - \frac{e}{2n} + \mathcal{O}\left(\frac{1}{n^2}\right)
   $$
   For $n = 1000$, $\frac{e}{2000} \approx \frac{2.71828}{2000} \approx 0.001359$, which matches our computed error $e - e_{1000} = 0.001358$.
