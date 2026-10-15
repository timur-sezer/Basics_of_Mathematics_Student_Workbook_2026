# Solution to Problem 15: Find the Error in the Monotonicity Analysis

## 1. Problem Statement

For the cubic polynomial:
$$
f(x) = x^3 - 3x
$$
the first derivative was correctly computed and factored as:
$$
f'(x) = 3(x - 1)(x + 1)
$$

However, a student wrote the following incorrect analysis:

> *"The derivative is positive between its zeros and negative outside them. Therefore, the function is decreasing on $(-\infty,-1)\cup(1,\infty)$, increasing on $(-1,1)$, has a local minimum at $x=-1$, and a local maximum at $x=1$."*

1. Without re-differentiating, explain why merely identifying the zeros of the derivative does not determine the sign chart, identify the precise conceptual error in the student's reasoning, and list all erroneous conclusions.
2. Construct the mathematically correct sign chart for $f'(x)$.
3. State the correct intervals of monotonicity and classify the true character and coordinates of each extremum.
4. In each of the three intervals, select a simple test point and show that evaluating the derivative explicitly validates the correct classification.

---

## 2. Theoretical Background and Concepts

1. **Zeros vs. Signs:**
   Finding the zeros of a continuous function $g(x)$ (solving $g(x) = 0$) identifies the boundary partition points where $g(x)$ *can potentially change sign* (by the Intermediate Value Theorem). However, the roots alone **never specify which side is positive and which is negative**, nor whether a sign change actually occurs (e.g., at roots of even multiplicity).

2. **The Sign of a Quadratic Polynomial $A x^2 + B x + C$:**
   Let a quadratic have two distinct real roots $x_1 < x_2$.
   - Its graph is a parabola.
   - If the leading coefficient $A > 0$, the parabola opens **upward**: it is **negative strictly between its roots** ($x \in (x_1, x_2)$) where the vertex dips below the axis, and **positive outside its roots** ($x < x_1$ or $x > x_2$).
   - If $A < 0$, the parabola opens **downward**: it is positive between its roots and negative outside them.

3. **Monotonicity and Set Notation:**
   Monotonicity is a property defined on connected intervals. It must not be stated across disconnected unions of intervals with the symbol $\cup$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Diagnosis of the Student's Errors

#### 1. Why Zeros Alone Do Not Justify a Sign Chart
The student solved $f'(x) = 0$ to find the zeros $x = -1$ and $x = 1$. The student then guessed or remembered a half-recalled rule about quadratics, blindly asserting that the polynomial was "positive between the zeros and negative outside."
Merely knowing that $f'(\pm 1) = 0$ establishes three intervals: $(-\infty, -1)$, $(-1, 1)$, and $(1, \infty)$. To determine the signs, one must either check the sign of the leading coefficient or evaluate concrete test points.

#### 2. The Primary Algebraic Error
The derivative is:
$$
f'(x) = 3(x^2 - 1) = 3x^2 - 3
$$
This is a quadratic with leading coefficient $A = +3 > 0$.
- Because $A = +3 > 0$, the parabola opens **upward**.
- An upward-opening parabola is **negative between its roots** (where it dips below the $x$-axis) and **positive outside its roots**.
- The student asserted the exact opposite, confusing an upward-opening parabola with a downward-opening one (as if $A$ were $-3$).

#### 3. Cascade of Resulting Errors
This single sign error caused every subsequent deduction to be completely wrong:
1. **Inverted signs:** The student declared $f'(x) > 0$ on $(-1, 1)$ (false; it is negative) and $f'(x) < 0$ outside (false; it is positive).
2. **Inverted monotonicity:** The student claimed $f$ is increasing on $(-1, 1)$ and decreasing on the outside. In reality, $f$ increases on the outside and decreases on $(-1, 1)$.
3. **Improper union notation:** The student wrote decreasing on $(-\infty, -1) \cup (1, \infty)$, which is mathematically invalid for monotonicity.
4. **Inverted extrema classification:**
   - At $x = -1$, the student claimed a local minimum because they believed $f'$ changed from $-$ to $+$. In reality, $f'$ changes from $+$ to $-$, making $x = -1$ a **local maximum**.
   - At $x = 1$, the student claimed a local maximum because they believed $f'$ changed from $+$ to $-$. In reality, $f'$ changes from $-$ to $+$, making $x = 1$ a **local minimum**.

---

### Step 2: The Correct Sign Chart for $f'(x)$

We factor $f'(x) = 3(x - 1)(x + 1)$ and analyze the sign of each factor across the three intervals partitioned by the roots $x = -1$ and $x = 1$:

| Factor / Function | $(-\infty, -1)$ | $x = -1$ | $(-1, 1)$ | $x = 1$ | $(1, \infty)$ |
|:---|:---:|:---:|:---:|:---:|:---:|
| $3$ (constant) | $+$ | $+$ | $+$ | $+$ | $+$ |
| $x + 1$ | $-$ | $0$ | $+$ | $+$ | $+$ |
| $x - 1$ | $-$ | $-$ | $-$ | $0$ | $+$ |
| **$f'(x) = 3(x+1)(x-1)$** | **$+$** | **$0$** | **$-$** | **$0$** | **$+$** |

---

### Step 3: Correct Monotonicity Intervals and Extrema

1. **Intervals of Monotonicity:**
   - On $(-\infty, -1]$: $f'(x) \ge 0 \implies f(x)$ is **strictly increasing**.
   - On $[-1, 1]$: $f'(x) \le 0 \implies f(x)$ is **strictly decreasing**.
   - On $[1, \infty)$: $f'(x) \ge 0 \implies f(x)$ is **strictly increasing**.

2. **Classification and Coordinates of Extrema:**
   - **Local Maximum at $x = -1$:**
     $f'(x)$ transitions from positive ($+$) to negative ($-$).
     $$
     y_{\max} = f(-1) = (-1)^3 - 3(-1) = -1 + 3 = 2
     $$
     The point $\mathbf{M(-1, 2)}$ is a **strict local maximum**.
   - **Local Minimum at $x = 1$:**
     $f'(x)$ transitions from negative ($-$) to positive ($+$).
     $$
     y_{\min} = f(1) = 1^3 - 3(1) = 1 - 3 = -2
     $$
     The point $\mathbf{m(1, -2)}$ is a **strict local minimum**.

---

### Step 4: Test Point Validation in Each Interval

To rigorously confirm the sign chart without factoring, we choose one simple test value inside each of the three open intervals:

1. **Interval 1: $(-\infty, -1)$ — Choose test point $x = -2$:**
   $$
   f'(-2) = 3((-2) - 1)((-2) + 1) = 3(-3)(-1) = +9 > 0
   $$
   The derivative is strictly positive ($+9$).
   **Confirmation:** $f(x)$ is strictly increasing on $(-\infty, -1]$.

2. **Interval 2: $(-1, 1)$ — Choose test point $x = 0$:**
   $$
   f'(0) = 3(0 - 1)(0 + 1) = 3(-1)(1) = -3 < 0
   $$
   The derivative is strictly negative ($-3$).
   **Confirmation:** $f(x)$ is strictly decreasing on $[-1, 1]$.

3. **Interval 3: $(1, \infty)$ — Choose test point $x = 2$:**
   $$
   f'(2) = 3(2 - 1)(2 + 1) = 3(1)(3) = +9 > 0
   $$
   The derivative is strictly positive ($+9$).
   **Confirmation:** $f(x)$ is strictly increasing on $[1, \infty)$.

The three test points unequivocally prove that the student's sign assignment was 100% backwards.

---

## 4. Verification and Consistency Checks

1. **Second Derivative Test:**
   $$
   f''(x) = \frac{d}{dx}[3x^2 - 3] = 6x
   $$
   - At $x = -1$: $f''(-1) = 6(-1) = -6 < 0 \implies$ strict local maximum ($\checkmark$).
   - At $x = +1$: $f''(1) = 6(1) = +6 > 0 \implies$ strict local minimum ($\checkmark$).
   This conclusively confirms that $(-1, 2)$ is a local maximum and $(1, -2)$ is a local minimum, directly contradicting the student's claims.

2. **Global Limits (End-Behavior) Check:**
   $$
   \lim_{x \to -\infty} (x^3 - 3x) = -\infty, \qquad \lim_{x \to +\infty} (x^3 - 3x) = +\infty
   $$
   - Because $f(x) \to -\infty$ as $x \to -\infty$ and rises to $f(-1) = 2$, it must be **increasing** on $(-\infty, -1)$.
   - Because $f(-1) = 2$ and drops to $f(1) = -2$, it must be **decreasing** on $(-1, 1)$.
   - Because $f(1) = -2$ and climbs to $+\infty$ as $x \to +\infty$, it must be **increasing** on $(1, \infty)$.
   Global limits provide a foolproof sanity check that completely refutes the student's inverted monotonicity.
