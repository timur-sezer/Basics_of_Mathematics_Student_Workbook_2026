# Solution to Problem 5: An Exponential Function with a Maximum

## 1. Problem Statement

Perform a comprehensive analysis of the exponential function:
$$
f(x) = x e^{-x}
$$

1. Determine the domain $\mathcal{D}_f$ and identify the intercepts with the axes.
2. Compute the first derivative $f'(x)$ and determine the intervals of monotonicity and the location and nature of the local/global extrema.
3. Examine the end-behavior by evaluating $\lim_{x \to -\infty} f(x)$ and $\lim_{x \to +\infty} f(x)$.
4. Compute the second derivative $f''(x)$ to determine concavity and find the inflection point.
5. Explain in detail how the limit as $x \to +\infty$ governs the geometric shape, curvature change, and asymptotic leveling of the graph on the right-hand side.

---

## 2. Theoretical Background and Concepts

1. **Growth Rates (Polynomial vs. Exponential):**
   Exponential growth and decay dominate any polynomial power:
   $$
   \lim_{x \to \infty} \frac{x^n}{e^x} = 0 \quad \text{for any } n \in \mathbb{R}
   $$
   As $x \to +\infty$, the exponential factor $e^{-x}$ drives the product to zero infinitely faster than the linear factor $x$ can grow.

2. **The Product Rule with Exponentials:**
   $$
   \frac{d}{dx}[u(x) e^{-x}] = u'(x)e^{-x} - u(x)e^{-x} = [u'(x) - u(x)]e^{-x}
   $$

3. **Asymptotic Deceleration and Inflection:**
   If a function is strictly positive, strictly decreasing, and bounded below by a horizontal asymptote $y = 0$, it cannot remain concave downward indefinitely (a strictly concave downward curve with negative slope would eventually plunge below any horizontal barrier). It must transition through an **inflection point** to become **concave upward**, allowing it to flatten smoothly against the asymptote.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and Intercepts

1. **Domain:**
   Both $x$ and $e^{-x}$ are defined for all real numbers:
   $$
   \mathcal{D}_f = \mathbb{R}
   $$

2. **Intercepts:**
   - Setting $f(x) = 0$:
     $$
     x e^{-x} = 0
     $$
     Since $e^{-x} > 0$ for all $x \in \mathbb{R}$, the unique root is $x = 0$.
   - The unique intercept is the origin:
     $$
     (0, 0)
     $$
   - **Sign of $f(x)$:**
     - For $x > 0$: $f(x) > 0$ (lies strictly above the $x$-axis).
     - For $x < 0$: $f(x) < 0$ (lies strictly below the $x$-axis).

---

### Step 2: First Derivative, Monotonicity, and Extrema

1. **Differentiate via the Product Rule:**
   Let $u(x) = x \implies u'(x) = 1$ and $v(x) = e^{-x} \implies v'(x) = -e^{-x}$.
   $$
   f'(x) = (1)(e^{-x}) + (x)(-e^{-x}) = (1 - x)e^{-x}
   $$

2. **Critical Points:**
   Set $f'(x) = 0$:
   $$
   (1 - x)e^{-x} = 0
   $$
   Because $e^{-x} > 0$ everywhere, we obtain:
   $$
   1 - x = 0 \iff x = 1
   $$
   The single critical point is $x = 1$.

3. **Sign Chart and Monotonicity:**
   The sign of $f'(x)$ is determined entirely by $(1 - x)$:
   - **For $x \in (-\infty, 1)$:** $1 - x > 0 \implies f'(x) > 0$. The function is **strictly increasing** on $(-\infty, 1]$.
   - **At $x = 1$:** $f'(1) = 0$.
   - **For $x \in (1, \infty)$:** $1 - x < 0 \implies f'(x) < 0$. The function is **strictly decreasing** on $[1, \infty)$.

4. **Character and Coordinates of the Maximum:**
   At $x = 1$, $f'(x)$ transitions from positive to negative. Hence, $x = 1$ is a **strict global maximum**:
   $$
   y_{\max} = f(1) = 1 \cdot e^{-1} = \frac{1}{e} \approx 0.367879
   $$
   The global maximum is:
   $$
   \mathbf{M\left(1, \frac{1}{e}\right)}
   $$

---

### Step 3: End-Behavior and Asymptotes

1. **Limit as $x \to -\infty$:**
   $$
   \lim_{x \to -\infty} x e^{-x} = (-\infty) \cdot e^{+\infty} = (-\infty) \cdot (+\infty) = -\infty
   $$
   The function plunges steeply into the third quadrant without any asymptote.

2. **Limit as $x \to +\infty$:**
   $$
   \lim_{x \to +\infty} x e^{-x} = \lim_{x \to +\infty} \frac{x}{e^x} \quad \left(\frac{\infty}{\infty}\right)
   $$
   Applying l'Hôpital's rule:
   $$
   \lim_{x \to +\infty} \frac{\frac{d}{dx}[x]}{\frac{d}{dx}[e^x]} = \lim_{x \to +\infty} \frac{1}{e^x} = 0^+
   $$
   Therefore, the line **$y = 0$** (the positive $x$-axis) is a **horizontal asymptote** as $x \to +\infty$.

---

### Step 4: Second Derivative, Concavity, and Inflection Point

Differentiate $f'(x) = (1 - x)e^{-x}$ using the product rule:
$$
f''(x) = \frac{d}{dx}[1 - x]e^{-x} + (1 - x)\frac{d}{dx}[e^{-x}] = (-1)e^{-x} + (1 - x)(-e^{-x})
$$
Factor out $e^{-x}$:
$$
f''(x) = \left[-1 - (1 - x)\right]e^{-x} = (x - 2)e^{-x}
$$

1. **Sign of $f''(x)$:**
   - For $x < 2$: $x - 2 < 0 \implies f''(x) < 0$ (the graph is **concave downward** $\cap$).
   - At $x = 2$: $f''(2) = 0$.
   - For $x > 2$: $x - 2 > 0 \implies f''(x) > 0$ (the graph is **concave upward** $\cup$).

2. **Inflection Point:**
   $$
   y_{\text{inf}} = f(2) = 2e^{-2} = \frac{2}{e^2} \approx 0.27067
   $$
   The inflection point is:
   $$
   \mathbf{I\left(2, \frac{2}{e^2}\right)}
   $$

---

### Step 5: How the Limit Governs the Shape on the Right-Hand Side

1. **The Inevitability of Inflection:**
   At the peak $(1, 1/e)$, the curve turns downward with negative curvature ($f''(1) = -1/e < 0$).
   If the curve maintained downward concavity, its slope would become increasingly negative, forcing the curve to cross the $x$-axis and plunge to $-\infty$.
   However, we know that:
   $$
   f(x) > 0 \quad \forall x > 0 \quad \text{and} \quad \lim_{x \to \infty} f(x) = 0
   $$
   The curve is trapped between decreasing and staying strictly above zero.

2. **The Role of the Inflection Point at $x = 2$:**
   At $x = 2$, the curve ceases to steepen its descent. The descent rate reaches its steepest slope at $x = 2$:
   $$
   f'(2) = (1 - 2)e^{-2} = -e^{-2} \approx -0.1353
   $$
   Beyond $x = 2$, the concavity becomes positive ($f''(x) > 0$). This positive second derivative causes the downward slope to gradually level out ($f'(x) \to 0^-$), enabling the curve to bend gently and cradle horizontally against the asymptote $y = 0$.

**ASCII Visual Profile:**
```text
           y
           ^
     0.4   |         * M(1, 1/e ≈ 0.368)
     0.3   |       *   *
           |      *      * I(2, 2/e^2 ≈ 0.271)
     0.2   |     *         *
     0.1   |    *            *  *  *  *  *  *  *  *  (approaching y = 0 from above)
   --------+---*-------------------------------------> x
    -1     |  0 (0, 0)  1    2    3    4    5    6
           | *
    -1     |*
           |
```

---

## 4. Verification and Consistency Checks

1. **Maximum Value Verification:**
   For any $x > 0$, using the inequality $e^u \ge 1 + u$:
   Set $u = x - 1$:
   $$
   e^{x - 1} \ge 1 + (x - 1) = x \implies \frac{e^x}{e} \ge x \implies \frac{1}{e} \ge \frac{x}{e^x} = f(x)
   $$
   This proves purely algebraically that $f(x) \le \frac{1}{e}$ for all $x \in \mathbb{R}$, with equality uniquely when $x - 1 = 0 \iff x = 1$.

2. **Difference Quotient Check at the Maximum $x = 1$:**
   $$
   f'(1) = \lim_{h \to 0} \frac{f(1 + h) - f(1)}{h} = \lim_{h \to 0} \frac{(1 + h)e^{-(1 + h)} - e^{-1}}{h} = e^{-1} \lim_{h \to 0} \frac{(1 + h)e^{-h} - 1}{h}
   $$
   Using $e^{-h} = 1 - h + \frac{h^2}{2} + \dots$:
   $$
   (1 + h)(1 - h + \dots) - 1 = (1 - h^2 + \dots) - 1 = -h^2 + \dots
   $$
   Dividing by $h$:
   $$
   \lim_{h \to 0} \frac{-h^2}{h} = \lim_{h \to 0} (-h) = 0
   $$
   This independently proves $f'(1) = 0$.
