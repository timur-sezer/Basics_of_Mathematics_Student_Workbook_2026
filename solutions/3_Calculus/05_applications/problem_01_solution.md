# Solution to Problem 1: Motion — from Position to Velocity

## 1. Problem Statement

The rectilinear position of a moving particle along a coordinate axis is described by the kinematic position function:
$$
s(t) = t^3 - 6t^2 + 9t + 2, \qquad t \ge 0
$$
where $t$ is time in seconds and $s(t)$ is position in meters.

1. Determine the instantaneous velocity $v(t)$ and instantaneous acceleration $a(t)$ as functions of time.
2. Find all moments in time $t \ge 0$ at which the particle instantaneously comes to a stop (stationary points).
3. Determine the time intervals on which the particle moves in the positive direction of the axis and the intervals on which it moves in the negative direction.
4. Calculate the position and acceleration at each stop, and summarize the overall trajectory.

---

## 2. Theoretical Background and Concepts

1. **Kinematics via Differential Calculus:**
   - **Position $s(t)$:** The coordinate of the particle along the line.
   - **Velocity $v(t)$:** The instantaneous rate of change of position with respect to time:
     $$
     v(t) = s'(t) = \frac{ds}{dt}
     $$
   - **Acceleration $a(t)$:** The instantaneous rate of change of velocity with respect to time:
     $$
     a(t) = v'(t) = s''(t) = \frac{d^2s}{dt^2}
     $$

2. **Physical Meaning of the Sign of Velocity:**
   - **$v(t) > 0$:** Position $s(t)$ is strictly increasing; the particle travels in the **positive coordinate direction** (forward / rightward).
   - **$v(t) < 0$:** Position $s(t)$ is strictly decreasing; the particle travels in the **negative coordinate direction** (backward / leftward).
   - **$v(t) = 0$:** The particle is instantaneously at rest. If the sign of $v(t)$ changes across $t_0$, the particle reverses its physical direction of motion.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute Velocity $v(t)$ and Acceleration $a(t)$

1. **Velocity $v(t)$:**
   Differentiate $s(t) = t^3 - 6t^2 + 9t + 2$ with respect to $t$:
   $$
   v(t) = \frac{d}{dt}[t^3 - 6t^2 + 9t + 2] = 3t^2 - 12t + 9
   $$
   Factor out the common factor $3$:
   $$
   v(t) = 3(t^2 - 4t + 3) = 3(t - 1)(t - 3) \quad [\mathrm{m/s}]
   $$

2. **Acceleration $a(t)$:**
   Differentiate $v(t) = 3t^2 - 12t + 9$ with respect to $t$:
   $$
   a(t) = \frac{d}{dt}[3t^2 - 12t + 9] = 6t - 12
   $$
   Factor out $6$:
   $$
   a(t) = 6(t - 2) \quad [\mathrm{m/s^2}]
   $$

---

### Step 2: Find the Times When the Particle Stops

The particle is instantaneously at rest when $v(t) = 0$:
$$
3(t - 1)(t - 3) = 0
$$
Since $t \ge 0$, there are two stopping moments:
$$
t_1 = 1\text{ s}, \qquad t_2 = 3\text{ s}
$$

Let us determine the state of the particle at both stops:
- **At $t_1 = 1\text{ s}$:**
  - Position:
    $$
    s(1) = 1^3 - 6(1^2) + 9(1) + 2 = 1 - 6 + 9 + 2 = 6\text{ m}
    $$
  - Acceleration:
    $$
    a(1) = 6(1 - 2) = -6\text{ m/s^2}
    $$
    Since $a(1) < 0$, the particle is accelerating in the negative direction, causing it to reverse from forward to backward motion.
- **At $t_2 = 3\text{ s}$:**
  - Position:
    $$
    s(3) = 3^3 - 6(3^2) + 9(3) + 2 = 27 - 54 + 27 + 2 = 2\text{ m}
    $$
  - Acceleration:
    $$
    a(3) = 6(3 - 2) = +6\text{ m/s^2}
    $$
    Since $a(3) > 0$, the particle accelerates in the positive direction, reversing from backward to forward motion.

---

### Step 3: Intervals and Direction of Motion

The two stopping times $t = 1$ and $t = 3$ divide the temporal domain $[0, \infty)$ into three distinct intervals:

1. **Interval $t \in [0, 1)$:**
   - At $t = 0$: $v(0) = 3(0 - 1)(0 - 3) = +9\text{ m/s} > 0$.
   - Since both factors $(t - 1) < 0$ and $(t - 3) < 0$, their product is positive:
     $$
     v(t) > 0 \quad \forall t \in [0, 1)
     $$
   - The particle moves in the **positive direction**, advancing from initial position $s(0) = 2\text{ m}$ to $s(1) = 6\text{ m}$.

2. **Interval $t \in (1, 3)$:**
   - Test $t = 2$: $v(2) = 3(2 - 1)(2 - 3) = 3(1)(-1) = -3\text{ m/s} < 0$.
   - Here $(t - 1) > 0$ while $(t - 3) < 0$, so:
     $$
     v(t) < 0 \quad \forall t \in (1, 3)
     $$
   - The particle moves in the **negative direction**, reversing from $s(1) = 6\text{ m}$ back to $s(3) = 2\text{ m}$.

3. **Interval $t \in (3, \infty)$:**
   - Test $t = 4$: $v(4) = 3(4 - 1)(4 - 3) = 3(3)(1) = +9\text{ m/s} > 0$.
   - Both $(t - 1) > 0$ and $(t - 3) > 0$, so:
     $$
     v(t) > 0 \quad \forall t \in (3, \infty)
     $$
   - The particle moves in the **positive direction**, accelerating forward from $s(3) = 2\text{ m}$ toward $+\infty$.

---

### Step 4: Summary Table of Motion

| Time Interval | Velocity $v(t)$ | Acceleration $a(t)$ | Direction of Motion | Position Range |
|:---:|:---:|:---:|:---|:---:|
| **$t = 0$** | $+9\text{ m/s}$ | $-12\text{ m/s^2}$ | Starts moving right | $s(0) = 2\text{ m}$ |
| **$(0, 1)$** | Positive ($>0$) | Negative ($<0$) | **Moving forward** (decelerating) | $2\text{ m} \to 6\text{ m}$ |
| **$t = 1$** | **$0\text{ m/s}$** | **$-6\text{ m/s^2}$** | **First Stop** (reversal point) | $s(1) = 6\text{ m}$ |
| **$(1, 2)$** | Negative ($<0$) | Negative ($<0$) | **Moving backward** (speeding up) | $6\text{ m} \to 4\text{ m}$ |
| **$t = 2$** | $-3\text{ m/s}$ | $0\text{ m/s^2}$ | Peak backward speed | $s(2) = 4\text{ m}$ |
| **$(2, 3)$** | Negative ($<0$) | Positive ($>0$) | **Moving backward** (slowing down) | $4\text{ m} \to 2\text{ m}$ |
| **$t = 3$** | **$0\text{ m/s}$** | **$+6\text{ m/s^2}$** | **Second Stop** (reversal point) | $s(3) = 2\text{ m}$ |
| **$(3, \infty)$** | Positive ($>0$) | Positive ($>0$) | **Moving forward** (accelerating) | $2\text{ m} \to +\infty$ |

---

## 4. Verification and Consistency Checks

1. **Total Distance vs. Net Displacement on $[0, 3]$:**
   - **Net displacement:**
     $$
     \Delta s = s(3) - s(0) = 2 - 2 = 0\text{ m}
     $$
     In integral form:
     $$
     \int_0^3 v(t) \, dt = \int_0^3 (3t^2 - 12t + 9) \, dt = \Big[t^3 - 6t^2 + 9t\Big]_0^3 = (27 - 54 + 27) - 0 = 0\text{ m} \quad (\checkmark)
     $$
   - **Total distance traveled:**
     $$
     d = |s(1) - s(0)| + |s(3) - s(1)| = |6 - 2| + |2 - 6| = 4 + 4 = 8\text{ m}
     $$
     In integral form:
     $$
     \int_0^3 |v(t)| \, dt = \int_0^1 (3t^2 - 12t + 9) \, dt - \int_1^3 (3t^2 - 12t + 9) \, dt = 4 - (-4) = 8\text{ m} \quad (\checkmark)
     $$
   The kinematic integration verifies both the turning points and directional segments.
