# Solution to Problem 11: Choose the Method First

## 1. Problem Statement

For each of the following three indefinite integrals, first explicitly identify the chosen integration method, justify the structural cues that reveal this method, and then execute the calculation to find the complete family of antiderivatives:

1. $I_1 = \int \sin(3x) \, dx$
2. $I_2 = \int x \ln x \, dx$
3. $I_3 = \int \frac{x}{\sqrt{x^2 + 1}} \, dx$

Verify each result by differentiation.

---

## 2. Theoretical Background and Concepts

1. **Strategic Taxonomy of Integration Techniques:**
   - **Direct / Linear Substitution:** Applicable when the argument is a simple linear function $g(x) = kx + b$. Because $g'(x) = k$ is a constant, no variable factors are needed in the differential: $\int f(kx + b) \, dx = \frac{1}{k} F(kx + b) + C$.
   - **Non-Linear Substitution ($u$-substitution):** Applicable when the integrand contains a composite function $f(g(x))$ multiplied by a factor proportional to the derivative of the inner function, $g'(x) \, dx$.
   - **Integration by Parts:** Applicable when the integrand is a product of two fundamentally different function types (e.g., algebraic $\times$ logarithmic, algebraic $\times$ exponential, or algebraic $\times$ trigonometric), where differentiating one factor reduces it to an algebraic form.
   - **The LIATE Rule for Integration by Parts:** Sets the priority for choosing $u$:
     $$\text{L (Logarithmic)} \to \text{I (Inverse Trig)} \to \text{A (Algebraic)} \to \text{T (Trigonometric)} \to \text{E (Exponential)}$$

---

## 3. Detailed Step-by-Step Solution

### Part 1: Integral $I_1 = \int \sin(3x) \, dx$

#### 1. Method Selection and Structural Rationale:
- **Chosen Method:** **Linear Substitution (or Direct Chain Rule Inversion)**.
- **Structural Cue:** The trigonometric function $\sin(\cdot)$ has an inner argument that is strictly linear in $x$: $u = 3x$. The derivative $\frac{du}{dx} = 3$ is a pure constant. No variable factors are required in the differential.

#### 2. Execution:
Let:
$$
u = 3x \implies du = 3 \, dx \implies dx = \frac{1}{3} du
$$

Substitute into the integral:
$$
I_1 = \int \sin(3x) \, dx = \int \sin u \cdot \left(\frac{1}{3} du\right) = \frac{1}{3} \int \sin u \, du
$$

Since the antiderivative of $\sin u$ is $-\cos u$:
$$
I_1 = \frac{1}{3}(-\cos u) + C = -\frac{1}{3}\cos(3x) + C
$$

#### 3. Verification by Differentiation:
$$
\frac{d}{dx}\left[-\frac{1}{3}\cos(3x) + C\right] = -\frac{1}{3}\left(-\sin(3x) \cdot \frac{d}{dx}[3x]\right) + 0 = -\frac{1}{3}\Big(-3\sin(3x)\Big) = \sin(3x) \quad (\checkmark)
$$

---

### Part 2: Integral $I_2 = \int x \ln x \, dx$

#### 1. Method Selection and Structural Rationale:
- **Chosen Method:** **Integration by Parts**.
- **Structural Cue:** The integrand is a product of two incompatible function families: an algebraic polynomial ($x$) and a transcendental logarithm ($\ln x$).
  - We cannot use substitution directly because the derivative of $\ln x$ (which is $1/x$) is missing; instead, we have $x$ multiplying $\ln x$.
  - However, according to the LIATE rule, choosing $u = \ln x$ is ideal because differentiating $\ln x$ yields $\frac{1}{x}$, which eliminates the transcendental logarithm entirely, leaving a purely algebraic integral.

#### 2. Execution:
Assign the factors:
$$
\begin{array}{r@{\quad=\quad}l@{\qquad}r@{\quad=\quad}l}
  u & \ln x & v & \frac{x^2}{2} \\
  du & \frac{1}{x} \, dx & dv & x \, dx
\end{array}
$$

Apply the integration-by-parts formula $\int u \, dv = u v - \int v \, du$:
$$
I_2 = (\ln x)\left(\frac{x^2}{2}\right) - \int \left(\frac{x^2}{2}\right)\left(\frac{1}{x} \, dx\right)
$$
Simplify the remaining integrand:
$$
\left(\frac{x^2}{2}\right)\left(\frac{1}{x}\right) = \frac{x}{2}
$$
Evaluate the secondary integral:
$$
I_2 = \frac{x^2}{2}\ln x - \frac{1}{2}\int x \, dx = \frac{x^2}{2}\ln x - \frac{1}{2}\left(\frac{x^2}{2}\right) + C = \frac{x^2}{2}\ln x - \frac{x^2}{4} + C
$$

Factoring out $\frac{x^2}{4}$:
$$
I_2 = \frac{x^2}{4}(2\ln x - 1) + C \qquad \text{for } x > 0
$$

#### 3. Verification by Differentiation:
Differentiate using the product rule:
$$
\frac{d}{dx}\left[\frac{x^2}{2}\ln x - \frac{x^2}{4} + C\right] = \frac{d}{dx}\left[\frac{x^2}{2}\right]\ln x + \frac{x^2}{2}\frac{d}{dx}[\ln x] - \frac{d}{dx}\left[\frac{x^2}{4}\right] + 0
$$
$$
= (x)\ln x + \frac{x^2}{2}\left(\frac{1}{x}\right) - \frac{2x}{4} = x\ln x + \frac{x}{2} - \frac{x}{2} = x\ln x \quad (\checkmark)
$$

---

### Part 3: Integral $I_3 = \int \frac{x}{\sqrt{x^2 + 1}} \, dx$

#### 1. Method Selection and Structural Rationale:
- **Chosen Method:** **Non-Linear Substitution**.
- **Structural Cue:** The denominator contains a composite radical with inner function $g(x) = x^2 + 1$. Its derivative is $g'(x) = 2x$. The numerator contains the variable factor $x$, which perfectly matches the degree of $g'(x)$ up to the constant scalar $2$.

#### 2. Execution:
Let:
$$
u = x^2 + 1
$$
Compute the differential:
$$
du = 2x \, dx \implies x \, dx = \frac{1}{2} du
$$

Rewrite the integrand in terms of $u$:
$$
I_3 = \int \frac{1}{\sqrt{x^2 + 1}} \cdot (x \, dx) = \int \frac{1}{\sqrt{u}} \cdot \left(\frac{1}{2} du\right) = \frac{1}{2} \int u^{-1/2} \, du
$$

Apply the power rule for integration ($\alpha = -1/2 \neq -1$):
$$
\frac{1}{2} \int u^{-1/2} \, du = \frac{1}{2} \cdot \left(\frac{u^{-\frac{1}{2} + 1}}{-\frac{1}{2} + 1}\right) + C = \frac{1}{2} \cdot \left(\frac{u^{1/2}}{1/2}\right) + C = u^{1/2} + C = \sqrt{u} + C
$$

Back-substitute $u = x^2 + 1$:
$$
I_3 = \sqrt{x^2 + 1} + C
$$

#### 3. Verification by Differentiation:
Differentiate using the chain rule:
$$
\frac{d}{dx}\left[\sqrt{x^2 + 1} + C\right] = \frac{1}{2\sqrt{x^2 + 1}} \cdot \frac{d}{dx}[x^2 + 1] + 0 = \frac{1}{2\sqrt{x^2 + 1}} \cdot (2x) = \frac{x}{\sqrt{x^2 + 1}} \quad (\checkmark)
$$

---

## 4. Verification and Consistency Checks

### Method Diagnostic Matrix

| Integral | Primary Structure | Why Other Methods Fail | Selected Technique | Final Result |
|:---|:---|:---|:---:|:---|
| $\int \sin(3x) \, dx$ | Single trig function with linear argument | Integration by parts is unnecessary; no non-linear composite | **Linear substitution** | $-\frac{1}{3}\cos(3x) + C$ |
| $\int x\ln x \, dx$ | Product of polynomial and logarithm | Derivative of $\ln x$ ($1/x$) is missing; substitution fails | **Integration by parts** | $\frac{x^2}{4}(2\ln x - 1) + C$ |
| $\int \frac{x}{\sqrt{x^2+1}} \, dx$ | Radical of quadratic with external linear factor | Integration by parts would produce higher-order fractions | **Substitution ($u = x^2+1$)** | $\sqrt{x^2 + 1} + C$ |

All three integrals have been uniquely paired with their optimal methods, evaluated rigorously, and checked via differentiation.
