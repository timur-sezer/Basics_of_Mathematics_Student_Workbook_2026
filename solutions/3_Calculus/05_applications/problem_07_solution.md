# Solution to Problem 7: Exponential Growth

## 1. Problem Statement

Consider the classical Malthusian exponential growth model:
$$
N(t) = N_0 e^{kt}, \qquad k > 0, \quad N_0 > 0
$$
where $N(t)$ is the population at time $t$, $N_0$ is the initial population at $t = 0$, and $k$ is the intrinsic continuous growth rate constant.

1. Verify by differentiation that $N(t)$ satisfies the first-order differential relation:
   $$
   N'(t) = k N(t)
   $$
2. Derive the exact mathematical formula for the population doubling time $T_d$.
3. Explain why the doubling time is completely independent of the initial population size $N_0$.
4. Analyze the implications of this scale invariance property.

---

## 2. Theoretical Background and Concepts

1. **The Law of Natural Growth:**
   In biological, demographic, and financial systems with unconstrained resources, the rate of increase of a quantity is directly proportional to its current magnitude:
   $$
   \frac{dN}{dt} \propto N(t) \iff \frac{dN}{dt} = k N(t)
   $$
   The constant of proportionality $k$ represents the per-capita growth rate:
   $$
   k = \frac{N'(t)}{N(t)}
   $$

2. **The Natural Exponential as the Unique Eigenfunction of Differentiation:**
   The function $e^{kt}$ is the fundamental solution to the differential equation $y' = ky$. Multiplying by a constant $N_0$ scales the solution to fit the initial condition $N(0) = N_0 e^0 = N_0$.

3. **Scale Invariance (Multiplicative Memorylessness):**
   A function $f(t)$ is scale-invariant under time shifts if the ratio $\frac{f(t + \Delta t)}{f(t)}$ depends only on the duration $\Delta t$, and not on the absolute population or starting time.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Verification of the Differential Relation

Differentiate $N(t) = N_0 e^{kt}$ with respect to $t$ using the chain rule:
$$
N'(t) = \frac{d}{dt}\left[N_0 e^{kt}\right] = N_0 \frac{d}{dt}\left[e^{kt}\right]
$$

Applying $\frac{d}{dt}[e^{u(t)}] = e^{u(t)} \cdot u'(t)$ with $u(t) = kt$:
$$
\frac{d}{dt}[e^{kt}] = e^{kt} \cdot \frac{d}{dt}[kt] = k e^{kt}
$$

Substitute this back:
$$
N'(t) = N_0 \cdot (k e^{kt})
$$

Rearrange terms using the commutativity of multiplication:
$$
N'(t) = k \cdot (N_0 e^{kt})
$$

Recognizing that $N(t) = N_0 e^{kt}$:
$$
N'(t) = k N(t)
$$

This verifies that the instantaneous rate of population growth is at every moment exactly equal to $k$ times the current population size.

---

### Step 2: Determine the Doubling Time $T_d$

By definition, the doubling time $T_d$ is the time duration required for the population to reach twice its initial size:
$$
N(T_d) = 2N_0
$$

1. Substitute $t = T_d$ into the exponential model:
   $$
   N_0 e^{k T_d} = 2N_0
   $$

2. Since $N_0 > 0$, divide both sides by $N_0$:
   $$
   e^{k T_d} = 2
   $$

3. Take the natural logarithm of both sides:
   $$
   \ln\left(e^{k T_d}\right) = \ln(2)
   $$

4. Use the inverse property $\ln(e^u) = u$:
   $$
   k T_d = \ln 2
   $$

5. Solve for $T_d$:
   $$
   T_d = \frac{\ln 2}{k}
   $$

Using $\ln 2 \approx 0.693147$:
$$
\mathbf{T_d = \frac{\ln 2}{k} \approx \frac{0.69315}{k}}
$$

*(In economics and demography, this is the origin of the famous "Rule of 70": doubling time $\approx 70 / (\text{percentage growth rate})$).*

---

### Step 3: Why Doubling Time Does Not Depend on $N_0$

1. **Algebraic Cancellation:**
   In Step 2, $N_0$ appears as a multiplicative scaling factor on both sides of the equation $N_0 e^{k T_d} = 2N_0$. Dividing through by $N_0$ eliminates it entirely, leaving the equation $e^{k T_d} = 2$. The parameter $N_0$ plays no role in determining $T_d$.

2. **Per-Capita Mechanism:**
   The equation $N'(t) = k N(t)$ means:
   $$
   \frac{N'(t)}{N(t)} = k \quad \text{per-capita growth rate}
   $$
   Each individual organism reproduces at the same statistical rate $k$, irrespective of whether the colony consists of 10 cells or 10 billion cells. Because the reproductive capability scales in exact 1:1 proportion to the population, the time required for any group to double its number is universally the same.

3. **Time-Translation Invariance (Universal Doubling):**
   The property is not restricted to doubling from $t = 0$. Let $t_1$ be any arbitrary time when the population is $P = N(t_1)$.
   Then at time $t_1 + T_d$:
   $$
   N(t_1 + T_d) = N_0 e^{k(t_1 + T_d)} = N_0 e^{k t_1} \cdot e^{k T_d} = N(t_1) \cdot e^{\ln 2} = P \cdot 2 = 2P
   $$
   The population doubles across **any** window of duration $T_d = \frac{\ln 2}{k}$.

---

## 4. Verification and Consistency Checks

1. **Concrete Numerical Scenario Check:**
   Suppose a bacterial culture has growth rate $k = 0.1\text{ h}^{-1}$:
   - Doubling time:
     $$
     T_d = \frac{\ln 2}{0.1} \approx \frac{0.693147}{0.1} \approx 6.9315\text{ hours}
     $$
   - Case A ($N_0 = 100$):
     $$
     N(6.9315) = 100 e^{0.1 \times 6.9315} = 100 e^{0.69315} = 100 \times 2 = 200 \quad (\checkmark)
     $$
   - Case B ($N_0 = 1\,000\,000$):
     $$
     N(6.9315) = 1\,000\,000 e^{0.69315} = 1\,000\,000 \times 2 = 2\,000\,000 \quad (\checkmark)
     $$
   Both populations double in exactly $6.9315$ hours despite a 10,000-fold difference in initial magnitude.

2. **Dimensional Analysis Check:**
   - Growth constant $k$ has dimension of inverse time: $[k] = \text{time}^{-1}$ (e.g. $\text{s}^{-1}$ or $\text{h}^{-1}$).
   - $\ln 2$ is a dimensionless mathematical constant.
   - Therefore, the dimension of $T_d = \frac{\ln 2}{k}$ is:
     $$
     [T_d] = \frac{1}{\text{time}^{-1}} = \text{time}
     $$
   The units are dimensionally consistent.
