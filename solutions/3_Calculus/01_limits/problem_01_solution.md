# Solution to Exercise 1: Dominant Terms in a Sequence

## 1. Problem Statement

Compute the limit of the rational sequence:
$$
\lim_{n \to \infty} \frac{4n^2 - 3n + 1}{2n^2 + 5n - 7}
$$

1. Carry out the algebraic evaluation of the limit.
2. Explain thoroughly why the highest-degree (dominant) terms in the numerator and denominator uniquely dictate the final result as $n \to \infty$.

---

## 2. Theoretical Background and Concepts

1. **Limit of a Sequence of Real Numbers:**
   A sequence $(a_n)$ converges to a real limit $L$, written $\lim_{n \to \infty} a_n = L$, if for every $\varepsilon > 0$ there exists an index $N \in \mathbb{N}$ such that for all $n > N$:
   $$
   |a_n - L| < \varepsilon
   $$

2. **The Principle of Dominant Terms:**
   A polynomial $P(n) = a_k n^k + a_{k-1} n^{k-1} + \dots + a_0$ with $a_k \ne 0$ is governed by its leading term $a_k n^k$ for large $n$.
   Every lower-order term $a_j n^j$ ($j < k$) becomes negligible in relative proportion:
   $$
   \lim_{n \to \infty} \frac{a_j n^j}{a_k n^k} = \frac{a_j}{a_k} \lim_{n \to \infty} \frac{1}{n^{k-j}} = 0
   $$

3. **Limit of a Rational Sequence:**
   For the quotient of two polynomials of identical degree $k$:
   $$
   \lim_{n \to \infty} \frac{a_k n^k + \dots + a_0}{b_k n^k + \dots + b_0} = \frac{a_k}{b_k}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Highest Power of $n$

- In the numerator $P(n) = 4n^2 - 3n + 1$, the highest power of $n$ is $n^2$, with leading coefficient $4$.
- In the denominator $Q(n) = 2n^2 + 5n - 7$, the highest power of $n$ is $n^2$, with leading coefficient $2$.

Both polynomials have degree $2$.

---

### Step 2: Factor Out the Dominant Power $n^2$

Factor $n^2$ out of both the numerator and denominator:
$$
\frac{4n^2 - 3n + 1}{2n^2 + 5n - 7} = \frac{n^2 \left( 4 - \frac{3}{n} + \frac{1}{n^2} \right)}{n^2 \left( 2 + \frac{5}{n} - \frac{7}{n^2} \right)}
$$

Cancel the non-zero common factor $n^2$ (valid for all $n \ge 1$):
$$
= \frac{4 - \frac{3}{n} + \frac{1}{n^2}}{2 + \frac{5}{n} - \frac{7}{n^2}}
$$

---

### Step 3: Evaluate the Limit of Individual Terms

Using the fundamental limit property $\lim_{n \to \infty} \frac{1}{n^p} = 0$ for any $p > 0$:
- In the numerator:
  $$
  \lim_{n \to \infty} \left(4 - \frac{3}{n} + \frac{1}{n^2}\right) = 4 - 3(0) + 0 = 4
  $$
- In the denominator:
  $$
  \lim_{n \to \infty} \left(2 + \frac{5}{n} - \frac{7}{n^2}\right) = 2 + 5(0) - 7(0) = 2
  $$

---

### Step 4: Apply the Quotient Rule for Limits

Since the limit of the denominator is non-zero ($2 \ne 0$), the limit of the quotient is the quotient of the limits:
$$
\lim_{n \to \infty} \frac{4n^2 - 3n + 1}{2n^2 + 5n - 7} = \frac{\lim_{n \to \infty} \left(4 - \frac{3}{n} + \frac{1}{n^2}\right)}{\lim_{n \to \infty} \left(2 + \frac{5}{n} - \frac{7}{n^2}\right)} = \frac{4}{2} = 2
$$

---

### Step 5: Why the Highest-Degree Terms Determine the Result

1. **Relative Growth Rate:**
   As $n$ grows, $n^2$ grows orders of magnitude faster than $n$ and constants. For instance:
   - At $n = 10^3$: $n^2 = 10^6$, whereas $n = 10^3$. The term $4n^2 = 4{,}000{,}000$, while $-3n + 1 = -2{,}999$. The leading term accounts for over $99.92\%$ of the numerator.
   - At $n = 10^6$: $n^2 = 10^{12}$, while $n = 10^6$. The subdominant terms contribute less than $0.0001\%$ of the total value.
2. **Vanishing Relative Errors:**
   Dividing numerator and denominator by $n^2$ demonstrates that the lower-order terms contribute fractions proportional to $\frac{1}{n}$ and $\frac{1}{n^2}$, which decay to zero in the limit.
3. **Asymptotic Equivalence:**
   We write $4n^2 - 3n + 1 \sim 4n^2$ and $2n^2 + 5n - 7 \sim 2n^2$ as $n \to \infty$. Thus:
   $$
   \lim_{n \to \infty} \frac{4n^2 - 3n + 1}{2n^2 + 5n - 7} = \lim_{n \to \infty} \frac{4n^2}{2n^2} = \frac{4}{2} = 2
   $$

---

## 4. Verification and Consistency Checks

1. **Numerical Sequence Values:**
   - For $n = 10$:
     $$
     a_{10} = \frac{4(100) - 30 + 1}{2(100) + 50 - 7} = \frac{371}{243} \approx 1.5267
     $$
   - For $n = 100$:
     $$
     a_{100} = \frac{4(10000) - 300 + 1}{2(10000) + 500 - 7} = \frac{39701}{20493} \approx 1.9373
     $$
   - For $n = 1000$:
     $$
     a_{1000} = \frac{4(10^6) - 3000 + 1}{2(10^6) + 5000 - 7} = \frac{3997001}{2004993} \approx 1.9935
     $$
   - For $n = 10000$:
     $$
     a_{10000} = \frac{399970001}{200049993} \approx 1.99935
     $$
   The sequence values monotonically approach $2.0000$ from below.

2. **Algebraic Difference Check:**
   $$
   a_n - 2 = \frac{4n^2 - 3n + 1}{2n^2 + 5n - 7} - 2 = \frac{4n^2 - 3n + 1 - 2(2n^2 + 5n - 7)}{2n^2 + 5n - 7} = \frac{-13n + 15}{2n^2 + 5n - 7}
   $$
   Notice that the difference has degree $1$ in the numerator and degree $2$ in the denominator:
   $$
   \lim_{n \to \infty} (a_n - 2) = \lim_{n \to \infty} \frac{-13n + 15}{2n^2 + 5n - 7} = 0
   $$
   This proves that $a_n \to 2$ with error decaying at rate $\mathcal{O}(1/n)$.
