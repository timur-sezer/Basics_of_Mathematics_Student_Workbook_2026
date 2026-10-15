# Solution to Exercise 2: Different Growth Rates

## 1. Problem Statement

Compute the following two limits of rational sequences:
$$
L_1 = \lim_{n \to \infty} \frac{3n + 1}{n^2 + 4}, \qquad L_2 = \lim_{n \to \infty} \frac{2n^3 - n}{5n^2 + 1}
$$

1. Evaluate each limit rigorously.
2. Compare the two cases in terms of the relative growth rates of the numerator and denominator.
3. Formulate a general rule governing the limit of a rational sequence based on the degrees of the polynomials in the numerator and denominator.

---

## 2. Theoretical Background and Concepts

1. **Hierarchy of Polynomial Growth Rates:**
   For any two powers $p, q \in \mathbb{N}$:
   - If $p < q$, then $\lim_{n \to \infty} \frac{n^p}{n^q} = \lim_{n \to \infty} \frac{1}{n^{q-p}} = 0$. The denominator grows infinitely faster than the numerator.
   - If $p > q$, then $\lim_{n \to \infty} \frac{n^p}{n^q} = \lim_{n \to \infty} n^{p-q} = +\infty$. The numerator grows infinitely faster than the denominator.
   - If $p = q$, then $\lim_{n \to \infty} \frac{n^p}{n^q} = 1$. Both grow at the exact same rate.

2. **Standard Limit of a Rational Expression:**
   Let $P(n) = a_p n^p + \dots + a_0$ (with $a_p \ne 0$) and $Q(n) = b_q n^q + \dots + b_0$ (with $b_q \ne 0$). Then:
   $$
   \lim_{n \to \infty} \frac{P(n)}{Q(n)} = \lim_{n \to \infty} \frac{a_p n^p}{b_q n^q}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Evaluation of Limit $L_1 = \lim_{n \to \infty} \frac{3n + 1}{n^2 + 4}$

1. **Identify Polynomial Degrees:**
   - Numerator: $\deg(P) = 1$ (leading term $3n$).
   - Denominator: $\deg(Q) = 2$ (leading term $n^2$).
   - Notice that $\deg(P) < \deg(Q)$.

2. **Factor Out the Highest Power of the Denominator ($n^2$):**
   $$
   \frac{3n + 1}{n^2 + 4} = \frac{n^2 \left(\frac{3}{n} + \frac{1}{n^2}\right)}{n^2 \left(1 + \frac{4}{n^2}\right)} = \frac{\frac{3}{n} + \frac{1}{n^2}}{1 + \frac{4}{n^2}}
   $$

3. **Take the Limit as $n \to \infty$:**
   Since $\lim_{n \to \infty} \frac{1}{n} = 0$ and $\lim_{n \to \infty} \frac{1}{n^2} = 0$:
   $$
   L_1 = \lim_{n \to \infty} \frac{\frac{3}{n} + \frac{1}{n^2}}{1 + \frac{4}{n^2}} = \frac{0 + 0}{1 + 0} = \frac{0}{1} = 0
   $$

---

### Step 2: Evaluation of Limit $L_2 = \lim_{n \to \infty} \frac{2n^3 - n}{5n^2 + 1}$

1. **Identify Polynomial Degrees:**
   - Numerator: $\deg(P) = 3$ (leading term $2n^3$).
   - Denominator: $\deg(Q) = 2$ (leading term $5n^2$).
   - Notice that $\deg(P) > \deg(Q)$.

2. **Factor Out the Highest Power of the Denominator ($n^2$):**
   $$
   \frac{2n^3 - n}{5n^2 + 1} = \frac{n^2 \left(2n - \frac{1}{n}\right)}{n^2 \left(5 + \frac{1}{n^2}\right)} = \frac{n \left(2 - \frac{1}{n^2}\right)}{5 + \frac{1}{n^2}}
   $$

3. **Take the Limit as $n \to \infty$:**
   As $n \to \infty$, the term $\frac{2 - 1/n^2}{5 + 1/n^2} \to \frac{2}{5} > 0$, while the factor $n \to \infty$:
   $$
   L_2 = \lim_{n \to \infty} \left[ n \cdot \frac{2 - \frac{1}{n^2}}{5 + \frac{1}{n^2}} \right] = (+\infty) \cdot \frac{2}{5} = +\infty
   $$

The sequence diverges to positive infinity.

---

### Step 3: General Classification Rule for Rational Sequences

Let $P(n) = a_p n^p + \dots + a_0$ and $Q(n) = b_q n^q + \dots + b_0$ with leading coefficients $a_p \ne 0$ and $b_q \ne 0$:

$$
\lim_{n \to \infty} \frac{a_p n^p + \dots + a_0}{b_q n^q + \dots + b_0} = \begin{cases}
0, & \text{if } p < q \quad (\text{Denominator dominates}), \\
\frac{a_p}{b_q}, & \text{if } p = q \quad (\text{Balanced growth, finite non-zero limit}), \\
\operatorname{sgn}\left(\frac{a_p}{b_q}\right) \cdot \infty, & \text{if } p > q \quad (\text{Numerator dominates, divergent to } \pm\infty).
\end{cases}
$$

**Comparative Summary:**
- In $L_1$: $p = 1 < q = 2 \implies$ The quadratic denominator outgrows the linear numerator, crushing the ratio to $0$.
- In $L_2$: $p = 3 > q = 2 \implies$ The cubic numerator outgrows the quadratic denominator, driving the ratio to $+\infty$.

---

## 4. Verification and Consistency Checks

1. **Numerical Check for $L_1$:**
   - $n = 10$: $a_{10} = \frac{31}{104} \approx 0.2981$
   - $n = 100$: $a_{100} = \frac{301}{10004} \approx 0.03009$
   - $n = 1000$: $a_{1000} = \frac{3001}{1000004} \approx 0.003001$
   The values decay at rate $\approx \frac{3}{n} \to 0$.

2. **Numerical Check for $L_2$:**
   - $n = 10$: $b_{10} = \frac{2(1000) - 10}{5(100) + 1} = \frac{1990}{501} \approx 3.972$
   - $n = 100$: $b_{100} = \frac{2(10^6) - 100}{5(10^4) + 1} = \frac{1999900}{50001} \approx 39.997$
   - $n = 1000$: $b_{1000} \approx \frac{2 \cdot 10^9}{5 \cdot 10^6} = 0.4 \times 10^3 = 400$
   The values grow linearly proportional to $\frac{2}{5}n \to +\infty$.
