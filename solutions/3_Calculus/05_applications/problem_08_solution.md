# Solution to Problem 8: Number of Requests Handled by a Server

## 1. Problem Statement

The rate at which HTTP requests arrive at a cloud web server during the first 5 minutes of a traffic surge ($0 \le t \le 5\text{ min}$) is modeled by the linear rate function:
$$
r(t) = 100 + 20t \quad [\text{requests/min}]
$$

1. Compute the total number of requests $R_{\text{total}}$ that arrive at the server during this 5-minute window.
2. Compute the average rate of incoming requests $r_{\text{avg}}$ over the interval $[0, 5]$.
3. Evaluate the boundary arrival rates $r(0)$ and $r(5)$ and compare the average rate $r_{\text{avg}}$ with their arithmetic mean.
4. Explain why the integral average of a linear rate function matches the arithmetic mean of its endpoints.

---

## 2. Theoretical Background and Concepts

1. **Continuous Accumulation from Rate Functions:**
   When a process occurs at a continuously varying rate $r(t)$ [units/time], the total accumulated quantity $Q$ over an interval $[t_1, t_2]$ is given by the definite integral:
   $$
   Q = \int_{t_1}^{t_2} r(t) \, dt
   $$
   In computer systems, network packet processing, and server throughput analysis, summing infinitesimal request arrivals $r(t) \, dt$ gives the exact total request volume.

2. **Average Value of a Continuous Rate:**
   $$
   r_{\text{avg}} = \frac{1}{t_2 - t_1} \int_{t_1}^{t_2} r(t) \, dt = \frac{Q_{\text{total}}}{\Delta t}
   $$

3. **Special Property of Linear Functions:**
   For any affine/linear function $f(t) = mt + k$, the graph is a straight line, and the area under the curve is an exact trapezoid. By geometry:
   $$
   \int_a^b f(t) \, dt = \frac{f(a) + f(b)}{2} \cdot (b - a)
   $$
   Dividing by the interval length $(b - a)$ yields:
   $$
   f_{\text{avg}} = \frac{f(a) + f(b)}{2} = f\left(\frac{a + b}{2}\right)
   $$
   The continuous integral average of any linear function coincides precisely with the simple arithmetic average of its endpoints and with the value at the interval midpoint.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Total Number of Requests

The total requests accumulated over the 5-minute interval is:
$$
R_{\text{total}} = \int_0^5 r(t) \, dt = \int_0^5 (100 + 20t) \, dt
$$

1. Find the general antiderivative:
   $$
   \int (100 + 20t) \, dt = 100t + 20\left(\frac{t^2}{2}\right) = 100t + 10t^2
   $$

2. Apply the Fundamental Theorem of Calculus on $[0, 5]$:
   $$
   R_{\text{total}} = \Big[100t + 10t^2\Big]_0^5
   $$

3. Evaluate at the boundaries:
   - Upper limit ($t = 5\text{ min}$):
     $$
     100(5) + 10(5^2) = 500 + 10(25) = 500 + 250 = 750
     $$
   - Lower limit ($t = 0\text{ min}$):
     $$
     100(0) + 10(0^2) = 0
     $$

4. Compute the total count:
   $$
   R_{\text{total}} = 750 - 0 = 750\text{ requests}
   $$

The server handles an exact total of **$750$ requests** during the 5 minutes.

---

### Step 2: Compute the Average Arrival Rate $r_{\text{avg}}$

The total duration is:
$$
\Delta t = 5 - 0 = 5\text{ minutes}
$$

Apply the average rate formula:
$$
r_{\text{avg}} = \frac{1}{\Delta t} \int_0^5 r(t) \, dt = \frac{R_{\text{total}}}{\Delta t} = \frac{750\text{ requests}}{5\text{ minutes}} = 150\text{ requests/min}
$$

The average arrival rate is:
$$
\mathbf{r_{\text{avg}} = 150\text{ requests/min}}
$$

---

### Step 3: Compare with the Endpoint Values

Evaluate the arrival rate at the beginning and end of the interval:
- Initial rate at $t = 0$:
  $$
  r(0) = 100 + 20(0) = 100\text{ requests/min}
  $$
- Final rate at $t = 5$:
  $$
  r(5) = 100 + 20(5) = 100 + 100 = 200\text{ requests/min}
  $$

Compute the arithmetic average of these two endpoint values:
$$
\frac{r(0) + r(5)}{2} = \frac{100 + 200}{2} = \frac{300}{2} = 150\text{ requests/min}
$$

**Comparison:**
$$
r_{\text{avg}} = \frac{r(0) + r(5)}{2} = 150\text{ requests/min}
$$
The continuous integral average $r_{\text{avg}}$ is **strictly identical** to the discrete arithmetic average of the endpoint values.

---

### Step 4: Explanation of the Exact Agreement

1. **Linear Symmetry:**
   The function $r(t) = 100 + 20t$ changes at a constant, uniform slope of $20\text{ requests/min}^2$.
   - For every second of time symmetrically positioned before the midpoint ($t = 2.5 - \tau$), the rate is below the midpoint rate by $20\tau$.
   - For the corresponding second positioned after the midpoint ($t = 2.5 + \tau$), the rate is above the midpoint rate by $20\tau$.
   - When integrating, these symmetrical deviations cancel out identically:
     $$
     [r(2.5 - \tau) + r(2.5 + \tau)] = (150 - 20\tau) + (150 + 20\tau) = 300 = 2 \times 150
     $$
   Consequently, the mean height across the interval is precisely the height at the temporal midpoint:
   $$
   r(2.5) = 100 + 20(2.5) = 100 + 50 = 150\text{ requests/min}
   $$

2. **Contrast with Non-Linear Rates:**
   If the request rate grew quadratically (e.g., $g(t) = 100 + 4t^2$, with $g(0) = 100$ and $g(5) = 200$), the endpoint arithmetic mean would still be $150$, but the true integral average would be:
   $$
   g_{\text{avg}} = \frac{1}{5}\int_0^5 (100 + 4t^2) \, dt = \frac{1}{5}\left[100(5) + \frac{4(125)}{3}\right] = 100 + \frac{100}{3} \approx 133.33 \neq 150
   $$
   The identity $f_{\text{avg}} = \frac{f(a) + f(b)}{2}$ is a unique signature of **linear growth**.

---

## 4. Verification and Consistency Checks

1. **Trapezoidal Geometry Check:**
   The area under $r(t) = 100 + 20t$ on $[0, 5]$ is a trapezoid with parallel vertical sides $a = 100$ and $b = 200$, and base width $h = 5$:
   $$
   \text{Area} = \frac{a + b}{2} \cdot h = \frac{100 + 200}{2} \times 5 = 150 \times 5 = 750\text{ requests}
   $$
   The geometric area formula confirms the integral calculation.

2. **Dimensional Consistency Check:**
   - Units of integrand: $\text{requests/min}$
   - Units of differential $dt$: $\text{min}$
   - Units of integral: $(\text{requests/min}) \times \text{min} = \text{requests}$
   - Units of average rate: $\frac{\text{requests}}{\text{min}} = \text{requests/min}$
   All physical dimensions match the server metrics.
