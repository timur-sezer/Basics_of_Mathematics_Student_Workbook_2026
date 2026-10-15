# Solution to Problem 5: The Chain Rule as Working Through Layers

## 1. Problem Statement

Given the composite function:
$$
f(x) = (3x^2 - 2x + 1)^5
$$

1. Identify the inner and outer functions forming the composition.
2. Compute the derivative of the outer function with respect to the intermediate variable, and the derivative of the inner function with respect to $x$.
3. Combine these derivatives according to the chain rule to obtain $f'(x)$, simplifying the expression.
4. Explain the conceptual and physical origin of the additional factor that arises from the inner derivative.

---

## 2. Theoretical Background and Concepts

1. **Composite Functions (Function Layers):**
   A composite function $f(x) = (g \circ u)(x) = g(u(x))$ processes an input $x$ in sequential stages:
   $$
   x \xrightarrow{\quad u \quad} u(x) \xrightarrow{\quad g \quad} g(u)
   $$
   - The **inner function** $u(x)$ acts first on the independent variable $x$.
   - The **outer function** $g(u)$ acts on the result of the inner function.

2. **The Chain Rule:**
   If $u$ is differentiable at $x$ and $g$ is differentiable at $u(x)$, then the composite function $f = g \circ u$ is differentiable at $x$, and its derivative is:
   $$
   f'(x) = g'(u(x)) \cdot u'(x)
   $$
   In Leibniz notation:
   $$
   \frac{df}{dx} = \frac{df}{du} \cdot \frac{du}{dx}
   $$

3. **Origin of the Factor $\frac{du}{dx}$ (Rate Multiplier):**
   A small perturbation $\Delta x$ causes an intermediate change $\Delta u \approx u'(x) \Delta x$. This change in the input to $g$ in turn creates an output change:
   $$
   \Delta f \approx g'(u) \Delta u \approx g'(u) \cdot [u'(x) \Delta x] = [g'(u) u'(x)] \Delta x
   $$
   Dividing by $\Delta x$ shows that the two rates of change multiply like gear ratios in a transmission system.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Layers of the Composition

The given expression is $f(x) = (3x^2 - 2x + 1)^5$.
We decompose $f$ into:
1. **Inner Function (Base):**
   $$
   u(x) = 3x^2 - 2x + 1
   $$
2. **Outer Function (Power):**
   $$
   g(u) = u^5
   $$
so that $f(x) = g(u(x))$.

---

### Step 2: Compute the Derivatives of the Layers

1. **Derivative of the Outer Function:**
   Differentiating $g(u) = u^5$ with respect to the variable $u$ using the power rule:
   $$
   \frac{dg}{du} = g'(u) = 5u^4
   $$
   Substituting back $u = 3x^2 - 2x + 1$:
   $$
   g'(u(x)) = 5(3x^2 - 2x + 1)^4
   $$

2. **Derivative of the Inner Function:**
   Differentiating $u(x) = 3x^2 - 2x + 1$ with respect to $x$:
   $$
   \frac{du}{dx} = u'(x) = \frac{d}{dx}[3x^2] - \frac{d}{dx}[2x] + \frac{d}{dx}[1] = 6x - 2
   $$

---

### Step 3: Combine via the Chain Rule

According to the chain rule:
$$
f'(x) = g'(u(x)) \cdot u'(x)
$$
Substitute the derived components:
$$
f'(x) = 5(3x^2 - 2x + 1)^4 \cdot (6x - 2)
$$

Factoring out the common factor $2$ from $(6x - 2) = 2(3x - 1)$:
$$
f'(x) = 5(3x^2 - 2x + 1)^4 \cdot 2(3x - 1) = 10(3x - 1)(3x^2 - 2x + 1)^4
$$

---

### Step 4: Explanation of the Additional Factor

- **What would happen without the chain rule?**
  A beginner often writes $\frac{d}{dx}[(3x^2 - 2x + 1)^5] \stackrel{?}{=} 5(3x^2 - 2x + 1)^4$.
  This naive application of the power rule assumes that the quantity inside the parentheses is the independent variable itself (i.e., that $\frac{du}{dx} = 1$, as in $\frac{d}{dx}[x^5] = 5x^4$).

- **Why is the factor $(6x - 2)$ necessary?**
  When $x$ changes by a tiny amount $\Delta x$, the inside expression $u(x)$ does not change at a $1:1$ rate with $x$. Instead, $u(x)$ changes by:
  $$
  \Delta u \approx (6x - 2) \Delta x
  $$
  Because the outer 5th-power operation responds to changes in $u$ at the instantaneous sensitivity $5u^4$, the total sensitivity of the output to changes in $x$ is:
  $$
  \frac{\Delta f}{\Delta x} \approx \underbrace{\frac{\Delta f}{\Delta u}}_{\text{sensitivity to } u} \times \underbrace{\frac{\Delta u}{\Delta x}}_{\text{sensitivity to } x} = 5u^4 \cdot (6x - 2)
  $$
  The additional factor $(6x - 2)$ is the **transmission ratio** that translates a rate of change with respect to $x$ into the rate of change with respect to $u$.

---

## 4. Verification and Consistency Checks

1. **Check at $x = 0$:**
   - Function value:
     $$
     f(0) = (3(0)^2 - 2(0) + 1)^5 = 1^5 = 1
     $$
   - Derivative value from our formula:
     $$
     f'(0) = 10(3(0) - 1)(3(0)^2 - 2(0) + 1)^4 = 10(-1)(1)^4 = -10
     $$
   - Verification via binomial expansion near $x = 0$:
     For very small $x$, neglect higher-order terms ($x^2, x^3, \dots$):
     $$
     f(x) = (1 - 2x + 3x^2)^5 \approx (1 - 2x)^5 = 1 - 5(2x) + \mathcal{O}(x^2) = 1 - 10x + \mathcal{O}(x^2)
     $$
     The linear coefficient of the Taylor expansion at $x = 0$ is exactly $-10$, which proves that $f'(0) = -10$.

2. **Check Critical Points:**
   Since $3x^2 - 2x + 1$ has discriminant $\Delta = (-2)^2 - 4(3)(1) = 4 - 12 = -8 < 0$ and leading coefficient $3 > 0$, the quadratic factor is strictly positive for all $x \in \mathbb{R}$:
   $$
   3x^2 - 2x + 1 > 0 \quad \forall x \in \mathbb{R} \implies (3x^2 - 2x + 1)^4 > 0 \quad \forall x \in \mathbb{R}
   $$
   Therefore, the only zero of $f'(x) = 10(3x - 1)(3x^2 - 2x + 1)^4$ occurs precisely when:
   $$
   3x - 1 = 0 \iff x = \frac{1}{3}
   $$
   Notice that $x = 1/3$ is the vertex of the inner parabola $u(x) = 3x^2 - 2x + 1$, where $u'(x) = 6x - 2 = 0$. Since $g(u) = u^5$ is strictly increasing, the extreme values of $f(x)$ must coincide exactly with the extreme values of $u(x)$. This confirms that $f'(x) = 0$ at $x = 1/3$.
