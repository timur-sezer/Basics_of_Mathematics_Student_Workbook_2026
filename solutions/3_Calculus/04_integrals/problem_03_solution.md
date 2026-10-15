# Solution to Problem 3: Recognizing Basic Antiderivatives

## 1. Problem Statement

Compute the indefinite integral:
$$
\int \left(2e^x + 3\cos x - 4\sin x\right) \, dx
$$

1. Systematically match each individual term of the integrand with a known basic derivative.
2. Apply the linearity of the indefinite integral to compute the complete family of antiderivatives.
3. Verify the final expression by performing a single, comprehensive differentiation.

---

## 2. Theoretical Background and Concepts

1. **Table of Fundamental Derivatives and Their Inverses:**
   - **Exponential Function:**
     $$
     \frac{d}{dx}[e^x] = e^x \iff \int e^x \, dx = e^x + C
     $$
   - **Trigonometric Sine:**
     $$
     \frac{d}{dx}[\sin x] = \cos x \iff \int \cos x \, dx = \sin x + C
     $$
   - **Trigonometric Cosine:**
     $$
     \frac{d}{dx}[\cos x] = -\sin x \iff \int \sin x \, dx = -\cos x + C
     $$

2. **Sign Management in Trigonometric Integration:**
   A common source of confusion in calculus is the sign change between differentiation and integration of trigonometric functions:
   - Differentiating $\sin x$ gives $+\cos x$; integrating $\sin x$ gives $-\cos x$.
   - Differentiating $\cos x$ gives $-\sin x$; integrating $\cos x$ gives $+\sin x$.
   - Therefore, the term $-4\sin x$ in the integrand directly corresponds to $+4 \frac{d}{dx}[\cos x] = -4\sin x$.

3. **Linearity of the Integral:**
   $$
   \int \left(\sum_{k=1}^m c_k f_k(x)\right) dx = \sum_{k=1}^m c_k \int f_k(x) \, dx + C
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Term-by-Term Matching with Known Derivatives

We decompose the integrand into three distinct terms and identify the corresponding primitive for each:

1. **Term 1 ($2e^x$):**
   - Fundamental derivative: $\frac{d}{dx}[e^x] = e^x$.
   - Applying the constant multiple rule:
     $$
     \frac{d}{dx}[2e^x] = 2e^x \implies \int 2e^x \, dx = 2e^x
     $$

2. **Term 2 ($3\cos x$):**
   - Fundamental derivative: $\frac{d}{dx}[\sin x] = \cos x$.
   - Applying the constant multiple rule:
     $$
     \frac{d}{dx}[3\sin x] = 3\cos x \implies \int 3\cos x \, dx = 3\sin x
     $$

3. **Term 3 ($-4\sin x$):**
   - Fundamental derivative: $\frac{d}{dx}[\cos x] = -\sin x$.
   - Multiplying by $+4$:
     $$
     \frac{d}{dx}[4\cos x] = 4(-\sin x) = -4\sin x \implies \int (-4\sin x) \, dx = 4\cos x
     $$

---

### Step 2: Assemble the Family of Antiderivatives

Combining the three primitives and adding the single arbitrary constant of integration $C \in \mathbb{R}$:
$$
\int \left(2e^x + 3\cos x - 4\sin x\right) \, dx = 2e^x + 3\sin x + 4\cos x + C
$$

---

### Step 3: Verification by Differentiation

To verify the antiderivative, compute the derivative of the entire assembled function:
$$
\frac{d}{dx}\Big[2e^x + 3\sin x + 4\cos x + C\Big]
$$

Differentiate term-by-term:
$$
= 2 \frac{d}{dx}[e^x] + 3 \frac{d}{dx}[\sin x] + 4 \frac{d}{dx}[\cos x] + \frac{d}{dx}[C]
$$
$$
= 2(e^x) + 3(\cos x) + 4(-\sin x) + 0
$$
$$
= 2e^x + 3\cos x - 4\sin x
$$

The derivative strictly recovers the original integrand.

---

## 4. Verification and Consistency Checks

1. **Evaluation of a Definite Integral on $[0, \pi]$:**
   Compute the exact definite integral:
   $$
   I = \int_0^\pi \left(2e^x + 3\cos x - 4\sin x\right) \, dx = \left[2e^x + 3\sin x + 4\cos x\right]_0^\pi
   $$
   - At upper limit $x = \pi$:
     $$
     F(\pi) = 2e^\pi + 3\sin(\pi) + 4\cos(\pi) = 2e^\pi + 3(0) + 4(-1) = 2e^\pi - 4
     $$
   - At lower limit $x = 0$:
     $$
     F(0) = 2e^0 + 3\sin(0) + 4\cos(0) = 2(1) + 3(0) + 4(1) = 2 + 4 = 6
     $$
   - Net value:
     $$
     I = (2e^\pi - 4) - 6 = 2e^\pi - 10 \approx 2(23.14069) - 10 = 46.28138 - 10 = 36.28138
     $$

2. **Term-by-Term Geometric Check on $[0, \pi]$:**
   - $\int_0^\pi 2e^x \, dx = 2(e^\pi - 1) = 2e^\pi - 2$.
   - $\int_0^\pi 3\cos x \, dx = [3\sin x]_0^\pi = 3(0 - 0) = 0$ (the positive area on $[0, \pi/2]$ exactly cancels the negative area on $[\pi/2, \pi]$ by odd symmetry about $\pi/2$).
   - $\int_0^\pi -4\sin x \, dx = [4\cos x]_0^\pi = 4(-1 - 1) = -8$.
   - Summing:
     $$
     (2e^\pi - 2) + 0 + (-8) = 2e^\pi - 10
     $$
   The term-by-term definite values sum exactly to $2e^\pi - 10$, confirming both algebraic accuracy and geometric consistency.
