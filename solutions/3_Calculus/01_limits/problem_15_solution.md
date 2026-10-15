# Solution to Exercise 15: Observation Versus Proof

## 1. Problem Statement

1. **Selection:**
   - **Sequence:** Choose $a_n = \sqrt{n^2 + 5n} - n$ (from Exercise 3).
   - **Function:** Choose $f(x) = \frac{x^2 - 4x + 3}{x - 3}$ as $x \to 3$ (from Exercise 7).

2. **Empirical Investigation:**
   - For the sequence, compute values for increasingly large $n$.
   - For the function, compute a table of values approaching $x = 3$ from both the left ($x \to 3^-$) and the right ($x \to 3^+$).
   - Sketch the geometric and graphical behavior of both objects.

3. **Critical Comparative Analysis:**
   - Compare numerical observations with the rigorous analytical limits.
   - Explain why a finite number of calculations, numerical simulations, or graphical sketches cannot constitute a mathematical proof of a limit.

---

## 2. Theoretical Background and Concepts

### 2.1 The Rigorous Definitions of Limits

1. **Limit of a Sequence ($\varepsilon$-$N$ Definition):**
   $$
   \lim_{n \to \infty} a_n = L \iff \forall \varepsilon > 0, \; \exists N \in \mathbb{N} \; \text{such that} \; \forall n > N, \; |a_n - L| < \varepsilon
   $$
   The statement requires that **every** single term past index $N$ remains within the band $(L - \varepsilon, L + \varepsilon)$ for **arbitrarily small** $\varepsilon > 0$.

2. **Limit of a Function ($\varepsilon$-$\delta$ Definition):**
   $$
   \lim_{x \to c} f(x) = L \iff \forall \varepsilon > 0, \; \exists \delta > 0 \; \text{such that} \; 0 < |x - c| < \delta \implies |f(x) - L| < \varepsilon
   $$
   The statement requires that the function value $f(x)$ falls within $(L - \varepsilon, L + \varepsilon)$ for **all** infinitely many real numbers in the punctured neighborhood $0 < |x - c| < \delta$.

### 2.2 Deductive Proof vs. Empirical Induction

- **Empirical Observation (Induction):**
  Observes a finite sample of points $\{x_1, x_2, \dots, x_k\}$ or $\{a_1, a_2, \dots, a_k\}$ and infers a global trend. In natural sciences, empirical induction provides strong evidence; in mathematics, it can never establish a theorem because infinitely many unobserved points exist.
- **Analytical Proof (Deduction):**
  Constructs a logically unbreakable chain from axioms, algebraic identities, and inequality laws that guarantees the property holds across the entirety of the infinite domain.

### 2.3 Classical Traps of Purely Numerical Observation

1. **Oscillation in the Gap:** A function like $g(x) = \sin\left(\frac{\pi}{x}\right)$ satisfies $g(1/k) = 0$ for all integers $k$. Sampling only $x = 1, 1/2, 1/3, \dots$ suggests $\lim_{x \to 0} g(x) = 0$, yet the true limit does not exist (the function oscillates infinitely between $-1$ and $+1$).
2. **Delayed Divergence:** A sequence like $s_n = \sum_{k=1}^n \frac{1}{k}$ (the harmonic series) grows so slowly that $s_{1000} \approx 7.485$ and $s_{10^6} \approx 14.39$, tempting an observer to guess it converges to a finite bound, whereas it actually diverges to $+\infty$.
3. **Catastrophic Cancellation & Numerical Artifacts:** Finite-precision floating-point arithmetic introduces rounding errors that can corrupt calculations at extreme scales.

---

## 3. Detailed Step-by-Step Solution

### Part A: Numerical and Graphical Exploration of Sequence $a_n = \sqrt{n^2 + 5n} - n$

#### 1. Analytical Benchmark
From Exercise 3, rationalizing via the conjugate yields:
$$
a_n = \frac{(\sqrt{n^2 + 5n} - n)(\sqrt{n^2 + 5n} + n)}{\sqrt{n^2 + 5n} + n} = \frac{5n}{\sqrt{n^2 + 5n} + n} = \frac{5}{\sqrt{1 + \frac{5}{n}} + 1}
$$
Taking $n \to \infty$:
$$
\lim_{n \to \infty} a_n = \frac{5}{\sqrt{1 + 0} + 1} = \frac{5}{2} = 2.5
$$

#### 2. Table of Numerical Values
| $n$ | $\sqrt{n^2 + 5n}$ | $a_n = \sqrt{n^2 + 5n} - n$ | Deviation $|a_n - 2.5|$ |
|:---|:---|:---|:---|
| $1$ | $\sqrt{6} \approx 2.44948974$ | $1.44948974$ | $1.05051026$ |
| $2$ | $\sqrt{14} \approx 3.74165739$ | $1.74165739$ | $0.75834261$ |
| $5$ | $\sqrt{50} \approx 7.07106781$ | $2.07106781$ | $0.42893219$ |
| $10$ | $\sqrt{150} \approx 12.24744871$ | $2.24744871$ | $0.25255129$ |
| $50$ | $\sqrt{2750} \approx 52.44044241$ | $2.44044241$ | $0.05955759$ |
| $100$ | $\sqrt{10500} \approx 102.46950766$ | $2.46950766$ | $0.03049234$ |
| $1\,000$ | $\sqrt{1005000} \approx 1002.49688279$ | $2.49688279$ | $0.00311721$ |
| $10\,000$ | $\sqrt{100050000} \approx 10002.49968754$ | $2.49968754$ | $0.00031246$ |
| $100\,000$ | $\sqrt{10000500000} \approx 100002.49996875$ | $2.49996875$ | $0.00003125$ |

#### 3. Graphical Sketch of the Sequence
```text
  a_n
   ^
3.0|
   |
2.5| - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - Horizontal Asymptote: L = 2.5
   |                         *    *    *    *    *    *   (approaching 2.5 from below)
2.0|                 *
   |           *
1.5|     *
   |  *
1.0+------------------------------------------------------------> n
   0     10        50       100                 1000
```
The sequence values increase monotonically and appear visually bounded above by $2.5$.

---

### Part B: Numerical and Graphical Exploration of Function $f(x) = \frac{x^2 - 4x + 3}{x - 3}$

#### 1. Analytical Benchmark
From Exercise 7, factoring the numerator for $x \neq 3$:
$$
f(x) = \frac{(x - 3)(x - 1)}{x - 3} = x - 1
$$
Taking the two-sided limit as $x \to 3$:
$$
\lim_{x \to 3} f(x) = \lim_{x \to 3} (x - 1) = 3 - 1 = 2
$$
The domain is $\mathcal{D}_f = \mathbb{R} \setminus \{3\}$. At $x = 3$, $f(x)$ is undefined; the graph has a removable discontinuity (a "hole") at the point $(3, 2)$.

#### 2. Table of Numerical Values Approaching $x = 3$
- **Approaching from the Left ($x \to 3^-$):**
  | $x$ | $x^2 - 4x + 3$ | $x - 3$ | $f(x) = \frac{x^2-4x+3}{x-3}$ | Error $|f(x) - 2|$ |
  |:---|:---|:---|:---|:---|
  | $2.5$ | $-0.75$ | $-0.5$ | $1.500000$ | $0.500000$ |
  | $2.9$ | $-0.19$ | $-0.1$ | $1.900000$ | $0.100000$ |
  | $2.99$ | $-0.0199$ | $-0.01$ | $1.990000$ | $0.010000$ |
  | $2.999$ | $-0.001999$ | $-0.001$ | $1.999000$ | $0.001000$ |
  | $2.9999$ | $-0.00019999$ | $-0.0001$ | $1.999900$ | $0.000100$ |

- **Approaching from the Right ($x \to 3^+$):**
  | $x$ | $x^2 - 4x + 3$ | $x - 3$ | $f(x) = \frac{x^2-4x+3}{x-3}$ | Error $|f(x) - 2|$ |
  |:---|:---|:---|:---|:---|
  | $3.5$ | $+1.25$ | $+0.5$ | $2.500000$ | $0.500000$ |
  | $3.1$ | $+0.21$ | $+0.1$ | $2.100000$ | $0.100000$ |
  | $3.01$ | $+0.0201$ | $+0.01$ | $2.010000$ | $0.010000$ |
  | $3.001$ | $+0.002001$ | $+0.001$ | $2.001000$ | $0.001000$ |
  | $3.0001$ | $+0.00020001$ | $+0.0001$ | $2.000100$ | $0.000100$ |

#### 3. Graphical Sketch of the Function
```text
   y
   ^
4  |                      /
   |                     /
3  |                    /
   |                   o  (3, 2) Removable singularity (Hole)
2  |                  /
   |                 /
1  |                /
   |               /
0  +--------------+---------------> x
  -1             1   2   3   4
```
For all $x \neq 3$, the graph of $f(x)$ is the straight line $y = x - 1$. As $x \to 3$ from either direction, the points on the line approach the coordinates $(3, 2)$.

---

### Part C: Comparison and Epistemological Analysis: Why Observation $\neq$ Proof

#### 1. Comparison of Results
- For the sequence: The empirical values $1.449 \to 2.247 \to 2.469 \to 2.4996 \to 2.49996$ strongly suggest a limit of $2.5$. The analytical conjugate proof confirms that the limit is exactly $\frac{5}{2}$.
- For the function: The values from left ($1.9, 1.99, 1.999, \dots$) and right ($2.1, 2.01, 2.001, \dots$) symmetrically converge toward $2$. The algebraic cancellation proof confirms that the limit is precisely $2$.

#### 2. Fundamental Reasons Why Finite Calculations and Sketches Do Not Constitute a Proof

1. **The Universal Quantifier ($\forall$) vs. Finite Sampling:**
   The definition of limit demands that the distance condition hold for **all** $n > N$ or **all** $0 < |x - c| < \delta$.
   - A numerical table tests only a finite set of points $\{x_1, x_2, \dots, x_k\}$ (here, 10 points).
   - Even if $10^{100}$ points were tested, there remain uncountably many untested points in $(c - \delta, c + \delta)$.
   - A function can behave smoothly at the tested sample points while oscillating wildly between them.

2. **The "Microscopic Oscillation" Counterexample:**
   Consider the function:
   $$
   h(x) = \frac{x^2 - 4x + 3}{x - 3} + \sin\left(\frac{10^{12}\pi}{x - 3}\right)
   $$
   If sampled at points where $\frac{10^{12}}{x - 3}$ is an integer (such as $x = 3 + 10^{-6}, 3 + 10^{-8}$), the sine term vanishes completely, yielding values identical to our table ($2.000000\dots$). Yet, as $x \to 3$, $h(x)$ oscillates between $1$ and $3$, so the limit does not even exist! A finite table is blind to high-frequency oscillation.

3. **Delayed Departure and Pseudo-Limits:**
   Consider the sequence:
   $$
   b_n = \sqrt{n^2 + 5n} - n + \frac{1}{1 + e^{10^6 - n}}
   $$
   For all $n \le 10^5$, $e^{10^6 - n}$ is astronomical, so $b_n \approx a_n \to 2.5$. Any human or computer testing $n \le 100\,000$ will observe convergence to $2.5000$. Yet for $n \gg 10^6$, the added term equals $1$, so the true limit is $3.5$. No finite calculation can rule out such delayed transitions.

4. **Floating-Point Arithmetic and Catastrophic Cancellation:**
   If we evaluate $a_n = \sqrt{n^2 + 5n} - n$ on a computer using standard double-precision (IEEE 754, ~16 decimal digits) for $n = 10^{16}$:
   $$
   n^2 = 10^{32}, \quad 5n = 5 \times 10^{16}
   $$
   Since $10^{32} + 5 \times 10^{16}$ rounds to $10^{32}$ in 16-digit floating-point, the computer calculates $\sqrt{10^{32}} - 10^{16} = 10^{16} - 10^{16} = 0$.
   Thus, numerical computation falsely outputs that $a_n \to 0$ for very large $n$! Only deductive analytical algebra reveals the correct limit $2.5$.

5. **Sketches Lack Infinite Precision:**
   A drawing has a finite physical resolution (pen stroke width, pixel size). A graph cannot depict an open interval of radius $\delta = 10^{-100}$ around a puncture, nor can it show the infinite tail beyond $n = 10^{1000}$. A sketch illustrates intuition, but cannot guarantee behavior across infinite domains.

---

## 4. Verification and Consistency Checks

1. **Formal $\varepsilon$-$N$ Proof for $a_n$:**
   We verify that $|a_n - 2.5| < \varepsilon$ can always be guaranteed.
   From Part A:
   $$
   |a_n - 2.5| = \left| \frac{5}{\sqrt{1 + 5/n} + 1} - \frac{5}{2} \right| = 5 \cdot \left| \frac{2 - (\sqrt{1 + 5/n} + 1)}{2(\sqrt{1 + 5/n} + 1)} \right| = \frac{5(\sqrt{1 + 5/n} - 1)}{2(\sqrt{1 + 5/n} + 1)}
   $$
   Using $\sqrt{1 + u} - 1 \le \frac{u}{2}$ for $u \ge 0$:
   $$
   |a_n - 2.5| < \frac{5 \cdot (5 / 2n)}{2(1 + 1)} = \frac{25}{8n}
   $$
   Given any $\varepsilon > 0$, setting $N = \left\lceil \frac{25}{8\varepsilon} \right\rceil$ guarantees that for all $n > N$:
   $$
   |a_n - 2.5| < \frac{25}{8n} < \varepsilon
   $$
   This constitutes a complete, deductive mathematical proof.

2. **Formal $\varepsilon$-$\delta$ Proof for $f(x)$:**
   We want $|f(x) - 2| < \varepsilon$ whenever $0 < |x - 3| < \delta$.
   For $x \neq 3$:
   $$
   |f(x) - 2| = |(x - 1) - 2| = |x - 3|
   $$
   Given any $\varepsilon > 0$, simply choosing $\delta = \varepsilon$ guarantees:
   $$
   0 < |x - 3| < \delta \implies |f(x) - 2| = |x - 3| < \varepsilon
   $$
   This proves unconditionally that $\lim_{x \to 3} f(x) = 2$.
