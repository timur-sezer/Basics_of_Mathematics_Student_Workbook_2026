# Solution to Problem 5: Distance from Velocity

## 1. Problem Statement

The rectilinear velocity of a car during the first five seconds of travel ($0 \le t \le 5\text{ s}$) is described by the linear kinematic function:
$$
v(t) = 4t + 2 \quad [\mathrm{m/s}]
$$

1. Compute the total distance traveled by the car during this 5-second interval.
2. Explain fundamentally from first principles and the Fundamental Theorem of Calculus why the definite integral of velocity yields the change in position (displacement).
3. Explain what essential modifications must be made to the mathematical model if the velocity function were to take both positive and negative values.

---

## 2. Theoretical Background and Concepts

1. **Velocity and Displacement:**
   Velocity $v(t)$ is defined as the time derivative of position $s(t)$:
   $$
   v(t) = \frac{ds}{dt} = s'(t)
   $$
   By the Fundamental Theorem of Calculus:
   $$
   \int_{t_1}^{t_2} v(t) \, dt = \int_{t_1}^{t_2} s'(t) \, dt = s(t_2) - s(t_1) = \Delta s
   $$
   The definite integral of velocity across $[t_1, t_2]$ computes the **net displacement** $\Delta s$ (the difference between the final and initial position coordinates).

2. **Displacement vs. Total Distance Traveled:**
   - **Net Displacement ($\Delta s$):** An algebraic vector quantity with sign:
     $$
     \Delta s = \int_{t_1}^{t_2} v(t) \, dt
     $$
   - **Total Distance Traveled ($d$):** A cumulative scalar quantity that measures total path length (what an automobile odometer records). It is computed by integrating the **speed** $|v(t)|$:
     $$
     d = \int_{t_1}^{t_2} |v(t)| \, dt
     $$

3. **Equivalence Condition:**
   Whenever the velocity does not change sign and remains non-negative ($v(t) \ge 0$) throughout the entire interval $[t_1, t_2]$, $|v(t)| = v(t)$.
   Under this condition, net displacement and total distance traveled are identical:
   $$
   d = \Delta s = \int_{t_1}^{t_2} v(t) \, dt
   $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Sign Analysis of the Velocity Function

Examine $v(t) = 4t + 2$ on the domain $t \in [0, 5]$:
- At $t = 0$: $v(0) = 4(0) + 2 = 2\text{ m/s} > 0$.
- For all $t \ge 0$: $4t \ge 0 \implies 4t + 2 \ge 2 > 0$.
The velocity is **strictly positive** throughout the entire 5-second duration:
$$
v(t) > 0 \quad \forall t \in [0, 5]
$$
Because the car never reverses direction ($v(t) > 0$), the total distance traveled $d$ is equal to the definite integral of $v(t)$.

---

### Step 2: Compute the Distance Traveled

Set up the definite integral:
$$
d = \int_0^5 v(t) \, dt = \int_0^5 (4t + 2) \, dt
$$

1. Find the antiderivative:
   $$
   \int (4t + 2) \, dt = 4\left(\frac{t^2}{2}\right) + 2t = 2t^2 + 2t
   $$

2. Apply the Newton-Leibniz formula on $[0, 5]$:
   $$
   d = \Big[2t^2 + 2t\Big]_0^5
   $$

3. Evaluate at the boundaries:
   - At $t = 5$:
     $$
     2(5^2) + 2(5) = 2(25) + 10 = 50 + 10 = 60\text{ m}
     $$
   - At $t = 0$:
     $$
     2(0^2) + 2(0) = 0\text{ m}
     $$

4. Compute the difference:
   $$
   d = 60 - 0 = 60\text{ meters}
   $$

The car travels an exact distance of **$60$ meters** during the first 5 seconds.

---

### Step 3: Why the Integral of Velocity Gives the Change in Position

1. **Riemann Sum Perspective (Accumulation of Infinitesimal Steps):**
   Partition the time interval $[0, 5]$ into $n$ small time increments of width $\Delta t$.
   During each small interval $[t_{k-1}, t_k]$, the velocity is approximately constant at $v(t_k^*)$.
   The displacement traveled during this small slice of time is:
   $$
   \Delta s_k \approx v(t_k^*) \cdot \Delta t
   $$
   The total change in position over the entire journey is the sum of these infinitesimal displacements:
   $$
   \Delta s = \sum_{k=1}^n \Delta s_k \approx \sum_{k=1}^n v(t_k^*) \Delta t
   $$
   In the limit as $\Delta t \to 0$ ($n \to \infty$), the Riemann sum converges to the definite integral:
   $$
   \Delta s = \lim_{n \to \infty} \sum_{k=1}^n v(t_k^*) \Delta t = \int_0^5 v(t) \, dt
   $$

2. **Differential Perspective:**
   The definition $v(t) = \frac{ds}{dt}$ states that $ds = v(t) \, dt$. Summing (integrating) all tiny position increments $ds$ along the timeline from $t = 0$ to $t = 5$ directly yields the net change in coordinate:
   $$
   \int_0^5 ds = s(5) - s(0)
   $$

---

### Step 4: What Must Be Changed if Velocity Takes Negative Values

If the vehicle were to reverse direction during the motion (so that $v(t) < 0$ on some sub-intervals):

1. **The Definite Integral Alone Is Insufficient for Distance:**
   The standard integral $\int_{t_1}^{t_2} v(t) \, dt$ would no longer compute the distance traveled. Instead, it would compute the **net displacement**:
   $$
   \text{Displacement} = s(t_2) - s(t_1) = \Delta s
   $$
   Forward motion ($v > 0$) would add to the integral, while reverse motion ($v < 0$) would subtract from it. For example, if a car drives 60 meters forward and then 20 meters in reverse, its net displacement is $+40$ meters, but the odometer has accumulated $80$ meters of travel.

2. **The Corrected Distance Formula:**
   To find the actual **total distance traveled**, one must integrate the **speed** (the magnitude of velocity):
   $$
   d = \int_{t_1}^{t_2} |v(t)| \, dt
   $$

3. **Practical Computational Procedure:**
   - Solve $v(t) = 0$ to find the reversal moments $t_r$.
   - Partition the time domain into sub-intervals where velocity maintains a constant sign: $[t_1, t_r]$ and $[t_r, t_2]$.
   - Negate the integral on the intervals where $v(t) < 0$:
     $$
     d = \int_{t_1}^{t_r} v(t) \, dt + \int_{t_r}^{t_2} (-v(t)) \, dt = \Big|\Delta s_1\Big| + \Big|\Delta s_2\Big|
     $$

---

## 4. Verification and Consistency Checks

1. **Geometric Area Verification (Trapezoid Formula):**
   The velocity graph $v(t) = 4t + 2$ is a straight line. The region under the curve on $[0, 5]$ is a **trapezoid**:
   - Left vertical parallel side: $a = v(0) = 2\text{ m/s}$
   - Right vertical parallel side: $b = v(5) = 4(5) + 2 = 22\text{ m/s}$
   - Horizontal base (height of trapezoid): $h = 5 - 0 = 5\text{ s}$
   Using the geometric trapezoid formula:
   $$
   \text{Area} = \frac{a + b}{2} \cdot h = \frac{2 + 22}{2} \cdot 5 = \frac{24}{2} \cdot 5 = 12 \cdot 5 = 60\text{ meters}
   $$
   The geometric area matches the analytical integral $60\text{ m}$ identically.

2. **Average Velocity Verification:**
   The average velocity over $[0, 5]$ is:
   $$
   \bar{v} = \frac{v(0) + v(5)}{2} = \frac{2 + 22}{2} = 12\text{ m/s}
   $$
   The distance traveled at average velocity $\bar{v}$ for $\Delta t = 5\text{ s}$ is:
   $$
   d = \bar{v} \cdot \Delta t = 12\text{ m/s} \times 5\text{ s} = 60\text{ meters}
   $$
   This reinforces complete physical consistency.
