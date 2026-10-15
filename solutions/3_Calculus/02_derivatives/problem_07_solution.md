# Solution to Problem 7: A Trigonometric Composition

## 1. Problem Statement

Given the composite trigonometric function:
$$
f(x) = \sin(x^2 + 1)
$$

1. Compute the derivative $f'(x)$ using the chain rule.
2. Explicitly identify the outer function, the inner function, and the derivative of the inner function.
3. Evaluate the derivative at $x = 0$ and determine its algebraic sign.
4. Interpret the local behavior of the function around $x = 0$.

---

## 2. Theoretical Background and Concepts

1. **Structure of Composition:**
   When a trigonometric function takes a non-linear argument, it is a composition $f(x) = g(u(x))$:
   $$
   x \xrightarrow{\quad u \quad} u(x) = x^2 + 1 \xrightarrow{\quad g \quad} \sin(u)
   $$
   - The **outer function** is the trigonometric envelope $g(u) = \sin u$.
   - The **inner function** is the algebraic argument $u(x) = x^2 + 1$.

2. **The Chain Rule for Trigonometric Functions:**
   $$
   \frac{d}{dx}[\sin(u(x))] = \cos(u(x)) \cdot u'(x)
   $$
   The outer derivative is evaluated at the unchanged inner argument $u(x)$, and then multiplied by the derivative of the argument $u'(x)$.

3. **Sign and Critical Point Classification:**
   The sign of $f'(x)$ determines the monotonicity of $f$:
   - If $f'(x_0) = 0$, $x_0$ is a critical (stationary) point with a horizontal tangent.
   - If $f'(x)$ changes sign from negative for $x < x_0$ to positive for $x > x_0$, $x_0$ is a local minimum.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Explicit Identification of the Layers

1. **Inner Function:**
   $$
   u(x) = x^2 + 1
   $$
2. **Outer Function:**
   $$
   g(u) = \sin u
   $$
   so that $f(x) = g(u(x)) = \sin(x^2 + 1)$.

---

### Step 2: Compute the Derivatives of the Layers

1. **Derivative of the Outer Function:**
   Differentiate $g(u) = \sin u$ with respect to $u$:
   $$
   g'(u) = \frac{d}{du}[\sin u] = \cos u
   $$
   Evaluating at the inner expression $u = x^2 + 1$:
   $$
   g'(u(x)) = \cos(x^2 + 1)
   $$

2. **Derivative of the Inner Function:**
   Differentiate $u(x) = x^2 + 1$ with respect to $x$ using the power and constant rules:
   $$
   u'(x) = \frac{d}{dx}[x^2 + 1] = 2x + 0 = 2x
   $$

---

### Step 3: Combine via the Chain Rule

Applying $f'(x) = g'(u(x)) \cdot u'(x)$:
$$
f'(x) = \cos(x^2 + 1) \cdot (2x)
$$
Writing the algebraic factor in front:
$$
f'(x) = 2x \cos(x^2 + 1)
$$

---

### Step 4: Determine the Value and Sign of $f'(0)$

1. **Substitute $x = 0$:**
   $$
   f'(0) = 2(0) \cdot \cos(0^2 + 1) = 0 \cdot \cos(1)
   $$
   Since $\cos(1)$ is evaluated in radians:
   $$
   1 \text{ radian} \approx 57.2958^\circ \in \left(0, \frac{\pi}{2}\right) \implies \cos(1) \approx 0.540302 > 0
   $$
   Therefore:
   $$
   f'(0) = 0 \cdot 0.540302 = 0
   $$

2. **Sign Determination:**
   The value is neither strictly positive nor strictly negative:
   $$
   f'(0) = 0 \quad (\text{zero / neutral sign})
   $$

3. **Behavior Near $x = 0$:**
   Consider an interval around $x = 0$, say $|x| < \sqrt{\frac{\pi}{2} - 1} \approx 0.755$, where $x^2 + 1 \in \left[1, \frac{\pi}{2}\right)$, so $\cos(x^2 + 1) > 0$:
   - For $x < 0$: $2x < 0$ and $\cos(x^2 + 1) > 0 \implies f'(x) < 0$ (strictly decreasing).
   - At $x = 0$: $f'(0) = 0$ (horizontal tangent line $y = \sin(1) \approx 0.8415$).
   - For $x > 0$: $2x > 0$ and $\cos(x^2 + 1) > 0 \implies f'(x) > 0$ (strictly increasing).

   Because $f'(x)$ changes from negative to positive across $x = 0$, the function attains a **strict local minimum** at $x = 0$ with value $f(0) = \sin(1)$.

---

## 4. Verification and Consistency Checks

1. **Parity (Symmetry) Verification:**
   The function $f(x) = \sin(x^2 + 1)$ is an **even function** because:
   $$
   f(-x) = \sin((-x)^2 + 1) = \sin(x^2 + 1) = f(x)
   $$
   The derivative of any differentiable even function is necessarily an **odd function**:
   $$
   f'(-x) = 2(-x)\cos((-x)^2 + 1) = -2x\cos(x^2 + 1) = -f'(x)
   $$
   For any continuous odd function defined at $0$, we must have $f'(0) = -f'(0) \implies 2f'(0) = 0 \implies f'(0) = 0$.
   This confirms that $f'(0) = 0$.

2. **Numerical Difference Quotient at $x = 0$:**
   Compute the one-sided difference quotient with $h = 10^{-4}$:
   - $f(0) = \sin(1) \approx 0.8414709848$
   - $f(0.0001) = \sin((0.0001)^2 + 1) = \sin(1 + 10^{-8}) \approx \sin(1) + 10^{-8}\cos(1) \approx 0.8414709848 + 5.4 \times 10^{-9}$
   - Difference quotient:
     $$
     \frac{f(10^{-4}) - f(0)}{10^{-4}} \approx \frac{5.4 \times 10^{-9}}{10^{-4}} = 5.4 \times 10^{-5} \to 0
     $$
   As $h \to 0$, the quotient approaches $0$, validating $f'(0) = 0$.
