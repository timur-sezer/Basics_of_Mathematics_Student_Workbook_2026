# Solution to Problem 11: A Parameter and the Number of Extrema

## 1. Problem Statement

Given the one-parameter family of cubic polynomials:
$$
f_a(x) = x^3 - 3ax
$$
where $a \in \mathbb{R}$ is a real parameter.

1. Compute the first derivative $f'_a(x)$ in terms of the parameter $a$.
2. Determine the number of critical points as a function of the parameter $a$.
3. Classify the parameter cases into three distinct regimes ($a > 0$, $a = 0$, $a < 0$).
4. In each case, determine the monotonicity of the function, the number and nature of any local extrema, and their exact coordinates.
5. Provide a physical and mathematical justification (bifurcation analysis) for why the qualitative structure of the graph transforms as $a$ crosses zero.

---

## 2. Theoretical Background and Concepts

1. **Parameter Families and Bifurcations:**
   When a family of functions $f_a(x)$ depends continuously on a parameter $a$, qualitative topological changes in the graph (such as the creation, annihilation, or merging of critical points) are known as **bifurcations**. The parameter values where these qualitative changes occur are called **bifurcation points**.

2. **Cubic Stationary Points:**
   For a cubic polynomial, the derivative is quadratic:
   $$
   f'_a(x) = A x^2 + B x + C
   $$
   The number of real critical points is determined by the discriminant $\Delta = B^2 - 4AC$:
   - $\Delta > 0$: Two distinct real roots $\implies$ two critical points (one local maximum and one local minimum).
   - $\Delta = 0$: One real root of multiplicity 2 $\implies$ one critical point (horizontal inflection point, no extrema).
   - $\Delta < 0$: No real roots $\implies$ no critical points (strictly monotonic everywhere).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Derivative and the Critical Equation

Differentiating $f_a(x) = x^3 - 3ax$ with respect to $x$:
$$
f'_a(x) = 3x^2 - 3a = 3(x^2 - a)
$$

The critical points are the solutions in $\mathbb{R}$ to $f'_a(x) = 0$:
$$
3(x^2 - a) = 0 \iff x^2 = a
$$

The nature and count of the real solutions to $x^2 = a$ depend fundamentally on the sign of $a$. We partition the parameter space into three mutually exclusive and exhaustive cases.

---

### Step 2: Case 1 — Parameter $a > 0$

1. **Critical Points:**
   Since $a > 0$, the equation $x^2 = a$ has two distinct real roots:
   $$
   x_1 = -\sqrt{a}, \qquad x_2 = +\sqrt{a}
   $$
   There are **two critical points**.

2. **Sign of $f'_a(x)$ and Monotonicity:**
   The derivative factors as $f'_a(x) = 3(x + \sqrt{a})(x - \sqrt{a})$, an upward-opening parabola:
   - On $(-\infty, -\sqrt{a})$: $x^2 > a \implies f'_a(x) > 0$ ($\mathbf{f_a}$ is strictly increasing).
   - On $(-\sqrt{a}, \sqrt{a})$: $x^2 < a \implies f'_a(x) < 0$ ($\mathbf{f_a}$ is strictly decreasing).
   - On $(\sqrt{a}, \infty)$: $x^2 > a \implies f'_a(x) > 0$ ($\mathbf{f_a}$ is strictly increasing).

3. **Classification and Coordinates of Extrema:**
   - **Local Maximum at $x_1 = -\sqrt{a}$:**
     The derivative transitions from positive to negative:
     $$
     y_{\max} = f_a(-\sqrt{a}) = (-\sqrt{a})^3 - 3a(-\sqrt{a}) = -a\sqrt{a} + 3a\sqrt{a} = 2a\sqrt{a} = 2a^{3/2} > 0
     $$
     Local maximum: $\mathbf{M(-\sqrt{a}, 2a\sqrt{a})}$.
   - **Local Minimum at $x_2 = +\sqrt{a}$:**
     The derivative transitions from negative to positive:
     $$
     y_{\min} = f_a(\sqrt{a}) = (\sqrt{a})^3 - 3a(\sqrt{a}) = a\sqrt{a} - 3a\sqrt{a} = -2a\sqrt{a} = -2a^{3/2} < 0
     $$
     Local minimum: $\mathbf{m(\sqrt{a}, -2a\sqrt{a})}$.

**Conclusion for $a > 0$:**
The function has **2 critical points**, which correspond to **1 strict local maximum** and **1 strict local minimum**. The graph has the classical "N" shape with two distinct turning points.

---

### Step 3: Case 2 — Parameter $a = 0$

1. **Critical Points:**
   When $a = 0$, the function is $f_0(x) = x^3$, and its derivative is:
   $$
   f'_0(x) = 3x^2
   $$
   Setting $f'_0(x) = 0$ yields:
   $$
   x^2 = 0 \implies x = 0 \quad (\text{root of multiplicity 2})
   $$
   There is **1 critical point**: $x = 0$.

2. **Monotonicity and Extrema Check:**
   - For all $x \neq 0$: $x^2 > 0 \implies f'_0(x) = 3x^2 > 0$.
   - The derivative is strictly positive on both $(-\infty, 0)$ and $(0, \infty)$.
   - Because $f'_0(x)$ does not change sign across $x = 0$, $x = 0$ is **neither a local maximum nor a local minimum**.
   - Instead, $(0, 0)$ is a **horizontal inflection point** (saddle point):
     $$
     f''_0(x) = 6x \implies f''_0(0) = 0 \quad \text{with a concavity change from } - \text{ to } +
     $$

**Conclusion for $a = 0$:**
The function has **1 critical point** and **0 local extrema**. The function is strictly increasing on all of $\mathbb{R}$.

---

### Step 4: Case 3 — Parameter $a < 0$

1. **Critical Points:**
   Let $a = -k$ where $k > 0$. Then:
   $$
   x^2 = a = -k < 0
   $$
   In the real numbers $\mathbb{R}$, a square cannot be negative. The equation has **no real solutions**.
   There are **0 critical points**.

2. **Monotonicity:**
   $$
   f'_a(x) = 3x^2 - 3a = 3(x^2 + k) \ge 3k > 0 \quad \forall x \in \mathbb{R}
   $$
   The derivative is strictly positive everywhere. The tangent line is never horizontal; its minimum slope is $f'_a(0) = -3a = 3k > 0$.
   Therefore, $f_a(x)$ is **strictly increasing on the entire real line $\mathbb{R}$**.

**Conclusion for $a < 0$:**
The function has **0 critical points** and **0 local extrema**.

---

### Step 5: Why the Structure of the Graph Changes (Bifurcation Mechanism)

The qualitative change across $a = 0$ can be understood through the competition between two terms:
$$
f_a(x) = \underbrace{x^3}_{\text{cubic growth}} - \underbrace{3ax}_{\text{linear influence}}
$$

1. **Competition near the origin:**
   Near $x = 0$, the linear term $-3ax$ dominates the cubic term $x^3$.
   - When $a > 0$, the linear term is $-3ax$, which has a **negative slope** $-3a < 0$. This forces the function to decrease in an open interval around the origin. However, for large $|x|$, the positive cubic term $x^3$ must dominate, forcing the function to rise to $+\infty$ on the right and plunge to $-\infty$ on the left. To reconcile local decrease with global increase, the graph is forced to fold twice, creating a local maximum to the left and a local minimum to the right.
   - When $a < 0$, the linear term is $+3|a|x$, which has a **positive slope**. Both the linear term and the cubic term push the curve in the same upward direction. There is no conflict between local and global behavior, so the curve rises monotonically without folding.

2. **Coalescence at $a = 0$:**
   As $a \to 0^+$, the distance between the two turning points shrinks:
   $$
   \Delta x = \sqrt{a} - (-\sqrt{a}) = 2\sqrt{a} \to 0
   $$
   and the vertical separation between the peak and trough collapses:
   $$
   \Delta y = 2a^{3/2} - (-2a^{3/2}) = 4a^{3/2} \to 0
   $$
   At the critical threshold $a = 0$, the local maximum and local minimum collide at the origin, annihilating each other in a cubic fold into a single horizontal inflection point. For $a < 0$, they vanish into the complex plane ($x = \pm i\sqrt{|a|}$), leaving behind a purely monotonic curve.

---

## 4. Verification and Consistency Checks

1. **Summary Classification Table:**

| Parameter Range | Number of Critical Points | Character of Critical Points | Number of Local Extrema | Monotonicity Profile |
|:---:|:---:|:---|:---:|:---|
| **$a > 0$** | **2** | $x = -\sqrt{a}$ (Local Max)<br>$x = +\sqrt{a}$ (Local Min) | **2** | Increasing on $(-\infty, -\sqrt{a}]$,<br>Decreasing on $[-\sqrt{a}, \sqrt{a}]$,<br>Increasing on $[\sqrt{a}, \infty)$ |
| **$a = 0$** | **1** | $x = 0$ (Horizontal Inflection Point) | **0** | Strictly increasing on $\mathbb{R}$ |
| **$a < 0$** | **0** | None | **0** | Strictly increasing on $\mathbb{R}$ |

2. **Numerical Sanity Check with Concrete Parameter Values:**
   - **$a = 1 > 0$:** $f_1(x) = x^3 - 3x \implies f'_1(x) = 3(x^2 - 1) = 0 \implies x = \pm 1$.
     Max at $(-1, 2)$, Min at $(1, -2)$. Formula gives $2(1)^{3/2} = 2$ and $-2(1)^{3/2} = -2$ ($\checkmark$).
   - **$a = 0$:** $f_0(x) = x^3 \implies f'_0(x) = 3x^2 \implies$ root at $x = 0$, strictly increasing ($\checkmark$).
   - **$a = -1 < 0$:** $f_{-1}(x) = x^3 + 3x \implies f'_{-1}(x) = 3x^2 + 3 \ge 3 > 0 \implies$ no roots, strictly increasing ($\checkmark$).
