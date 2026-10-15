# Solution to Exercise 4: Powers and Oscillation

## 1. Problem Statement

Analyze the asymptotic behavior of the following four sequences:
$$
a_n = \left(\frac{2}{3}\right)^n, \qquad b_n = \left(\frac{3}{2}\right)^n, \qquad c_n = (-1)^n, \qquad d_n = \frac{(-1)^n}{n}
$$

For each sequence:
1. Determine whether the sequence converges or diverges, and compute its limit if it exists.
2. Characterize the qualitative behavior (e.g., monotonic decay, unbounded growth, persistent oscillation, damped oscillation).
3. Explain why alternating signs (oscillation) do not automatically prevent a sequence from converging.

---

## 2. Theoretical Background and Concepts

1. **Limit of a Geometric Sequence $q^n$:**
   The behavior of the geometric progression $(q^n)_{n=1}^\infty$ depends strictly on the base $q \in \mathbb{R}$:
   - If $|q| < 1$: $\lim_{n \to \infty} q^n = 0$ (convergent to $0$).
   - If $q = 1$: $\lim_{n \to \infty} 1^n = 1$ (constant sequence, convergent).
   - If $q > 1$: $\lim_{n \to \infty} q^n = +\infty$ (unbounded, divergent).
   - If $q \le -1$: $(q^n)$ oscillates without bound or between signs (divergent).

2. **The Squeeze Theorem (Sandwich Theorem):**
   If three sequences satisfy $u_n \le v_n \le w_n$ for all $n \ge N$, and $\lim_{n \to \infty} u_n = \lim_{n \to \infty} w_n = L$, then:
   $$
   \lim_{n \to \infty} v_n = L
   $$
   In particular, if $|v_n| \le w_n$ and $w_n \to 0$, then $v_n \to 0$ regardless of any sign oscillation.

---

## 3. Detailed Step-by-Step Solution

### Sequence 1: $a_n = \left(\frac{2}{3}\right)^n$

1. **Classification and Limit:**
   This is a geometric sequence with base $q = \frac{2}{3}$.
   Since $|q| = \frac{2}{3} < 1$, each successive term is obtained by multiplying by a factor smaller than $1$:
   $$
   \lim_{n \to \infty} \left(\frac{2}{3}\right)^n = 0
   $$
2. **Behavior:**
   The sequence terms are strictly positive and **monotonically decreasing** towards $0$:
   $$
   \frac{2}{3} \approx 0.667, \quad \frac{4}{9} \approx 0.444, \quad \frac{8}{27} \approx 0.296, \quad \frac{16}{81} \approx 0.198, \dots \to 0
   $$
   **Conclusion:** **Convergent to $0$**.

---

### Sequence 2: $b_n = \left(\frac{3}{2}\right)^n$

1. **Classification and Limit:**
   This is a geometric sequence with base $q = \frac{3}{2} = 1.5$.
   Since $q > 1$, each step scales the term by a factor greater than $1$:
   $$
   \lim_{n \to \infty} \left(\frac{3}{2}\right)^n = +\infty
   $$
2. **Behavior:**
   The sequence displays **strictly monotonic exponential growth**:
   $$
   1.5, \quad 2.25, \quad 3.375, \quad 5.0625, \quad 7.59375, \dots \to +\infty
   $$
   **Conclusion:** **Divergent to $+\infty$**.

---

### Sequence 3: $c_n = (-1)^n$

1. **Classification and Limit:**
   The terms of the sequence alternate indefinitely:
   $$
   -1, \quad 1, \quad -1, \quad 1, \quad -1, \quad 1, \dots
   $$
   The subsequence of odd terms converges to $-1$ ($c_{2k-1} = -1 \to -1$), while the subsequence of even terms converges to $+1$ ($c_{2k} = 1 \to 1$).
2. **Behavior:**
   Because there exist two distinct subsequential limits ($-1 \ne 1$), the sequence fails Cauchy's convergence criterion (e.g., $|c_{n+1} - c_n| = 2$ for all $n$). It remains bounded within $[-1, 1]$ but oscillates eternally without settling on any single value.
   **Conclusion:** **Divergent by persistent oscillation**.

---

### Sequence 4: $d_n = \frac{(-1)^n}{n}$

1. **Classification and Limit:**
   The terms alternate in sign, but their denominators grow:
   $$
   -1, \quad \frac{1}{2} = 0.5, \quad -\frac{1}{3} \approx -0.333, \quad \frac{1}{4} = 0.25, \quad -\frac{1}{5} = -0.2, \dots
   $$
2. **Rigorous Proof via the Squeeze Theorem:**
   For all integers $n \ge 1$:
   $$
   -1 \le (-1)^n \le 1 \implies -\frac{1}{n} \le \frac{(-1)^n}{n} \le \frac{1}{n}
   $$
   Evaluate the bounding limits:
   $$
   \lim_{n \to \infty} \left(-\frac{1}{n}\right) = 0, \qquad \lim_{n \to \infty} \left(\frac{1}{n}\right) = 0
   $$
   Since both the lower and upper envelopes converge to $0$, by the Squeeze Theorem:
   $$
   \lim_{n \to \infty} \frac{(-1)^n}{n} = 0
   $$
3. **Behavior:**
   This sequence exhibits **damped oscillation**; the sign changes with every step, but the amplitude decays to zero as $\frac{1}{n}$.
   **Conclusion:** **Convergent to $0$**.

---

### Step 5: Why Oscillation Does Not Rule Out Convergence

- **Persistently Oscillating vs. Damped Oscillating:**
  A sequence oscillates whenever its terms change sign or alternate directions. However, convergence is determined exclusively by the **limit of the absolute error $|x_n - L|$**.
- In $(-1)^n$, the amplitude remains fixed at $|(-1)^n| = 1$. The oscillation is sustained and never collapses, so no limit exists.
- In $\frac{(-1)^n}{n}$, the alternating factor $(-1)^n$ is multiplied by an infinitesimal factor $\frac{1}{n}$. Because $\lim_{n \to \infty} \left|\frac{(-1)^n}{n}\right| = \lim_{n \to \infty} \frac{1}{n} = 0$, the envelope of oscillation squeezes down to a single point $0$.
- In general, any sequence of the form $a_n = \alpha_n \beta_n$ where $(\alpha_n)$ is bounded (even wildly oscillating) and $\lim_{n \to \infty} \beta_n = 0$ **always converges to $0$**.

---

## 4. Verification and Consistency Checks

1. **Comparative Overview Table:**

| Sequence | Explicit Formula | Bound Property | Monotonicity | Convergence Status | Limit $L$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $a_n$ | $(2/3)^n$ | Bounded ($0 < a_n \le 2/3$) | Strictly decreasing | **Convergent** | $0$ |
| $b_n$ | $(3/2)^n$ | Unbounded ($b_n \ge 1.5$) | Strictly increasing | **Divergent** | $+\infty$ |
| $c_n$ | $(-1)^n$ | Bounded ($-1 \le c_n \le 1$) | Non-monotonic (oscillates) | **Divergent** | Does not exist |
| $d_n$ | $(-1)^n/n$ | Bounded ($-1 \le d_n \le 0.5$) | Non-monotonic (damped) | **Convergent** | $0$ |

2. **$\varepsilon$-$N$ Proof for $d_n$:**
   Given any $\varepsilon > 0$, we require $\left|\frac{(-1)^n}{n} - 0\right| = \frac{1}{n} < \varepsilon \iff n > \frac{1}{\varepsilon}$.
   Choosing $N = \left\lceil \frac{1}{\varepsilon} \right\rceil$ guarantees that for all $n > N$, $|d_n - 0| < \varepsilon$.
   This confirms convergence to $0$.
