# Solution to Exercise 11: An n-th Root

## 1. Problem Statement

Compute the limit of the sequence:
$$
\lim_{n \to \infty} \sqrt[n]{5^n + 2^n}
$$

1. Identify which exponential term dominates the expression as $n \to \infty$.
2. Compute the exact limit using both the factoring method and the Squeeze Theorem.
3. Explain why the algebraic transformation of exponential sums under an $n$-th root differs in form from the technique used for quotients of polynomials.

---

## 2. Theoretical Background and Concepts

1. **Hierarchy of Exponential Growth:**
   For any two bases $a > b > 0$, the ratio $\frac{b^n}{a^n} = \left(\frac{b}{a}\right)^n$ decays exponentially to zero:
   $$
   \lim_{n \to \infty} \left(\frac{b}{a}\right)^n = 0 \quad \left(\text{since } \frac{b}{a} < 1\right)
   $$
   Consequently, the term with the larger base ($a^n$) overwhelmingly dominates the sum $a^n + b^n$ for large $n$.

2. **The Squeeze Theorem for $n$-th Roots:**
   For any sum of positive exponential terms $\sum_{i=1}^k a_i^n$ with $M = \max(a_1, \dots, a_k)$:
   $$
   M^n \le a_1^n + a_2^n + \dots + a_k^n \le k \cdot M^n
   $$
   Taking the $n$-th root gives:
   $$
   M \le \sqrt[n]{a_1^n + \dots + a_k^n} \le M \sqrt[n]{k}
   $$
   Because $\lim_{n \to \infty} \sqrt[n]{k} = 1$ for any constant $k > 0$, the limit is identically $M$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Dominant Exponential Term

Compare the two terms $5^n$ and $2^n$:
- Since $5 > 2$, $5^n$ grows much faster than $2^n$.
- Ratio: $\frac{2^n}{5^n} = \left(\frac{2}{5}\right)^n = (0.4)^n \to 0$ as $n \to \infty$.
- Therefore, $5^n$ is the **dominant term**.

---

### Step 2: Method A — Factoring Out the Dominant Term

Factor $5^n$ out of the sum inside the radical:
$$
5^n + 2^n = 5^n \left(1 + \frac{2^n}{5^n}\right) = 5^n \left(1 + \left(\frac{2}{5}\right)^n\right)
$$

Apply the $n$-th root:
$$
\sqrt[n]{5^n + 2^n} = \sqrt[n]{5^n \left(1 + \left(\frac{2}{5}\right)^n\right)} = \sqrt[n]{5^n} \cdot \sqrt[n]{1 + \left(\frac{2}{5}\right)^n}
$$

Since $\sqrt[n]{5^n} = (5^n)^{1/n} = 5$ for all positive integers $n$:
$$
= 5 \cdot \left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n}
$$

Now evaluate the limit of the second factor:
- Let $u_n = \left(\frac{2}{5}\right)^n \to 0$ as $n \to \infty$.
- Then the base $1 + u_n \to 1 + 0 = 1$.
- The exponent is $\frac{1}{n} \to 0$.
- Because the base approaches $1$ and the exponent approaches $0$, the form is $1^0$, which is **not indeterminate**:
  $$
  \lim_{n \to \infty} \left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n} = 1^0 = 1
  $$

Multiplying by the leading factor:
$$
\lim_{n \to \infty} \sqrt[n]{5^n + 2^n} = 5 \cdot 1 = 5
$$

---

### Step 3: Method B — The Squeeze Theorem (Sandwich Rule)

1. **Construct the Lower Bound:**
   Since $2^n > 0$ for all $n \ge 1$:
   $$
   5^n < 5^n + 2^n \implies \sqrt[n]{5^n} < \sqrt[n]{5^n + 2^n} \implies 5 < \sqrt[n]{5^n + 2^n}
   $$

2. **Construct the Upper Bound:**
   Replace the smaller term $2^n$ with the dominant term $5^n$:
   $$
   5^n + 2^n < 5^n + 5^n = 2 \cdot 5^n
   $$
   Taking the $n$-th root:
   $$
   \sqrt[n]{5^n + 2^n} < \sqrt[n]{2 \cdot 5^n} = \sqrt[n]{2} \cdot \sqrt[n]{5^n} = 5 \sqrt[n]{2}
   $$

3. **Combine the Inequalities:**
   $$
   5 < \sqrt[n]{5^n + 2^n} < 5 \sqrt[n]{2} \quad \text{for all } n \ge 1
   $$

4. **Take the Limit of the Bounds:**
   - Left bound: $\lim_{n \to \infty} 5 = 5$.
   - Right bound: $\lim_{n \to \infty} \left(5 \sqrt[n]{2}\right) = 5 \cdot \lim_{n \to \infty} 2^{1/n} = 5 \cdot 2^0 = 5 \cdot 1 = 5$.

By the Squeeze Theorem, the sequence must converge to the same value:
$$
\lim_{n \to \infty} \sqrt[n]{5^n + 2^n} = 5
$$

---

### Step 4: Why the Transformation Differs from Polynomial Quotients

1. **Polynomial Quotients vs. Exponential Radicals:**
   - In a **polynomial quotient** $\frac{P(n)}{Q(n)}$, we have an algebraic fraction of powers of $n$. We divide numerator and denominator by $n^k$. This produces rational terms like $\frac{1}{n}$ that vanish by simple division.
   - In an **exponential $n$-th root** $\sqrt[n]{a^n + b^n}$, the variable $n$ appears in the **exponent** as well as in the **root index**.
2. **The Inversion Mechanism:**
   - The operation of taking the $n$-th root is the inverse of raising to the $n$-th power: $\sqrt[n]{a^n} = a$.
   - Pulling $a^n$ out from under an $n$-th radical eliminates the $n$ completely from the leading factor, leaving a pure constant $a$.
   - The remainder term $(1 + (b/a)^n)^{1/n}$ has the structure $(1 + \text{vanishing})^{\text{vanishing}} \to 1^0 = 1$.
   - Thus, while polynomial dominance relies on dividing by $n^k$, exponential dominance relies on factoring out $a^n$ to cancel the root index $n$ entirely.

---

## 4. Verification and Consistency Checks

1. **Numerical Sequence Values:**
   - $n = 1$: $\sqrt[1]{5 + 2} = 7.0000$
   - $n = 2$: $\sqrt{25 + 4} = \sqrt{29} \approx 5.3852$
   - $n = 5$: $\sqrt[5]{3125 + 32} = \sqrt[5]{3157} \approx 5.0203$
   - $n = 10$: $\sqrt[10]{5^{10} + 2^{10}} = \sqrt[10]{9765625 + 1024} \approx 5.0005$
   - $n = 20$: $\sqrt[20]{5^{20} + 2^{20}} \approx 5.00000005$
   The sequence values strictly decrease and converge rapidly to $5.0000$.

2. **Generalization Check for $k$ Exponential Terms:**
   For any finite sum $\lim_{n \to \infty} \sqrt[n]{a_1^n + a_2^n + \dots + a_k^n} = \max(a_1, a_2, \dots, a_k)$.
   Here $\max(5, 2) = 5$, verifying the result.
