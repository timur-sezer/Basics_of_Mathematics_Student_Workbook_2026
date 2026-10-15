# Solution to Problem 7: A Trigonometric Function

## 1. Problem Statement

For the trigonometric function defined on the closed and bounded interval $[0, 2\pi]$:
$$
f(x) = \sin x + \cos x
$$

1. Compute the first derivative $f'(x)$ and determine all interior critical points in $(0, 2\pi)$.
2. Construct a sign chart for $f'(x)$ and identify the intervals of strict increase and decrease on $[0, 2\pi]$.
3. Compute the function values at all interior critical points and at both endpoints $x = 0$ and $x = 2\pi$.
4. Classify all local and global (absolute) extrema on the closed interval.
5. Provide a harmonic identity synthesis rewriting $f(x)$ as a single sine wave to geometrically verify the results.

---

## 2. Theoretical Background and Concepts

1. **Extreme Value Theorem and Extrema on a Closed Interval $[a, b]$:**
   By the Extreme Value Theorem, a continuous function on a closed bounded interval $[a, b]$ is guaranteed to attain an absolute maximum and an absolute minimum.
   Candidates for extrema are:
   - **Interior critical points:** points $c \in (a, b)$ where $f'(c) = 0$ or $f'(c)$ does not exist.
   - **Boundary endpoints:** $x = a$ and $x = b$.

2. **Classification of Endpoints:**
   - If $f'(x) > 0$ on $(a, a + \varepsilon)$, the function increases away from the left endpoint, making $x = a$ a **local minimum**.
   - If $f'(x) > 0$ on $(b - \varepsilon, b)$, the function increases toward the right endpoint, making $x = b$ a **local maximum**.

3. **Harmonic Addition Identity:**
   Any linear combination of sine and cosine of the same frequency can be written as a single phase-shifted wave:
   $$
   A \sin x + B \cos x = R \sin(x + \varphi), \qquad R = \sqrt{A^2 + B^2}, \quad \tan \varphi = \frac{B}{A}
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Derivative and Interior Critical Points

1. Differentiating term-by-term:
   $$
   f'(x) = \frac{d}{dx}[\sin x] + \frac{d}{dx}[\cos x] = \cos x - \sin x
   $$

2. Find stationary points in $(0, 2\pi)$ by setting $f'(x) = 0$:
   $$
   \cos x - \sin x = 0 \iff \sin x = \cos x
   $$
   Notice that $\cos x \neq 0$ when $\sin x = \cos x$ (if $\cos x = 0$, then $\sin x = \pm 1 \neq 0$). Dividing both sides by $\cos x$:
   $$
   \tan x = 1 \quad \text{for } x \in (0, 2\pi)
   $$
   The tangent function equals $1$ in the first and third quadrants:
   - Quadrant I:
     $$
     x_1 = \frac{\pi}{4}
     $$
   - Quadrant III:
     $$
     x_2 = \frac{\pi}{4} + \pi = \frac{5\pi}{4}
     $$

---

### Step 2: Sign Chart and Monotonicity on $[0, 2\pi]$

The critical points partition $[0, 2\pi]$ into three subintervals:
1. $\left[0, \frac{\pi}{4}\right)$
2. $\left(\frac{\pi}{4}, \frac{5\pi}{4}\right)$
3. $\left(\frac{5\pi}{4}, 2\pi\right]$

We test the sign of $f'(x) = \cos x - \sin x$:

- **Subinterval $\left[0, \frac{\pi}{4}\right)$:**
  Test $x = 0$:
  $$
  f'(0) = \cos(0) - \sin(0) = 1 - 0 = +1 > 0
  $$
  $f'(x) > 0 \implies f(x)$ is **strictly increasing** on $\left[0, \frac{\pi}{4}\right]$.

- **Subinterval $\left(\frac{\pi}{4}, \frac{5\pi}{4}\right)$:**
  Test $x = \pi$:
  $$
  f'(\pi) = \cos(\pi) - \sin(\pi) = -1 - 0 = -1 < 0
  $$
  $f'(x) < 0 \implies f(x)$ is **strictly decreasing** on $\left[\frac{\pi}{4}, \frac{5\pi}{4}\right]$.

- **Subinterval $\left(\frac{5\pi}{4}, 2\pi\right]$:**
  Test $x = \frac{3\pi}{2}$:
  $$
  f'\left(\frac{3\pi}{2}\right) = \cos\left(\frac{3\pi}{2}\right) - \sin\left(\frac{3\pi}{2}\right) = 0 - (-1) = +1 > 0
  $$
  $f'(x) > 0 \implies f(x)$ is **strictly increasing** on $\left[\frac{5\pi}{4}, 2\pi\right]$.

---

### Step 3: Evaluation at Critical Points and Endpoints

We evaluate the function $f(x) = \sin x + \cos x$ at all four candidate points:

1. **Left Endpoint ($x = 0$):**
   $$
   f(0) = \sin(0) + \cos(0) = 0 + 1 = 1
   $$
2. **First Interior Critical Point $\left(x = \frac{\pi}{4}\right)$:**
   $$
   f\left(\frac{\pi}{4}\right) = \sin\left(\frac{\pi}{4}\right) + \cos\left(\frac{\pi}{4}\right) = \frac{\sqrt{2}}{2} + \frac{\sqrt{2}}{2} = \sqrt{2} \approx 1.4142
   $$
3. **Second Interior Critical Point $\left(x = \frac{5\pi}{4}\right)$:**
   $$
   f\left(\frac{5\pi}{4}\right) = \sin\left(\frac{5\pi}{4}\right) + \cos\left(\frac{5\pi}{4}\right) = -\frac{\sqrt{2}}{2} - \frac{\sqrt{2}}{2} = -\sqrt{2} \approx -1.4142
   $$
4. **Right Endpoint ($x = 2\pi$):**
   $$
   f(2\pi) = \sin(2\pi) + \cos(2\pi) = 0 + 1 = 1
   $$

---

### Step 4: Comparison and Classification of Extrema

Ordering all four values:
$$
-\sqrt{2} < 1 < \sqrt{2}
$$

1. **Absolute (Global) Maximum:**
   The highest value attained on the interval is $\sqrt{2}$.
   - Occurs at the interior critical point **$x = \frac{\pi}{4}$**.
   - Maximum point: $\mathbf{\left(\frac{\pi}{4}, \sqrt{2}\right)}$.

2. **Absolute (Global) Minimum:**
   The lowest value attained on the interval is $-\sqrt{2}$.
   - Occurs at the interior critical point **$x = \frac{5\pi}{4}$**.
   - Minimum point: $\mathbf{\left(\frac{5\pi}{4}, -\sqrt{2}\right)}$.

3. **Boundary Local Extrema:**
   - **At $x = 0$:** Because $f(x)$ increases on $[0, \pi/4]$, $f(0) = 1$ is a **local minimum** with respect to the domain $[0, 2\pi]$.
   - **At $x = 2\pi$:** Because $f(x)$ increases on $[5\pi/4, 2\pi]$, $f(2\pi) = 1$ is a **local maximum** with respect to the domain $[0, 2\pi]$.

---

## 4. Verification and Consistency Checks

1. **Harmonic Representation Identity:**
   Let us rewrite $f(x)$ using $A = 1, B = 1$:
   $$
   f(x) = \sin x + \cos x = \sqrt{1^2 + 1^2} \left(\frac{1}{\sqrt{2}}\sin x + \frac{1}{\sqrt{2}}\cos x\right)
   $$
   Since $\cos(\pi/4) = \sin(\pi/4) = \frac{1}{\sqrt{2}}$:
   $$
   f(x) = \sqrt{2}\left(\sin x \cos\frac{\pi}{4} + \cos x \sin\frac{\pi}{4}\right) = \sqrt{2}\sin\left(x + \frac{\pi}{4}\right)
   $$
   - The amplitude is $R = \sqrt{2}$. The range of the standard sine is $[-1, 1]$, so the range of $f$ is $[-\sqrt{2}, \sqrt{2}]$.
   - Peak occurs when $x + \frac{\pi}{4} = \frac{\pi}{2} \implies x = \frac{\pi}{4}$, value $\sqrt{2}$.
   - Trough occurs when $x + \frac{\pi}{4} = \frac{3\pi}{2} \implies x = \frac{5\pi}{4}$, value $-\sqrt{2}$.
   - At $x = 0$: $\sqrt{2}\sin(\pi/4) = \sqrt{2}(1/\sqrt{2}) = 1$.
   - At $x = 2\pi$: $\sqrt{2}\sin(2\pi + \pi/4) = 1$.
   This confirms the calculus results.

2. **Second Derivative Test at Critical Points:**
   $$
   f''(x) = \frac{d}{dx}[\cos x - \sin x] = -\sin x - \cos x = -f(x)
   $$
   - At $x = \frac{\pi}{4}$: $f''(\pi/4) = -\sqrt{2} < 0 \implies$ strict local maximum ($\checkmark$).
   - At $x = \frac{5\pi}{4}$: $f''(5\pi/4) = -(-\sqrt{2}) = +\sqrt{2} > 0 \implies$ strict local minimum ($\checkmark$).
