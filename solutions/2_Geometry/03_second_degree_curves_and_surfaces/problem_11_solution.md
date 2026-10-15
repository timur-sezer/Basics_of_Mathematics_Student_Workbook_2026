# Solution to Exercise 11: Two Similar Surfaces

## 1. Problem Statement

Compare the two second-degree surfaces in three-dimensional space $\mathbb{R}^3$:
$$
\text{Surface 1: } x^2 + y^2 - z^2 = 1
$$
$$
\text{Surface 2: } x^2 + y^2 - z^2 = -1 \iff z^2 - (x^2 + y^2) = 1
$$

1. For several test values of height $z = c$, determine whether a real cross-section exists and calculate its radius.
2. Based on the behavior of these horizontal cross-sections, identify and contrast the qualitative shapes and connectivity of both surfaces.
3. Classify both surfaces by their standard geometric names.

---

## 2. Theoretical Background and Concepts

1. **Central Quadrics of Hyperbolic Type:**
   Equations involving two positive squared terms and one negative squared term represent hyperboloids of revolution:
   - **Hyperboloid of One Sheet:** $\frac{x^2}{a^2} + \frac{y^2}{b^2} - \frac{z^2}{c^2} = +1$.
     The surface is connected in a single continuous piece. Horizontal slices $z = \text{const}$ exist for **all** $z \in \mathbb{R}$ and are non-empty ellipses (or circles when $a = b$).
   - **Hyperboloid of Two Sheets:** $\frac{x^2}{a^2} + \frac{y^2}{b^2} - \frac{z^2}{c^2} = -1 \iff \frac{z^2}{c^2} - \left(\frac{x^2}{a^2} + \frac{y^2}{b^2}\right) = +1$.
     The surface consists of two separate, disconnected sheets separated by a gap along the $z$-axis (where $|z| < c$).

2. **Rotational Symmetry:**
   Because the terms $x^2 + y^2 = r^2$ appear together, both surfaces possess complete rotational symmetry about the $z$-axis. Slicing with any horizontal plane $z = c$ always produces a circle centered on the $z$-axis.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Cross-Sectional Analysis of Surface 1 ($x^2 + y^2 - z^2 = 1$)

Isolate the horizontal circular term by setting $z = c$:
$$
x^2 + y^2 = 1 + c^2
$$

Notice that for every real number $c \in \mathbb{R}$, $c^2 \ge 0$, which implies:
$$
1 + c^2 \ge 1 > 0 \quad \text{for all } c \in \mathbb{R}
$$
Therefore, **a real cross-section exists for every single height $c$ without exception**.
Every horizontal slice is a **circle** of radius:
$$
R_1(c) = \sqrt{1 + c^2}
$$

**Evaluate at Specific Test Values:**
- **At $c = 0$ (Equator):**
  $x^2 + y^2 = 1 + 0 = 1 \implies R_1(0) = 1$.
  The minimum radius occurs at the waist circle (throat) with radius $1$.
- **At $c = \pm 1$:**
  $x^2 + y^2 = 1 + 1^2 = 2 \implies R_1(\pm 1) = \sqrt{2} \approx 1.414$.
- **At $c = \pm \sqrt{3}$:**
  $x^2 + y^2 = 1 + 3 = 4 \implies R_1(\pm \sqrt{3}) = 2$.
- **At $c = \pm 2$:**
  $x^2 + y^2 = 1 + 4 = 5 \implies R_1(\pm 2) = \sqrt{5} \approx 2.236$.

**Qualitative Shape:**
Surface 1 is a single continuous, open tube with an hourglass (cooling-tower) shape that narrows to a minimum radius of $1$ at $z = 0$ and flares out quadratically as $|z| \to \infty$. It is connected in one single continuous piece, known as a **hyperboloid of one sheet** (Polish: *hiperboloida jednopowłokowa*).

---

### Step 2: Cross-Sectional Analysis of Surface 2 ($x^2 + y^2 - z^2 = -1$)

Rearrange the equation and set $z = c$:
$$
x^2 + y^2 = c^2 - 1
$$

The existence of a real cross-section requires the right-hand side to be non-negative:
$$
c^2 - 1 \ge 0 \iff c^2 \ge 1 \iff |c| \ge 1
$$

**Case Analysis Based on $c$:**
- **Case 1: $|c| < 1$ (e.g., $c = 0, c = 0.5, c = -0.8$):**
  $c^2 - 1 < 0$.
  For instance, at $c = 0$: $x^2 + y^2 = -1$.
  Since a sum of real squares cannot be negative, there are **no real points** (empty set $\emptyset$).
  There is a complete spatial gap of height $2$ (from $z = -1$ to $z = +1$) where no part of the surface exists.
- **Case 2: $|c| = 1$ ($c = +1$ or $c = -1$):**
  $x^2 + y^2 = 1^2 - 1 = 0 \implies (x, y) = (0, 0)$.
  The cross-section degenerates into a **single point**:
  - Upper vertex: $(0, 0, 1)$
  - Lower vertex: $(0, 0, -1)$
- **Case 3: $|c| > 1$ (e.g., $c = \pm \sqrt{2}, c = \pm 2$):**
  $c^2 - 1 > 0$, forming a **circle** of radius:
  $$
  R_2(c) = \sqrt{c^2 - 1}
  $$
  - At $c = \pm \sqrt{2}$: $x^2 + y^2 = 2 - 1 = 1 \implies R_2 = 1$.
  - At $c = \pm 2$: $x^2 + y^2 = 4 - 1 = 3 \implies R_2 = \sqrt{3} \approx 1.732$.
  - At $c = \pm \sqrt{5}$: $x^2 + y^2 = 5 - 1 = 4 \implies R_2 = 2$.

**Qualitative Shape:**
Surface 2 is disconnected into two separate, opposing bowl-shaped shells: an upper bowl opening upwards starting from the vertex $(0, 0, 1)$ for $z \ge 1$, and a lower bowl opening downwards starting from the vertex $(0, 0, -1)$ for $z \le -1$. It consists of two separate sheets, known as a **hyperboloid of two sheets** (Polish: *hiperboloida dwupowłokowa*).

---

### Step 3: Comparative Summary Table

| Property | Surface 1: $x^2 + y^2 - z^2 = 1$ | Surface 2: $x^2 + y^2 - z^2 = -1$ |
| :--- | :--- | :--- |
| **Standard Name** | **Hyperboloid of One Sheet** | **Hyperboloid of Two Sheets** |
| **Connectivity** | Connected (single surface) | Disconnected (two separate shells) |
| **Cross-Section at $z = 0$** | Waist circle of radius $R = 1$ | Empty set $\emptyset$ (spatial gap) |
| **Domain of Existence for $z$** | All $z \in (-\infty, \infty)$ | Only $|z| \ge 1$ ($z \in (-\infty, -1] \cup [1, \infty)$) |
| **Cross-Section Radius $R(c)$** | $R_1(c) = \sqrt{1 + c^2} \ge 1$ | $R_2(c) = \sqrt{c^2 - 1} \ge 0$ |
| **Vertical Slices ($x=0$ or $y=0$)** | Hyperbolas crossing the equator | Hyperbolas crossing the $z$-axis at $\pm 1$ |
| **Asymptotic Boundary** | Common asymptotic cone $x^2 + y^2 = z^2$ | Common asymptotic cone $x^2 + y^2 = z^2$ |

---

## 4. Verification and Consistency Checks

1. **Common Asymptotic Cone Verification:**
   As $|c| \to \infty$, both radii asymptotically approach the cone radius $R_{\text{cone}}(c) = |c|$:
   - For Surface 1: $R_1(c) = \sqrt{c^2 + 1} = |c|\sqrt{1 + \frac{1}{c^2}} \approx |c| + \frac{1}{2|c|}$.
   - For Surface 2: $R_2(c) = \sqrt{c^2 - 1} = |c|\sqrt{1 - \frac{1}{c^2}} \approx |c| - \frac{1}{2|c|}$.
   As $|c|$ grows, Surface 1 hugs the cone from the *outside*, while Surface 2 hugs the cone from the *inside*:
   $$
   R_2(c) < |c| < R_1(c) \quad \text{for all } |c| > 1 \quad (\checkmark)
   $$

2. **Test Point Verification on Both Surfaces:**
   - On Surface 1: $(1, 0, 0) \implies 1^2 + 0^2 - 0^2 = 1 \quad (\checkmark)$
   - On Surface 2: $(0, 0, 1) \implies 0^2 + 0^2 - 1^2 = -1 \quad (\checkmark)$
