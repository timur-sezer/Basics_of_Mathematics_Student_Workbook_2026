# Solution to Problem 12: Complete Model and Computer Verification

## 1. Problem Statement

A museum plans to construct a rectangular exhibition room adjacent to an existing straight wall. The side along the existing wall requires no new construction. The remaining three walls are to be built according to two distinct architectural and structural standards:
- The two side walls perpendicular to the existing wall cost $300\ \mathrm{PLN/m}$ each.
- The front wall parallel to the existing wall costs $500\ \mathrm{PLN/m}$.
- The total construction budget allocated for these three walls is $30\,000\ \mathrm{PLN}$.

The objective is to design the room so as to maximize its enclosed floor area.

Prepare a comprehensive analysis containing:
1. Definition of variables and units.
2. Formulation of the mathematical model.
3. Determination of the domain resulting from physical and financial constraints.
4. Computation of the first derivative of the objective function.
5. Determination of the critical point and formal verification of the optimum.
6. Interpretation of the geometric and economic results (including budget distribution).
7. Graphical representation of the objective function.
8. Numerical sensitivity verification for dimensions in the neighborhood of the optimum.
9. Methodological distinction between the problem modeling phase and the computational execution phase.

---

## 2. Theoretical Background and Concepts

### 2.1 Single-Variable Constrained Optimization
An optimization problem with two variables $x, y$ subject to an equality constraint $g(x, y) = C$ can be reduced to a single-variable unconstrained problem if one variable can be explicitly expressed in terms of the other:
$$
y = h(x) \implies f(x, y) = f(x, h(x)) = F(x).
$$

### 2.2 Domain Analysis and Extreme Value Theorem
For an objective function $F(x)$ defined on a bounded interval, the admissible domain $\mathcal{D}_F$ is dictated by the physical feasibility of the dimensions:
$$
x > 0 \quad \text{and} \quad y = h(x) > 0.
$$
If $F(x)$ is continuous on the compact closure $\overline{\mathcal{D}_F} = [a, b]$ and vanishes at the boundary ($F(a) = F(b) = 0$) while remaining strictly positive on $(a, b)$, then by the Weierstrass Extreme Value Theorem, $F$ must achieve a global maximum at an interior critical point where $F'(x) = 0$.

### 2.3 Second Derivative Test for Concavity
If $F(x)$ is twice continuously differentiable on an open interval $\mathcal{D}_F$:
- A critical point $x^*$ satisfies $F'(x^*) = 0$.
- If $F''(x) < 0$ for all $x \in \mathcal{D}_F$, the function $F$ is strictly concave on $\mathcal{D}_F$, guaranteeing that $x^*$ is the unique global maximum.

### 2.4 Economic Equipartition Principle (Lagrange Multipliers)
When maximizing a bilinear objective $A(x, y) = x \cdot y$ subject to a linear budget constraint $c_x x + c_y y = B$, the method of Lagrange multipliers states:
$$
\nabla A = \lambda \nabla g \implies (y, x) = \lambda (c_x, c_y) \implies \frac{y}{c_x} = \frac{x}{c_y} \implies c_x x = c_y y.
$$
Since $c_x x + c_y y = B$, it follows that:
$$
c_x x = \frac{B}{2} \quad \text{and} \quad c_y y = \frac{B}{2}.
$$
That is, the optimal economic allocation splits the total budget equally between the two orthogonal cost components.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Definition of Variables and Units
Let:
- $x$: the length of the new wall built parallel to the existing museum wall, measured in meters ($\mathrm{m}$).
- $y$: the length of each of the two new walls built perpendicular to the existing wall, measured in meters ($\mathrm{m}$).
- $A$: the enclosed floor area of the rectangular exhibition room, measured in square meters ($\mathrm{m}^2$).
- $C$: the total construction cost, measured in Polish Zloty ($\mathrm{PLN}$).

```
          Existing Museum Wall (Cost = 0 PLN)
   =================================================
   |                                               |
   |                                               |
y  |                   Room Area                   |  y
(300 PLN/m)            A = x * y               (300 PLN/m)
   |                                               |
   |                                               |
   -------------------------------------------------
                           x
               (Parallel: 500 PLN/m)
```

### Step 2: Formulation of the Mathematical Model
The total cost of constructing the three walls consists of:
- Parallel wall cost: $500 \cdot x\ \mathrm{PLN}$.
- Two perpendicular walls cost: $2 \cdot (300 \cdot y) = 600 \cdot y\ \mathrm{PLN}$.

Given the fixed budget of $30\,000\ \mathrm{PLN}$, the linear constraint is:
$$
500x + 600y = 30\,000.
$$

We isolate $y$ as a function of $x$:
$$
600y = 30\,000 - 500x \implies y = \frac{30\,000}{600} - \frac{500}{600}x = 50 - \frac{5}{6}x.
$$

The objective function to maximize is the area $A(x, y) = x \cdot y$. Substituting $y(x)$:
$$
A(x) = x\left(50 - \frac{5}{6}x\right) = 50x - \frac{5}{6}x^2.
$$

### Step 3: Determination of the Domain
Both geometric dimensions must be strictly positive:
1. $x > 0$.
2. $y > 0 \implies 50 - \frac{5}{6}x > 0 \implies \frac{5}{6}x < 50 \implies x < \frac{50 \cdot 6}{5} = 60$.

Therefore, the physically feasible open domain is:
$$
\mathcal{D}_A = (0, 60)\quad [\mathrm{m}].
$$
On the boundary $x \to 0^+$ or $x \to 60^-$, the area degenerates to $0$.

### Step 4: First Derivative and Critical Point
Differentiating $A(x)$ with respect to $x$:
$$
A'(x) = \frac{d}{dx}\left(50x - \frac{5}{6}x^2\right) = 50 - 2 \cdot \frac{5}{6}x = 50 - \frac{5}{3}x.
$$

Setting the first derivative to zero to find stationary points:
$$
50 - \frac{5}{3}x = 0 \implies \frac{5}{3}x = 50 \implies x^* = 50 \cdot \frac{3}{5} = 30\ \mathrm{m}.
$$

Since $30 \in (0, 60)$, $x^* = 30\ \mathrm{m}$ is a valid interior critical point.

### Step 5: Verification of the Optimum
We evaluate the second derivative of $A(x)$:
$$
A''(x) = \frac{d}{dx}\left(50 - \frac{5}{3}x\right) = -\frac{5}{3}.
$$

Since $A''(x) = -\frac{5}{3} < 0$ everywhere on $(0, 60)$:
- The function $A(x)$ is strictly concave on the entire interval $(0, 60)$.
- By the second derivative test, $x^* = 30\ \mathrm{m}$ corresponds to a unique, strict global maximum.

### Step 6: Calculation of Optimal Dimensions and Maximum Area
Substituting $x^* = 30\ \mathrm{m}$ into the expression for $y$:
$$
y^* = 50 - \frac{5}{6}(30) = 50 - 25 = 25\ \mathrm{m}.
$$

The maximum floor area is:
$$
A_{\max} = x^* \cdot y^* = 30\ \mathrm{m} \times 25\ \mathrm{m} = 750\ \mathrm{m}^2.
$$

### Step 7: Economic Budget Distribution
Let us verify the financial expenditures at the optimum:
- Expenditure on the front parallel wall:
  $$
  C_{\parallel} = 500\ \mathrm{PLN/m} \times 30\ \mathrm{m} = 15\,000\ \mathrm{PLN}.
  $$
- Expenditure on the two perpendicular side walls:
  $$
  C_{\perp} = 600\ \mathrm{PLN/m} \times 25\ \mathrm{m} = 15\,000\ \mathrm{PLN}.
  $$
- Total cost:
  $$
  C_{\text{total}} = 15\,000 + 15\,000 = 30\,000\ \mathrm{PLN}.
  $$

Exactly $50\%$ of the budget is spent on the parallel wall, and exactly $50\%$ is spent on the two perpendicular walls combined, confirming the equipartition principle of economic optimization.

### Step 8: Graphical Representation of $A(x)$
The objective function $A(x) = -\frac{5}{6}(x - 30)^2 + 750$ is a downward-opening parabola with its vertex at $(30, 750)$:

```
   Area A(x) [m^2]
     ^
 750 |                       * (30, 750) [MAXIMUM]
     |                   . *   * .
 600 |                .             .
     |              .                 .
 450 |            .                     .
     |          .                         .
 300 |        .                             .
     |       .                               .
 150 |     .                                   .
     |   .                                       .
   0 +---+---+---+---+---+---+---+---+---+---+---+---+---> x [m]
     0   5  10  15  20  25  30  35  40  45  50  55  60
```

### Step 9: Methodological Distinction: Modeling vs. Calculation
The prompt requests an explicit delineation between which steps constituted **modeling** and which constituted **execution of calculation**:

1. **Modeling Phase (Translating Reality into Formal Mathematics):**
   - Identifying the independent degrees of freedom and assigning geometric variables ($x, y$ in meters).
   - Recognizing that the existing wall incurs zero material cost.
   - Formulating the cost constraint with disparate unit rates ($500x + 600y = 30\,000$).
   - Formulating the physical objective function ($A = xy$).
   - Deducing the physical boundary conditions requiring non-degenerate lengths, yielding $\mathcal{D}_A = (0, 60)$.

2. **Computational Execution Phase (Mathematical Machinery):**
   - Algebraically eliminating $y$ to obtain the univariate quadratic $A(x) = 50x - \frac{5}{6}x^2$.
   - Differentiating $A(x)$ using standard calculus power and sum rules.
   - Solving the algebraic equation $A'(x) = 0$.
   - Evaluating $A''(x) = -5/3 < 0$ to verify global concavity.
   - Performing arithmetic substitutions to obtain $y^* = 25\ \mathrm{m}$ and $A_{\max} = 750\ \mathrm{m}^2$.

---

## 4. Verification and Consistency Checks

### 4.1 Numerical Neighborhood Verification
We calculate the area for dimensions flanking the critical point $x^* = 30\ \mathrm{m}$ to confirm maximality:

| Parallel Side $x$ ($\mathrm{m}$) | Perpendicular Side $y = 50 - \frac{5}{6}x$ ($\mathrm{m}$) | Total Cost ($\mathrm{PLN}$) | Area $A = x \cdot y$ ($\mathrm{m}^2$) | Area Difference $\Delta A = A - A_{\max}$ |
| :---: | :---: | :---: | :---: | :---: |
| $18$ | $35.00$ | $500(18) + 600(35) = 30\,000$ | $630.00$ | $-120.00$ |
| $24$ | $30.00$ | $500(24) + 600(30) = 30\,000$ | $720.00$ | $-30.00$ |
| $28$ | $26.67$ | $500(28) + 600(26.67) = 30\,000$ | $746.67$ | $-3.33$ |
| **$30$** | **$25.00$** | **$500(30) + 600(25) = 30\,000$** | **$750.00$** | **$0.00$ (MAXIMUM)** |
| $32$ | $23.33$ | $500(32) + 600(23.33) = 30\,000$ | $746.67$ | $-3.33$ |
| $36$ | $20.00$ | $500(36) + 600(20) = 30\,000$ | $720.00$ | $-30.00$ |
| $42$ | $15.00$ | $500(42) + 600(15) = 30\,000$ | $630.00$ | $-120.00$ |

The table confirms strict symmetry around $x = 30$ and verifies that any deviation in either direction reduces the enclosed area.

### 4.2 Independent Verification via AM-GM Inequality
We express the area in terms of the two cost components $u = 500x$ and $v = 600y$:
$$
u + v = 30\,000, \quad u, v > 0.
$$
The area is:
$$
A = x y = \left(\frac{u}{500}\right)\left(\frac{v}{600}\right) = \frac{u v}{300\,000}.
$$
By the Arithmetic Mean - Geometric Mean (AM-GM) inequality:
$$
\sqrt{u v} \le \frac{u + v}{2} = \frac{30\,000}{2} = 15\,000.
$$
Squaring both sides:
$$
u v \le (15\,000)^2 = 225\,000\,000.
$$
Equality holds if and only if $u = v = 15\,000\ \mathrm{PLN}$. Thus:
$$
A_{\max} = \frac{225\,000\,000}{300\,000} = 750\ \mathrm{m}^2,
$$
achieved when:
$$
500x = 15\,000 \implies x^* = 30\ \mathrm{m}, \qquad 600y = 15\,000 \implies y^* = 25\ \mathrm{m}.
$$
The calculus and algebraic optimization solutions are in total concordance.
