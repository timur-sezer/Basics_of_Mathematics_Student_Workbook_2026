# Solution to Exercise 10: Continuity of a Piecewise Function

## 1. Problem Statement

Given the piecewise-defined function:
$$
f(x) = \begin{cases}
ax + 1, & \text{for } x < 2, \\
x^2 - 1, & \text{for } x \ge 2.
\end{cases}
$$

1. Find the unique value of the real parameter $a$ such that $f(x)$ is continuous at $x = 2$.
2. Explicitly compute and compare the three fundamental quantities required for continuity:
   - The left-hand limit $\lim_{x \to 2^-} f(x)$,
   - The right-hand limit $\lim_{x \to 2^+} f(x)$,
   - The function value $f(2)$.

---

## 2. Theoretical Background and Concepts

1. **Definition of Continuity at a Point:**
   A function $f: D \to \mathbb{R}$ is continuous at a point $x_0 \in D$ if and only if:
   $$
   \lim_{x \to x_0} f(x) = f(x_0)
   $$
   For a piecewise function where the definition changes across $x_0$, this requirement is equivalent to the simultaneous agreement of three distinct quantities:
   $$
   \lim_{x \to x_0^-} f(x) = \lim_{x \to x_0^+} f(x) = f(x_0)
   $$

2. **Continuity of Elementary Components:**
   - The branch for $x < 2$ is a linear polynomial $p_1(x) = ax + 1$, which is continuous on $(-\infty, 2)$.
   - The branch for $x \ge 2$ is a quadratic polynomial $p_2(x) = x^2 - 1$, which is continuous on $[2, \infty)$.
   - Therefore, the function is automatically continuous everywhere on $\mathbb{R} \setminus \{2\}$. Continuity on the entire real line $\mathbb{R}$ reduces strictly to ensuring that the two branches glue together seamlessly at the boundary point $x = 2$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Function Value $f(2)$

According to the piecewise definition, for $x \ge 2$, the function is governed by the second branch $f(x) = x^2 - 1$.
Substitute $x = 2$:
$$
f(2) = 2^2 - 1 = 4 - 1 = 3
$$

---

### Step 2: Compute the Right-Hand Limit ($\lim_{x \to 2^+} f(x)$)

For $x > 2$, $f(x) = x^2 - 1$.
Since polynomials are continuous:
$$
\lim_{x \to 2^+} f(x) = \lim_{x \to 2^+} (x^2 - 1) = 2^2 - 1 = 3
$$
Notice that $\lim_{x \to 2^+} f(x) = f(2) = 3$ holds automatically by the definition of the right branch.

---

### Step 3: Compute the Left-Hand Limit ($\lim_{x \to 2^-} f(x)$)

For $x < 2$, $f(x)$ is governed by the first branch $f(x) = ax + 1$.
Take the limit as $x$ approaches $2$ from the left:
$$
\lim_{x \to 2^-} f(x) = \lim_{x \to 2^-} (ax + 1) = a(2) + 1 = 2a + 1
$$

---

### Step 4: Solve for Parameter $a$

For $f(x)$ to be continuous at $x = 2$, the left-hand limit must equal the right-hand limit (and the function value):
$$
\lim_{x \to 2^-} f(x) = \lim_{x \to 2^+} f(x) = f(2)
$$
Substitute the derived expressions:
$$
2a + 1 = 3
$$
Solve the linear equation for $a$:
$$
2a = 3 - 1 \implies 2a = 2 \implies a = 1
$$

Thus, the unique value of $a$ that guarantees continuity is:
$$
a = 1
$$

The continuous function is:
$$
f(x) = \begin{cases}
x + 1, & \text{for } x < 2, \\
x^2 - 1, & \text{for } x \ge 2.
\end{cases}
$$

---

### Step 5: Explicit Comparison of the Three Quantities

Substituting $a = 1$:
1. **Left-Hand Limit:**
   $$
   \lim_{x \to 2^-} f(x) = 1(2) + 1 = 3
   $$
2. **Right-Hand Limit:**
   $$
   \lim_{x \to 2^+} f(x) = 2^2 - 1 = 3
   $$
3. **Function Value:**
   $$
   f(2) = 2^2 - 1 = 3
   $$

Because:
$$
\lim_{x \to 2^-} f(x) = \lim_{x \to 2^+} f(x) = f(2) = 3
$$
all three quantities are identical, establishing continuity at $x = 2$.

---

## 4. Verification and Consistency Checks

1. **Numerical Table of Approaching Values with $a = 1$:**

| Approaching from Left ($x < 2$, $f(x) = x + 1$) | Function Value | Approaching from Right ($x > 2$, $f(x) = x^2 - 1$) | Function Value |
| :---: | :---: | :---: | :---: |
| $x = 1.9$ | $1.9 + 1 = 2.9000$ | $x = 2.1$ | $(2.1)^2 - 1 = 3.4100$ |
| $x = 1.99$ | $1.99 + 1 = 2.9900$ | $x = 2.01$ | $(2.01)^2 - 1 = 3.0401$ |
| $x = 1.999$ | $1.999 + 1 = 2.9990$ | $x = 2.001$ | $(2.001)^2 - 1 = 3.0040$ |
| $x \to 2^-$ | $\to 3.0000$ | $x \to 2^+$ | $\to 3.0000$ |

2. **Differentiability Check at the Glue Point (Optional Extension):**
   - Left-hand derivative: $f'_-(2) = \frac{d}{dx}(x + 1)\big|_{x=2} = 1$.
   - Right-hand derivative: $f'_+(2) = \frac{d}{dx}(x^2 - 1)\big|_{x=2} = 2(2) = 4$.
   Although $f(x)$ is continuous at $x = 2$ ($3 = 3$), it has a corner/kink at $(2, 3)$ because $f'_-(2) = 1 \ne 4 = f'_+(2)$. This illustrates that continuity does not require differentiability.
