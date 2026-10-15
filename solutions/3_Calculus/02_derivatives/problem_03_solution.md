# Solution to Problem 3: The Product Rule — Why Is It Needed?

## 1. Problem Statement

Given the function:
$$
f(x) = (x^2 + 1) e^x
$$

1. Compute the exact derivative $f'(x)$ using the product rule, simplifying the resulting expression.
2. Compare this correct result with the erroneous conjecture:
   $$
   f'(x) \stackrel{?}{=} (2x) e^x
   $$
3. Explicitly identify which term is missing from the incorrect conjecture and explain from both a geometric/differential and limit perspective why the product rule is necessary.

---

## 2. Theoretical Background and Concepts

1. **The Product Rule (Leibniz Rule):**
   If $u(x)$ and $v(x)$ are differentiable functions at $x$, then their product $f(x) = u(x)v(x)$ is differentiable at $x$, and its derivative is given by:
   $$
   (u \cdot v)' = u' \cdot v + u \cdot v'
   $$
   In Leibniz notation:
   $$
   \frac{d}{dx}[u v] = \frac{du}{dx} v + u \frac{dv}{dx}
   $$

2. **Why the Naive Conjecture $(u \cdot v)' \stackrel{?}{=} u' \cdot v'$ or $u' \cdot v$ Fails:**
   Differentiation is a linear operator, meaning:
   $$
   (u + v)' = u' + v'
   $$
   However, differentiation does **not** distribute over multiplication:
   $$
   (u \cdot v)' \neq u' \cdot v' \quad \text{and} \quad (u \cdot v)' \neq u' \cdot v
   $$

3. **Geometric / Differential Interpretation:**
   Consider a rectangle whose side lengths are varying quantities $u(t)$ and $v(t)$. The area of this rectangle is $A = u \cdot v$.
   When $u$ increases by $\Delta u$ and $v$ increases by $\Delta v$, the change in area is:
   $$
   \Delta A = (u + \Delta u)(v + \Delta v) - uv = (\Delta u) \cdot v + u \cdot (\Delta v) + (\Delta u)(\Delta v)
   $$
   Dividing by $\Delta x$ and taking the limit as $\Delta x \to 0$, the second-order term $\frac{\Delta u \Delta v}{\Delta x} \to 0$, yielding:
   $$
   \frac{dA}{dx} = \frac{du}{dx} \cdot v + u \cdot \frac{dv}{dx}
   $$
   The rate of change of the area consists of two distinct components:
   - The expansion in width while height is held constant: $v \cdot du$.
   - The expansion in height while width is held constant: $u \cdot dv$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Factors of the Product

The function is given by:
$$
f(x) = u(x) \cdot v(x)
$$
where:
- First factor: $u(x) = x^2 + 1$
- Second factor: $v(x) = e^x$

### Step 2: Differentiate Each Factor Individually

1. Differentiating $u(x)$:
   $$
   u'(x) = \frac{d}{dx}[x^2 + 1] = 2x + 0 = 2x
   $$
2. Differentiating $v(x)$:
   $$
   v'(x) = \frac{d}{dx}[e^x] = e^x
   $$
   (since the natural exponential function is its own derivative).

### Step 3: Apply the Product Rule

Using $(u v)' = u' v + u v'$:
$$
f'(x) = u'(x) v(x) + u(x) v'(x)
$$
Substitute the respective components:
$$
f'(x) = (2x) e^x + (x^2 + 1) e^x
$$

### Step 4: Simplify and Factor the Expression

Factor out the common exponential factor $e^x$:
$$
f'(x) = \left[2x + (x^2 + 1)\right] e^x = (x^2 + 2x + 1) e^x
$$
Recognizing the perfect square trinomial $x^2 + 2x + 1 = (x + 1)^2$:
$$
f'(x) = (x + 1)^2 e^x
$$

---

### Step 5: Analysis of the Erroneous Idea and Missing Term

The proposed incorrect conjecture was:
$$
f'_{\text{incorrect}}(x) = (2x) e^x
$$

1. **Identification of the Error:**
   Notice that:
   $$
   f'_{\text{incorrect}}(x) = u'(x) \cdot v(x)
   $$
   The student only differentiated the algebraic polynomial factor $u(x) = x^2 + 1 \to 2x$, but treated the second factor $v(x) = e^x$ as if it were a passive constant multiplying $u(x)$, completely ignoring the fact that $e^x$ is also actively changing with $x$.

2. **The Missing Term:**
   Subtracting the incorrect conjecture from the true derivative:
   $$
   f'(x) - f'_{\text{incorrect}}(x) = \left[(2x)e^x + (x^2 + 1)e^x\right] - (2x)e^x = (x^2 + 1)e^x = u(x) \cdot v'(x)
   $$
   The missing term is:
   $$
   u(x) \cdot v'(x) = (x^2 + 1) e^x
   $$
   This term represents the contribution to the rate of change caused by the exponential factor $e^x$ growing while weighted by the value of the polynomial $(x^2 + 1)$.

---

## 4. Verification and Consistency Checks

1. **Evaluation at $x = 0$:**
   - **Correct derivative:**
     $$
     f'(0) = (0 + 1)^2 e^0 = 1^2 \cdot 1 = 1
     $$
   - **Incorrect conjecture:**
     $$
     f'_{\text{incorrect}}(0) = (2 \cdot 0) e^0 = 0
     $$
   - **Independent limit check at $x = 0$:**
     $f(0) = (0^2 + 1)e^0 = 1$.
     $$
     f'(0) = \lim_{h \to 0} \frac{f(h) - f(0)}{h} = \lim_{h \to 0} \frac{(h^2 + 1)e^h - 1}{h}
     $$
     Using the linear approximation $e^h = 1 + h + \mathcal{O}(h^2)$:
     $$
     (h^2 + 1)(1 + h + \mathcal{O}(h^2)) - 1 = (1 + h + h^2 + h^3 + \dots) - 1 = h + h^2 + \dots
     $$
     Dividing by $h$:
     $$
     \lim_{h \to 0} \frac{h + \mathcal{O}(h^2)}{h} = \lim_{h \to 0} (1 + \mathcal{O}(h)) = 1
     $$
     The limit definition confirms $f'(0) = 1 \neq 0$. The incorrect conjecture predicts a horizontal tangent ($m = 0$) at $x = 0$, which is false; the true tangent has slope $m = 1$.

2. **Sign and Critical Point Consistency:**
   - The correct derivative is $f'(x) = (x + 1)^2 e^x$.
   - Because $(x + 1)^2 \ge 0$ for all $x \in \mathbb{R}$ and $e^x > 0$ for all $x \in \mathbb{R}$:
     $$
     f'(x) \ge 0 \quad \forall x \in \mathbb{R}
     $$
     with $f'(x) = 0$ exclusively at $x = -1$. Thus, $f(x)$ is monotonically non-decreasing over all of $\mathbb{R}$, having a horizontal inflection point at $x = -1$.
   - In contrast, the incorrect formula $(2x)e^x$ would falsely imply that $f'(x) < 0$ for all $x < 0$, predicting a local minimum at $x = 0$, which contradicts the actual behavior of $f(x) = (x^2 + 1)e^x$.
