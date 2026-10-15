# Solution to Problem 7: Integration by Parts as Reversing the Product Rule

## 1. Problem Statement

Compute the indefinite integral:
$$
\int x e^x \, dx
$$

1. Write out the product rule for differentiation for two functions $u(x)$ and $v(x)$.
2. Derive the integration-by-parts formula from the product rule and explain its operational meaning.
3. Apply integration by parts to evaluate $\int x e^x \, dx$, explicitly stating the choices of $u$, $v$, $du$, and $dv$.
4. Simplify and factor the resulting antiderivative.
5. Verify the complete result by differentiating back to the integrand.

---

## 2. Theoretical Background and Concepts

1. **Derivation of Integration by Parts from the Product Rule:**
   Let $u(x)$ and $v(x)$ be differentiable functions. The product rule of differentiation states:
   $$
   \frac{d}{dx}[u(x) v(x)] = u'(x) v(x) + u(x) v'(x)
   $$
   Integrating both sides with respect to $x$:
   $$
   \int \frac{d}{dx}[u(x) v(x)] \, dx = \int u'(x) v(x) \, dx + \int u(x) v'(x) \, dx
   $$
   By the Fundamental Theorem of Calculus, the integral of the derivative of $uv$ is simply the product $u(x) v(x)$ (up to an arbitrary constant absorbed later):
   $$
   u(x) v(x) = \int v(x) u'(x) \, dx + \int u(x) v'(x) \, dx
   $$
   Rearranging terms to isolate $\int u(x) v'(x) \, dx$:
   $$
   \int u(x) v'(x) \, dx = u(x) v(x) - \int v(x) u'(x) \, dx
   $$
   Using differential notation $du = u'(x) \, dx$ and $dv = v'(x) \, dx$:
   $$
   \int u \, dv = u v - \int v \, du
   $$

2. **The Operational Philosophy of Integration by Parts:**
   Integration by parts does not evaluate an integral in a single step; rather, it **transforms** a difficult integral $\int u \, dv$ into a new integral $\int v \, du$.
   The strategy succeeds when the new integral $\int v \, du$ is strictly simpler than the original.
   - We choose $u(x)$ to be a factor that becomes simpler upon differentiation (such as a polynomial $x$, whose derivative is a constant $1$).
   - We choose $dv$ to be a factor whose antiderivative $v$ is readily known and does not grow in complexity (such as $e^x$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Assign the Factors $u$ and $dv$

The integral to evaluate is:
$$
\int x e^x \, dx
$$
The integrand is a product of an algebraic polynomial $x$ and an exponential $e^x$.
- Choose:
  $$
  u = x
  $$
- Choose:
  $$
  dv = e^x \, dx
  $$

### Step 2: Compute $du$ and $v$

1. Differentiate $u$:
   $$
   du = \frac{d}{dx}[x] \, dx = 1 \, dx = dx
   $$
2. Integrate $dv$ (choosing the simplest antiderivative with constant $0$):
   $$
   v = \int e^x \, dx = e^x
   $$

Summary table:
$$
\begin{array}{r@{\quad=\quad}l@{\qquad}r@{\quad=\quad}l}
  u & x & v & e^x \\
  du & dx & dv & e^x \, dx
\end{array}
$$

---

### Step 3: Apply the Integration-by-Parts Formula

Substitute $u, v, du, dv$ into $\int u \, dv = u v - \int v \, du$:
$$
\int x e^x \, dx = (x)(e^x) - \int (e^x)(dx)
$$

Notice that the remaining integral $\int e^x \, dx$ no longer contains the variable factor $x$. Differentiating $u = x \to 1$ has successfully eliminated the algebraic obstacle!

Now evaluate the elementary integral $\int e^x \, dx$:
$$
\int e^x \, dx = e^x
$$

Substitute this back and append the arbitrary integration constant $C$:
$$
\int x e^x \, dx = x e^x - e^x + C
$$

---

### Step 4: Factor and Organize the Antiderivative

Factor out the common exponential term $e^x$:
$$
F(x) = (x - 1)e^x + C
$$

---

### Step 5: Verification by Differentiation

To verify the antiderivative, differentiate $F(x) = (x - 1)e^x + C$ using the product rule:
$$
F'(x) = \frac{d}{dx}[(x - 1)e^x + C] = \frac{d}{dx}[(x - 1)] \cdot e^x + (x - 1) \cdot \frac{d}{dx}[e^x] + 0
$$

Compute the individual derivatives:
- $\frac{d}{dx}[x - 1] = 1$
- $\frac{d}{dx}[e^x] = e^x$

Substitute:
$$
F'(x) = (1)(e^x) + (x - 1)(e^x)
$$
Expand and group terms:
$$
F'(x) = e^x + x e^x - e^x = x e^x
$$
The derivative reproduces the original integrand $f(x) = x e^x$ identically.

---

## 4. Verification and Consistency Checks

1. **Definite Integral Evaluation on $[0, 1]$:**
   Evaluate $\int_0^1 x e^x \, dx$:
   $$
   \int_0^1 x e^x \, dx = \Big[(x - 1)e^x\Big]_0^1 = (1 - 1)e^1 - (0 - 1)e^0 = 0 - (-1)(1) = 0 - (-1) = 1
   $$
   The exact accumulated value on $[0, 1]$ is precisely $1$.

2. **Numerical Midpoint Riemann Sum Verification on $[0, 1]$:**
   Let $n = 4$ subintervals with width $\Delta x = 0.25$:
   - Midpoints: $m_1 = 0.125, m_2 = 0.375, m_3 = 0.625, m_4 = 0.875$.
   - $f(0.125) = 0.125 e^{0.125} \approx 0.125(1.1331) \approx 0.14164$.
   - $f(0.375) = 0.375 e^{0.375} \approx 0.375(1.4550) \approx 0.54562$.
   - $f(0.625) = 0.625 e^{0.625} \approx 0.625(1.8682) \approx 1.16765$.
   - $f(0.875) = 0.875 e^{0.875} \approx 0.875(2.3989) \approx 2.09900$.
   Sum of values:
   $$
   0.14164 + 0.54562 + 1.16765 + 2.09900 = 3.95391
   $$
   Multiply by $\Delta x = 0.25$:
   $$
   M_4 = 3.95391 \times 0.25 = 0.98848 \approx 1.00
   $$
   The numerical Riemann sum confirms the analytical value $1$, validating the integration-by-parts calculation.
