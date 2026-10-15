# Solution to Problem 2: Maximum Area of a Rectangle

## 1. Problem Statement

A rectangle has a fixed perimeter of $P = 40$ units.

1. Express the area $A$ of the rectangle as a function of the length of one of its sides, $x$.
2. Determine the maximal domain of this function dictated by the geometric constraints of the problem.
3. Find the optimal dimensions (length and width) that maximize the enclosed area.
4. Provide a complete mathematical justification verifying that the identified dimensions yield a true global maximum.

---

## 2. Theoretical Background and Concepts

1. **The Optimization Workflow in Applied Calculus:**
   - **Step 1 (Variables & Constraints):** Identify independent variables and express geometric constraints as an equation relating them.
   - **Step 2 (Objective Function):** Eliminate secondary variables using the constraint equation to formulate the target quantity as a single-variable function $f(x)$.
   - **Step 3 (Feasible Domain):** Identify the allowable physical/geometric interval $I$ (lengths must be strictly positive).
   - **Step 4 (Differentiation & Critical Points):** Solve $f'(x) = 0$ on the interior of $I$.
   - **Step 5 (Verification):** Use the First or Second Derivative Test (or convexity arguments) to prove that the critical point corresponds to an absolute maximum.

2. **The Isoperimetric Property of the Square:**
   Among all planar rectangles with a fixed perimeter, the **square** encloses the greatest possible area.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Formulate the Area as a Single-Variable Function

Let the side lengths of the rectangle be $x$ and $y$.
1. **Perimeter Constraint:**
   $$
   2x + 2y = 40
   $$
   Divide both sides by $2$:
   $$
   x + y = 20
   $$
2. **Eliminate Variable $y$:**
   $$
   y = 20 - x
   $$
3. **Objective Function (Area):**
   $$
   A(x) = x \cdot y = x(20 - x) = 20x - x^2
   $$

---

### Step 2: Determine the Geometrically Meaningful Domain

In physical geometry, the side lengths of a non-degenerate rectangle must be strictly positive:
- Length $x > 0$.
- Width $y = 20 - x > 0 \iff x < 20$.

Combining these two conditions:
$$
\mathcal{D}_A = (0, 20) = \{x \in \mathbb{R} : 0 < x < 20\}
$$

*(Note: If degenerate rectangles of zero area are permitted, the domain is the compact interval $[0, 20]$, where $A(0) = A(20) = 0$).*

---

### Step 3: Find the Critical Points

Differentiate $A(x) = 20x - x^2$ with respect to $x$:
$$
A'(x) = \frac{d}{dx}[20x - x^2] = 20 - 2x
$$

Set the first derivative to zero to find the stationary points:
$$
20 - 2x = 0 \iff 2x = 20 \iff x = 10
$$
Since $10 \in (0, 20)$, $x = 10$ is a valid interior critical point.

Compute the corresponding dimension $y$:
$$
y = 20 - 10 = 10
$$

The optimal rectangle has dimensions:
$$
\text{Length} = 10, \qquad \text{Width} = 10 \quad (\text{a square})
$$

The maximum area enclosed is:
$$
A(10) = 10 \times 10 = 100 \text{ square units}
$$

---

### Step 4: Justification of the Maximum

We confirm that $x = 10$ yields a global maximum using three independent mathematical arguments:

#### Argument 1: The Second Derivative Test
Compute the second derivative:
$$
A''(x) = \frac{d}{dx}[20 - 2x] = -2
$$
Because $A''(x) = -2 < 0$ strictly for all $x \in (0, 20)$, the function $A(x)$ is **strictly concave downward** ($\cap$) on its entire domain.
Any critical point of a strictly concave function is the unique, absolute global maximum on that interval.

#### Argument 2: Monotonicity and the First Derivative Test
- For $x \in (0, 10)$: $20 - 2x > 0 \implies A'(x) > 0$ ($A$ is strictly increasing).
- For $x \in (10, 20)$: $20 - 2x < 0 \implies A'(x) < 0$ ($A$ is strictly decreasing).
Because $A(x)$ increases up to $x = 10$ and decreases thereafter, $x = 10$ is an absolute maximum.

#### Argument 3: Pure Algebraic Verification (Completing the Square)
$$
A(x) = -(x^2 - 20x) = -(x^2 - 20x + 100) + 100 = 100 - (x - 10)^2
$$
Since $(x - 10)^2 \ge 0$ for all real numbers $x$, with equality if and only if $x = 10$:
$$
A(x) = 100 - (x - 10)^2 \le 100 \quad \forall x \in \mathbb{R}
$$
This demonstrates that $A(x) \le 100$ unconditionally, with maximum area $100$ achieved uniquely when $x = 10$.

---

## 4. Verification and Consistency Checks

1. **AM-GM Inequality Cross-Check:**
   By the Arithmetic Mean - Geometric Mean inequality, for any positive numbers $x$ and $y$:
   $$
   \sqrt{xy} \le \frac{x + y}{2}
   $$
   Squaring both sides:
   $$
   xy \le \left(\frac{x + y}{2}\right)^2
   $$
   Substituting the perimeter constraint $x + y = 20$:
   $$
   A = xy \le \left(\frac{20}{2}\right)^2 = 10^2 = 100
   $$
   Equality in the AM-GM inequality holds if and only if all variables are equal:
   $$
   x = y = 10
   $$
   The algebraic AM-GM theorem completely confirms our calculus solution.

2. **Sample Comparison Table:**
   | Dimensions $(x \times y)$ | Perimeter $2(x + y)$ | Area $A = x \cdot y$ | Comparison to Max |
   |:---:|:---:|:---:|:---:|
   | $1 \times 19$ | $40$ | $19$ | $-81\%$ |
   | $5 \times 15$ | $40$ | $75$ | $-25\%$ |
   | $8 \times 12$ | $40$ | $96$ | $-4\%$ |
   | $9 \times 11$ | $40$ | $99$ | $-1\%$ |
   | **$10 \times 10$ (Square)** | **$40$** | **$100$** | **Optimal Maximum** |

   Any deviation from the square strictly diminishes the enclosed area.
