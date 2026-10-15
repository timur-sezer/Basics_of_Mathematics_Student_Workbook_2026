# Solution to Problem 13: A Multi-Layer Composition

## 1. Problem Statement

Given the three-layer composite function:
$$
f(x) = e^{\sin(x^2)}
$$

1. Trace and write down the sequence of nested layers from the independent variable to the final output:
   $$
   x \longrightarrow x^2 \longrightarrow \sin(x^2) \longrightarrow e^{\sin(x^2)}
   $$
2. Explain why differentiation according to the chain rule traverses these layers in the **exact reverse order** (from outside inward).
3. Compute the derivative $f'(x)$ showing each intermediate factor.
4. Simplify and organize the final expression.

---

## 2. Theoretical Background and Concepts

1. **Multi-Stage Composition:**
   Let a function be defined by composing $n$ differentiable mappings:
   $$
   x \xrightarrow{\quad u \quad} u(x) \xrightarrow{\quad v \quad} v(u) \xrightarrow{\quad w \quad} w(v)
   $$
   Evaluating $f(x) = w(v(u(x)))$ requires a **forward pass**: start with $x$, compute $u$, feed $u$ into $v$, and feed $v$ into $w$.

2. **The Generalized Chain Rule (Leibniz Product Form):**
   The derivative of a triple composition is given by:
   $$
   \frac{df}{dx} = \frac{dw}{dv} \cdot \frac{dv}{du} \cdot \frac{du}{dx}
   $$
   Each term represents the instantaneous sensitivity of a layer to changes in its direct input.

3. **Why Differentiation Moves in Reverse Order:**
   - When we observe the composite function $f(x)$, its outermost envelope is $w$. To determine how a change in the outermost value occurs, we must first measure the response of $w$ with respect to its immediate argument $v$: $\frac{dw}{dv}$.
   - But $v$ is not an independent parameter; its change is driven by $u$: $\Delta v \approx \frac{dv}{du} \Delta u$.
   - Similarly, $u$ is driven by $x$: $\Delta u \approx \frac{du}{dx} \Delta x$.
   - Cascading these linear approximations backward:
     $$
     \Delta w \approx \frac{dw}{dv} \Delta v \approx \frac{dw}{dv} \left(\frac{dv}{du} \Delta u\right) \approx \frac{dw}{dv} \left(\frac{dv}{du} \left(\frac{du}{dx} \Delta x\right)\right) = \left(\frac{dw}{dv} \cdot \frac{dv}{du} \cdot \frac{du}{dx}\right) \Delta x
     $$
   Thus, differentiation naturally peels layers away from the outside inward. (In computer science and machine learning, this fundamental principle is called **reverse-mode automatic differentiation** or **backpropagation**).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Explicit Definition of the Three Layers

We define the intermediate state variables:
1. **Innermost Layer (Algebraic Power):**
   $$
   u = x^2
   $$
2. **Intermediate Layer (Trigonometric Sine):**
   $$
   v = \sin u = \sin(x^2)
   $$
3. **Outermost Layer (Natural Exponential):**
   $$
   w = e^v = e^{\sin(x^2)}
   $$

The forward evaluation flow is:
$$
x \xrightarrow{\quad (\cdot)^2 \quad} u = x^2 \xrightarrow{\quad \sin(\cdot) \quad} v = \sin(x^2) \xrightarrow{\quad e^{(\cdot)} \quad} w = e^{\sin(x^2)}
$$

---

### Step 2: Differentiate Each Layer in Reverse Order

We now move backward from the outermost function $w$ to the input $x$:

1. **Step A: Differentiate the Outermost Layer ($w$ with respect to $v$):**
   $$
   \frac{dw}{dv} = \frac{d}{dv}[e^v] = e^v = e^{\sin(x^2)}
   $$

2. **Step B: Differentiate the Intermediate Layer ($v$ with respect to $u$):**
   $$
   \frac{dv}{du} = \frac{d}{du}[\sin u] = \cos u = \cos(x^2)
   $$

3. **Step C: Differentiate the Innermost Layer ($u$ with respect to $x$):**
   $$
   \frac{du}{dx} = \frac{d}{dx}[x^2] = 2x
   $$

---

### Step 3: Multiply the Chain of Factors

Combine the three layer derivatives according to the chain rule:
$$
f'(x) = \frac{dw}{dv} \cdot \frac{dv}{du} \cdot \frac{du}{dx}
$$
Substitute the evaluated expressions:
$$
f'(x) = \left(e^{\sin(x^2)}\right) \cdot \left(\cos(x^2)\right) \cdot (2x)
$$

Rearrange into conventional mathematical order (algebraic factors first, then trigonometric, then exponential):
$$
f'(x) = 2x \cos(x^2) e^{\sin(x^2)}
$$

---

## 4. Verification and Consistency Checks

1. **Parity Check (Even/Odd Symmetry):**
   - The original function $f(x) = e^{\sin(x^2)}$ satisfies:
     $$
     f(-x) = e^{\sin((-x)^2)} = e^{\sin(x^2)} = f(x)
     $$
     Thus, $f(x)$ is an **even function**.
   - The derivative of an even function must be an **odd function**:
     $$
     f'(-x) = 2(-x) \cos((-x)^2) e^{\sin((-x)^2)} = -2x \cos(x^2) e^{\sin(x^2)} = -f'(x)
     $$
     The formula satisfies $f'(-x) = -f'(x)$, confirming that $f'$ is odd.
   - For any continuous odd function, $f'(0)$ must equal $0$:
     $$
     f'(0) = 2(0) \cos(0) e^{\sin(0)} = 0 \cdot 1 \cdot e^0 = 0
     $$
     This is fully consistent.

2. **Series Expansion Verification at $x = 0$:**
   Expand the nested layers using their Maclaurin series:
   - $x^2$ is $\mathcal{O}(x^2)$.
   - $\sin(x^2) = x^2 - \frac{(x^2)^3}{6} + \dots = x^2 - \frac{x^6}{6} + \dots$
   - $e^{\sin(x^2)} = 1 + \sin(x^2) + \frac{(\sin(x^2))^2}{2} + \dots = 1 + x^2 + \frac{x^4}{2} + \mathcal{O}(x^6)$
   Differentiating the power series term-by-term:
   $$
   \frac{d}{dx}\left[1 + x^2 + \frac{x^4}{2} + \dots\right] = 2x + 2x^3 + \dots
   $$
   Now expand our derivative formula $f'(x) = 2x \cos(x^2) e^{\sin(x^2)}$:
   $$
   f'(x) = 2x \cdot \left(1 - \frac{x^4}{2} + \dots\right) \cdot (1 + x^2 + \dots) = 2x(1 + x^2 + \dots) = 2x + 2x^3 + \dots
   $$
   The series agree exactly up to higher-order terms.

3. **Logarithmic Differentiation (Alternative Independent Method):**
   Take the natural logarithm of both sides:
   $$
   \ln(f(x)) = \ln\left(e^{\sin(x^2)}\right) = \sin(x^2)
   $$
   Differentiate implicitly with respect to $x$:
   $$
   \frac{f'(x)}{f(x)} = \frac{d}{dx}[\sin(x^2)] = \cos(x^2) \cdot 2x = 2x \cos(x^2)
   $$
   Multiply by $f(x)$:
   $$
   f'(x) = 2x \cos(x^2) \cdot f(x) = 2x \cos(x^2) e^{\sin(x^2)}
   $$
   This independently proves the validity of the chain rule result.
