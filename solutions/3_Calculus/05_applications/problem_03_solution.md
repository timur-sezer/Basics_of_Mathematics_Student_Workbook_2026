# Solution to Problem 3: A Box Made from Cardboard

## 1. Problem Statement

A rectangular sheet of cardboard measures $30\text{ cm} \times 40\text{ cm}$. Squares of identical side length $x$ are cut out from each of the four corners, and the remaining flaps are folded upward at right angles to form an open-top rectangular box.

1. Construct the mathematical model expressing the volume $V$ of the box as a single-variable function of $x$.
2. Determine the physically and geometrically meaningful domain of the volume function.
3. Compute the derivative $V'(x)$ and determine all critical points.
4. Filter out any unphysical critical points and find the exact and approximate value of $x$ that maximizes the volume.
5. Compute the optimal dimensions of the box and the maximum volume enclosed, verifying that the critical point is an absolute maximum.

---

## 2. Theoretical Background and Concepts

1. **Geometric Optimization Modeling:**
   A rectangular cuboid with base dimensions $W$ and $L$ and height $H$ has volume:
   $$
   V = W \cdot L \cdot H
   $$
   When cutting squares of side $x$ from the corners of a flat rectangular sheet of dimensions $A \times B$:
   - The height of the folded box is $H = x$.
   - The two base dimensions are reduced by $2x$ (one cutout from each opposing edge):
     $$
     W = A - 2x, \qquad L = B - 2x
     $$

2. **Feasible Domain Determination:**
   In physical manufacturing, all three linear dimensions must be strictly positive:
   $$
   x > 0, \qquad A - 2x > 0, \qquad B - 2x > 0
   $$
   The upper bound of the feasible domain is strictly governed by the shorter side of the sheet: $x < \frac{\min(A, B)}{2}$.

3. **Extreme Value Theorem on Compact Domains:**
   If $V(x)$ is continuous on the closed interval $\left[0, \frac{A}{2}\right]$ with $V(0) = 0$ and $V(A/2) = 0$, and positive on the interior, the absolute maximum must occur at an interior critical point where $V'(x) = 0$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Formulate the Volume Function $V(x)$

The dimensions of the original sheet are:
- Width $A = 30\text{ cm}$
- Length $B = 40\text{ cm}$

Cutting out corner squares of side length $x$:
- Height of the box:
  $$
  H(x) = x
  $$
- Width of the base:
  $$
  W(x) = 30 - 2x
  $$
- Length of the base:
  $$
  L(x) = 40 - 2x
  $$

The volume function is the product of these three dimensions:
$$
V(x) = x(30 - 2x)(40 - 2x)
$$

Expand the polynomial:
$$
(30 - 2x)(40 - 2x) = 1200 - 60x - 80x + 4x^2 = 4x^2 - 140x + 1200
$$
Multiplying by $x$:
$$
V(x) = 4x^3 - 140x^2 + 1200x \quad [\text{cm}^3]
$$

---

### Step 2: Determine the Feasible Physical Domain

All three physical dimensions must be strictly positive:
1. Height: $x > 0$
2. Width: $30 - 2x > 0 \iff 2x < 30 \iff x < 15$
3. Length: $40 - 2x > 0 \iff 2x < 40 \iff x < 20$

Taking the intersection of the three inequalities:
$$
\mathcal{D}_V = (0, 15) = \{x \in \mathbb{R} : 0 < x < 15\}
$$

*(If degenerate zero-volume boxes are included at the boundaries, the closed domain is $[0, 15]$).*

---

### Step 3: Compute the Derivative and Find Critical Points

Differentiate $V(x) = 4x^3 - 140x^2 + 1200x$ with respect to $x$:
$$
V'(x) = \frac{d}{dx}[4x^3 - 140x^2 + 1200x] = 12x^2 - 280x + 1200
$$

Set $V'(x) = 0$ to find stationary points:
$$
12x^2 - 280x + 1200 = 0
$$

Divide the entire equation by $4$:
$$
3x^2 - 70x + 300 = 0
$$

Apply the quadratic formula with $a = 3, b = -70, c = 300$:
$$
x = \frac{-(-70) \pm \sqrt{(-70)^2 - 4(3)(300)}}{2(3)} = \frac{70 \pm \sqrt{4900 - 3600}}{6} = \frac{70 \pm \sqrt{1300}}{6}
$$
Simplify the radical $\sqrt{1300} = \sqrt{100 \times 13} = 10\sqrt{13}$:
$$
x = \frac{70 \pm 10\sqrt{13}}{6} = \frac{35 \pm 5\sqrt{13}}{3}
$$

---

### Step 4: Evaluate and Filter the Critical Points

Evaluate the two mathematical solutions numerically using $\sqrt{13} \approx 3.605551$:

1. **First Root ($x_1$):**
   $$
   x_1 = \frac{35 - 5\sqrt{13}}{3} \approx \frac{35 - 5(3.605551)}{3} = \frac{35 - 18.027756}{3} = \frac{16.972244}{3} \approx 5.657415\text{ cm}
   $$
   Notice that $0 < 5.6574 < 15$. Thus, **$x_1 \in \mathcal{D}_V$ is physically feasible**.

2. **Second Root ($x_2$):**
   $$
   x_2 = \frac{35 + 5\sqrt{13}}{3} \approx \frac{35 + 18.027756}{3} = \frac{53.027756}{3} \approx 17.675919\text{ cm}
   $$
   Notice that $17.68 > 15$. If $x = 17.68$, the width would be:
   $$
   W = 30 - 2(17.68) = -5.36\text{ cm} < 0
   $$
   A negative side length is physically impossible. Thus, **$x_2 \notin \mathcal{D}_V$ is discarded as an unphysical artifact**.

The unique viable critical point is:
$$
\mathbf{x^* = \frac{35 - 5\sqrt{13}}{3} \approx 5.657\text{ cm}}
$$

---

### Step 5: Verification of the Maximum and Optimal Dimensions

1. **Second Derivative Test:**
   $$
   V''(x) = \frac{d}{dx}[12x^2 - 280x + 1200] = 24x - 280
   $$
   Evaluate at $x^* \approx 5.6574$:
   $$
   V''(x^*) = 24(5.6574) - 280 \approx 135.78 - 280 = -144.22 < 0
   $$
   Because $V''(x^*) < 0$, $x^*$ is a **strict local maximum**.
   Furthermore, on the compact interval $[0, 15]$:
   - $V(0) = 0$
   - $V(15) = 15(30 - 30)(40 - 30) = 0$
   - $V(x) > 0$ for all $x \in (0, 15)$
   Since $x^*$ is the only critical point inside $(0, 15)$, it must be the **absolute (global) maximum**.

2. **Optimal Dimensions of the Box:**
   - **Cutout / Height:**
     $$
     H = x^* \approx 5.657\text{ cm}
     $$
   - **Width:**
     $$
     W = 30 - 2x^* \approx 30 - 2(5.6574) = 30 - 11.315 = 18.685\text{ cm}
     $$
   - **Length:**
     $$
     L = 40 - 2x^* \approx 40 - 2(5.6574) = 40 - 11.315 = 28.685\text{ cm}
     $$

3. **Maximum Volume:**
   $$
   V_{\max} = H \times W \times L \approx 5.6574 \times 18.6851 \times 28.6851 \approx 3032.28\text{ cm}^3
   $$

---

## 4. Verification and Consistency Checks

1. **Numerical Sampling Around the Optimum:**
   | Cutout Size $x$ | Height $H$ | Width $W = 30 - 2x$ | Length $L = 40 - 2x$ | Volume $V(x)$ |
   |:---:|:---:|:---:|:---:|:---:|
   | $1.0\text{ cm}$ | $1.0$ | $28.0$ | $38.0$ | $1064.0\text{ cm}^3$ |
   | $3.0\text{ cm}$ | $3.0$ | $24.0$ | $34.0$ | $2448.0\text{ cm}^3$ |
   | $5.0\text{ cm}$ | $5.0$ | $20.0$ | $30.0$ | $3000.0\text{ cm}^3$ |
   | **$5.657\text{ cm}$ (Optimum)** | **$5.657$** | **$18.685$** | **$28.685$** | **$3032.28\text{ cm}^3$** |
   | $6.0\text{ cm}$ | $6.0$ | $18.0$ | $28.0$ | $3024.0\text{ cm}^3$ |
   | $8.0\text{ cm}$ | $8.0$ | $14.0$ | $24.0$ | $2688.0\text{ cm}^3$ |
   | $10.0\text{ cm}$ | $10.0$ | $10.0$ | $20.0$ | $2000.0\text{ cm}^3$ |
   | $14.0\text{ cm}$ | $14.0$ | $2.0$ | $12.0$ | $336.0\text{ cm}^3$ |
   | $15.0\text{ cm}$ | $15.0$ | $0.0$ | $10.0$ | $0.0\text{ cm}^3$ |

   The numerical table confirms that the volume peaks smoothly at $x \approx 5.66\text{ cm}$ and decreases in both directions.

2. **Derivative Factorization Check:**
   $$
   12(x - x_1)(x - x_2) = 12\left(x - \frac{35 - 5\sqrt{13}}{3}\right)\left(x - \frac{35 + 5\sqrt{13}}{3}\right)
   $$
   $$
   = 12\left(x^2 - \frac{70}{3}x + \frac{1225 - 325}{9}\right) = 12\left(x^2 - \frac{70}{3}x + \frac{900}{9}\right) = 12x^2 - 280x + 1200
   $$
   The product recovers the original derivative polynomial, validating algebraic precision.
