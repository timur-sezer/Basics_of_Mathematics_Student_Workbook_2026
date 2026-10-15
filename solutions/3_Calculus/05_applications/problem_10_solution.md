# Solution to Problem 10: A Cable Through Water and Land

## 1. Problem Statement

A telecommunications company must lay a cable between two points separated by a river:
- Point $A$ is situated on one bank of a straight river of uniform width $w = 100\text{ m}$.
- Point $B$ is located on the opposite bank, positioned $L = 500\text{ m}$ downstream from the point directly opposite $A$.
- The installation cost per meter underwater is exactly twice the installation cost per meter on land ($c_{\text{water}} = 2 c_{\text{land}}$).

The cable will run underwater in a straight line from $A$ to an exit point $P$ on the opposite bank, and then along the bank on land from $P$ to $B$.

1. Construct a single-variable cost function $C(x)$ parameterized by the distance $x$ from the point directly opposite $A$ to the water-exit point $P$.
2. State the physically feasible domain of the variable $x$.
3. Compute the derivative $C'(x)$ and determine the critical point that minimizes the total installation cost.
4. Verify that this critical point represents an absolute minimum, and compare the optimal cost with both extreme boundary strategies ($x = 0$ and $x = 500$).
5. Reveal the fundamental physical connection between this optimization result and **Snell's Law of Refraction (Fermat's Principle)**.

---

## 2. Theoretical Background and Concepts

1. **Geometric Setup in Cartesian Coordinates:**
   Let the opposite bank containing point $B$ lie along the $x$-axis:
   - Origin $(0, 0)$: Point directly across the river from $A$.
   - Point $A$: $(0, 100)$ on the starting bank.
   - Point $B$: $(500, 0)$ on the destination bank.
   - Point $P(x, 0)$: The point where the cable emerges from the water, with $0 \le x \le 500$.

2. **Distance Formulas via the Pythagorean Theorem:**
   - **Underwater segment ($AP$):**
     $$
     d_{\text{water}}(x) = \sqrt{x^2 + 100^2} = \sqrt{x^2 + 10\,000}
     $$
   - **Land segment ($PB$):**
     $$
     d_{\text{land}}(x) = 500 - x
     $$

3. **Cost Formulation:**
   Let $c > 0$ be the cost per meter on land ($c_{\text{land}} = c$).
   Then $c_{\text{water}} = 2c$.
   Total cost is:
   $$
   C(x) = 2c \cdot d_{\text{water}}(x) + c \cdot d_{\text{land}}(x)
   $$
   Minimizing $C(x)$ is mathematically equivalent to minimizing the normalized cost function $f(x) = \frac{C(x)}{c}$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Formulate the Normalized Cost Function

The total cost is:
$$
C(x) = 2c \sqrt{x^2 + 10\,000} + c(500 - x)
$$
Factoring out the unit cost $c$:
$$
f(x) = \frac{C(x)}{c} = 2\sqrt{x^2 + 10\,000} + 500 - x
$$

---

### Step 2: Establish the Feasible Domain

The exit point $P(x, 0)$ must lie between the point opposite $A$ ($x = 0$) and the destination $B$ ($x = 500$):
- If $x < 0$, both the underwater path and the land path are strictly longer than at $x = 0$.
- If $x > 500$, the underwater path is longer and requires doubling back on land.
Therefore, the feasible domain is the compact interval:
$$
\mathcal{D} = [0, 500] = \{x \in \mathbb{R} : 0 \le x \le 500\}
$$

---

### Step 3: Compute the Derivative and Find the Optimal Point

Differentiate $f(x)$ with respect to $x$:
$$
f'(x) = \frac{d}{dx}\left[2(x^2 + 10\,000)^{1/2} + 500 - x\right]
$$
Using the chain rule:
$$
f'(x) = 2 \cdot \frac{1}{2}(x^2 + 10\,000)^{-1/2} \cdot (2x) - 1 = \frac{2x}{\sqrt{x^2 + 10\,000}} - 1
$$

Set $f'(x) = 0$ to find stationary points:
$$
\frac{2x}{\sqrt{x^2 + 10\,000}} - 1 = 0 \iff \frac{2x}{\sqrt{x^2 + 10\,000}} = 1
$$
Multiply through by the positive square root:
$$
2x = \sqrt{x^2 + 10\,000}
$$

Square both sides (valid since $x \ge 0$):
$$
4x^2 = x^2 + 10\,000
$$
Subtract $x^2$:
$$
3x^2 = 10\,000 \iff x^2 = \frac{10\,000}{3}
$$

Take the positive square root (since $x \ge 0$):
$$
x^* = \frac{100}{\sqrt{3}} = \frac{100\sqrt{3}}{3} \approx 57.735\text{ m}
$$

Notice that $0 < 57.735 < 500$.
The critical point is **strictly feasible**:
$$
\mathbf{x^* = \frac{100\sqrt{3}}{3} \approx 57.74\text{ m}}
$$

---

### Step 4: Verification of the Absolute Minimum

1. **Second Derivative Test:**
   Differentiate $f'(x) = \frac{2x}{\sqrt{x^2 + 10\,000}} - 1$ using the quotient rule:
   $$
   f''(x) = \frac{2\sqrt{x^2 + 10\,000} - 2x \cdot \frac{x}{\sqrt{x^2 + 10\,000}}}{x^2 + 10\,000} = \frac{2(x^2 + 10\,000) - 2x^2}{(x^2 + 10\,000)^{3/2}}
   $$
   $$
   f''(x) = \frac{20\,000}{(x^2 + 10\,000)^{3/2}}
   $$
   Because $20\,000 > 0$ and the denominator is strictly positive for all $x \in \mathbb{R}$:
   $$
   f''(x) > 0 \quad \forall x \in [0, 500]
   $$
   The cost function is **strictly convex** on the entire interval. Hence, $x^*$ is the unique **absolute global minimum**.

2. **Comparison with Extreme Boundary Strategies:**
   - **Strategy 1 ($x = 0$):** Perpendicular river crossing (shortest possible water path $= 100\text{ m}$, longest land path $= 500\text{ m}$):
     $$
     f(0) = 2\sqrt{0 + 10\,000} + 500 - 0 = 2(100) + 500 = 200 + 500 = 700\text{ cost units}
     $$
   - **Strategy 2 ($x = 500$):** Direct diagonal underwater line from $A$ to $B$ (zero land cable):
     $$
     f(500) = 2\sqrt{500^2 + 100^2} + 500 - 500 = 2\sqrt{250\,000 + 10\,000} = 2\sqrt{260\,000} = 200\sqrt{26} \approx 200(5.09902) \approx 1019.80\text{ cost units}
     $$
   - **Optimal Strategy ($x^* = 100/\sqrt{3} \approx 57.74\text{ m}$):**
     Underwater length:
     $$
     d_{\text{water}} = \sqrt{\left(\frac{100}{\sqrt{3}}\right)^2 + 100^2} = \sqrt{\frac{10\,000}{3} + \frac{30\,000}{3}} = \sqrt{\frac{40\,000}{3}} = \frac{200}{\sqrt{3}} \approx 115.47\text{ m}
     $$
     Land length:
     $$
     d_{\text{land}} = 500 - \frac{100}{\sqrt{3}} \approx 500 - 57.74 = 442.26\text{ m}
     $$
     Total normalized cost:
     $$
     f(x^*) = 2\left(\frac{200}{\sqrt{3}}\right) + \left(500 - \frac{100}{\sqrt{3}}\right) = \frac{400 - 100}{\sqrt{3}} + 500 = \frac{300}{\sqrt{3}} + 500 = 100\sqrt{3} + 500 \approx 173.21 + 500 = 673.21\text{ cost units}
     $$

**Cost Comparison:**
$$
f(x^*) = 673.21 < f(0) = 700 < f(500) \approx 1019.80
$$
The optimal solution achieves a significant cost reduction compared to both naive extremes.

---

### Step 5: Connection with Snell's Law and Fermat's Principle

```text
  Bank 1 (A)        A(0, 100)
   --------------------+---------------------------------
                       | \
           width = 100 |  \  underwater path
                       | θ \
   --------------------+----*---------------------------* Bank 2 (B)
  Bank 2 (B)         (0, 0) P(x*, 0)                  B(500, 0)
                       |<x*>|<-------- 500 - x -------->|
```

Let $\theta$ be the angle that the underwater cable makes with the normal (perpendicular) to the riverbank:
$$
\sin \theta = \frac{x}{\sqrt{x^2 + 100^2}}
$$

Look at our critical point equation from Step 3:
$$
\frac{2x}{\sqrt{x^2 + 100^2}} = 1 \implies \frac{x}{\sqrt{x^2 + 100^2}} = \frac{1}{2}
$$
Therefore:
$$
\sin \theta = \frac{1}{2} \implies \theta = 30^\circ
$$

This is precisely **Snell's Law of Refraction**:
$$
\frac{\sin \theta_{\text{water}}}{\sin \theta_{\text{land}}} = \frac{c_{\text{land}}}{c_{\text{water}}} = \frac{1}{2}
$$
Because the cable runs along the bank on land ($\theta_{\text{land}} = 90^\circ$, so $\sin \theta_{\text{land}} = 1$), the optimal underwater departure angle must satisfy $\sin \theta = 1/2 \implies \theta = 30^\circ$.
Nature minimizes the transit time of light across different media according to Fermat's Principle using the exact same mathematics.

---

## 4. Verification and Consistency Checks

1. **Trigonometric Geometry Consistency Check:**
   In the right triangle formed by the perpendicular width ($100\text{ m}$), downstream drift ($x^*$), and underwater cable:
   $$
   \tan(30^\circ) = \frac{1}{\sqrt{3}}
   $$
   By definition of tangent:
   $$
   \tan(30^\circ) = \frac{\text{opposite}}{\text{adjacent}} = \frac{x^*}{100} \implies x^* = 100 \tan(30^\circ) = \frac{100}{\sqrt{3}} \approx 57.735\text{ m}
   $$
   The trigonometric calculation confirms the calculus derivation.

2. **Numerical Sensitivity Table:**
   | Exit Location $x$ | Underwater Cost ($2 \cdot d_{\text{w}}$) | Land Cost ($d_{\text{l}}$) | Total Cost $f(x)$ |
   |:---:|:---:|:---:|:---:|
   | $0\text{ m}$ | $200.00$ | $500.00$ | $700.00$ |
   | $30\text{ m}$ | $208.81$ | $470.00$ | $678.81$ |
   | $50\text{ m}$ | $223.61$ | $450.00$ | $673.61$ |
   | **$57.74\text{ m}$ (Optimal)** | **$230.94$** | **$442.26$** | **$673.21$** |
   | $70\text{ m}$ | $244.13$ | $430.00$ | $674.13$ |
   | $100\text{ m}$ | $282.84$ | $400.00$ | $682.84$ |
   | $200\text{ m}$ | $447.21$ | $300.00$ | $747.21$ |
   | $500\text{ m}$ | $1019.80$ | $0.00$ | $1019.80$ |

   The numerical sensitivity table confirms that the cost reaches its minimum at $x \approx 57.74\text{ m}$.
