# Solution to Exercise 5: Hyperbola and Asymptotes

## 1. Problem Statement

Given the canonical equation of the hyperbola in $\mathbb{R}^2$:
$$
\frac{x^2}{16} - \frac{y^2}{9} = 1
$$

1. Find the intercepts with the $x$-axis (the vertices) and check whether there are any intercepts with the $y$-axis.
2. Determine the equations of the asymptotes.
3. Explain mathematically why the asymptotes accurately describe the asymptotic behavior of the hyperbola far from the center (as $|x| \to \infty$).

---

## 2. Theoretical Background and Concepts

1. **Canonical Form of a Horizontally Opening Hyperbola:**
   The standard canonical equation is:
   $$
   \frac{x^2}{a^2} - \frac{y^2}{b^2} = 1
   $$
   where:
   - $a > 0$ is the real (transverse) semiaxis.
   - $b > 0$ is the imaginary (conjugate) semiaxis.
   - Vertices are at $(\pm a, 0)$.

2. **Asymptotes of a Hyperbola:**
   The asymptotes are straight lines passing through the center $(0, 0)$ that the hyperbola approaches arbitrarily closely as the coordinates grow without bound. Their equations are obtained by setting the right-hand side of the canonical equation to $0$:
   $$
   \frac{x^2}{a^2} - \frac{y^2}{b^2} = 0 \iff y = \pm \frac{b}{a} x
   $$

3. **Asymptotic Convergence:**
   Solving for $y$ explicitly from the hyperbola equation:
   $$
   y(x) = \pm \frac{b}{a} \sqrt{x^2 - a^2} = \pm \frac{b}{a} |x| \sqrt{1 - \frac{a^2}{x^2}}
   $$
   As $|x| \to \infty$, the term $\frac{a^2}{x^2} \to 0$, causing $\sqrt{1 - \frac{a^2}{x^2}} \to 1$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Find Axis Intercepts

1. **$x$-Intercepts (let $y = 0$):**
   $$
   \frac{x^2}{16} - \frac{0^2}{9} = 1 \implies \frac{x^2}{16} = 1 \implies x^2 = 16 \implies x = \pm 4
   $$
   The hyperbola intersects the $x$-axis at the vertices:
   $$
   A_1 = (-4, 0), \qquad A_2 = (4, 0)
   $$

2. **$y$-Intercepts (let $x = 0$):**
   $$
   \frac{0^2}{16} - \frac{y^2}{9} = 1 \implies -\frac{y^2}{9} = 1 \implies y^2 = -9
   $$
   Since $y^2 \ge 0$ for all real numbers $y$, $y^2 = -9$ has **no real solutions**.
   Therefore, the hyperbola **does not intersect the $y$-axis**.

---

### Step 2: Determine the Equations of the Asymptotes

Comparing $\frac{x^2}{16} - \frac{y^2}{9} = 1$ with the standard form:
- $a^2 = 16 \implies a = 4$
- $b^2 = 9 \implies b = 3$

The asymptotes are the lines obtained by replacing $1$ with $0$:
$$
\frac{x^2}{16} - \frac{y^2}{9} = 0 \iff \left(\frac{x}{4} - \frac{y}{3}\right)\left(\frac{x}{4} + \frac{y}{3}\right) = 0
$$
Setting each linear factor to zero yields the pair of lines:
$$
\frac{y}{3} = \pm \frac{x}{4} \implies y = \pm \frac{3}{4} x
$$

In explicit form:
$$
L_1: y = \frac{3}{4}x = 0.75x, \qquad L_2: y = -\frac{3}{4}x = -0.75x
$$

---

### Step 3: Mathematical Explanation of Asymptotic Behavior

To see why the hyperbola approaches the asymptotes far from the center, isolate $y$ for $x > 4$:
$$
\frac{y^2}{9} = \frac{x^2}{16} - 1 = \frac{x^2 - 16}{16} \implies y_{\text{hyp}}(x) = \frac{3}{4} \sqrt{x^2 - 16}
$$
Factor out $x$ from the square root:
$$
y_{\text{hyp}}(x) = \frac{3}{4} x \sqrt{1 - \frac{16}{x^2}}
$$

Now calculate the vertical distance $\Delta y$ between the hyperbola branch and the asymptote line $y_{\text{asymp}} = \frac{3}{4}x$:
$$
\Delta y(x) = y_{\text{asymp}}(x) - y_{\text{hyp}}(x) = \frac{3}{4} x \left(1 - \sqrt{1 - \frac{16}{x^2}}\right)
$$
Multiply and divide by the conjugate expression $\left(1 + \sqrt{1 - \frac{16}{x^2}}\right)$:
$$
\Delta y(x) = \frac{3}{4} x \frac{1 - \left(1 - \frac{16}{x^2}\right)}{1 + \sqrt{1 - \frac{16}{x^2}}} = \frac{3}{4} x \frac{\frac{16}{x^2}}{1 + \sqrt{1 - \frac{16}{x^2}}} = \frac{12}{x \left(1 + \sqrt{1 - \frac{16}{x^2}}\right)}
$$

Take the limit as $x \to \infty$:
$$
\lim_{x \to \infty} \Delta y(x) = \lim_{x \to \infty} \frac{12}{x (1 + 1)} = \lim_{x \to \infty} \frac{6}{x} = 0
$$

**Conclusion:**
As the distance from the center increases ($|x| \to \infty$), the constant term $1$ in $\frac{x^2}{16} - \frac{y^2}{9} = 1$ becomes negligibly small compared to the quadratic terms (ratio $\frac{16}{x^2} \to 0$). The hyperbola and the asymptotes become indistinguishable at large scales.

---

### Step 4: Required Geometric Sketch of the Hyperbola

Below is the sketch of the horizontal hyperbola $\frac{x^2}{16} - \frac{y^2}{9} = 1$ with its vertices and asymptotes:

```
                  y
           \      ^      /  Asymptote y = 3x/4
             \    |    /
          .    \  |  /    .
        /        \|/        \
  -----+----------+----------+-----> x
      /(-4, 0)  Center     (4, 0)\
     / [Vertex]  (0,0)   [Vertex] \
        \        /|\        /
          '    /  |  \    '
             /    |    \
           /      |      \  Asymptote y = -3x/4
                  |
```

*Geometric Features Labeled on the Sketch:*
- **Center:** $(0, 0)$ at the intersection of the coordinate axes and asymptotes.
- **Transverse Axis:** Along the $x$-axis; Vertices at $(-4, 0)$ and $(4, 0)$ with real semiaxis $a = 4$.
- **Asymptote Lines:** $y = \frac{3}{4}x$ and $y = -\frac{3}{4}x$ passing through the origin.
- **Branches:** Two disjoint branches opening horizontally to the left ($x \le -4$) and to the right ($x \ge 4$), asymptotically converging towards the lines $y = \pm \frac{3}{4}x$ as $|x| \to \infty$.

---

## 4. Verification and Consistency Checks

1. **Numerical Value Verification Far from Center:**
   Test at $x = 100$:
   - Asymptote value: $y_{\text{asymp}} = \frac{3}{4}(100) = 75.0000$
   - Hyperbola value:
     $$
     y_{\text{hyp}} = \frac{3}{4}\sqrt{100^2 - 16} = \frac{3}{4}\sqrt{10000 - 16} = \frac{3}{4}\sqrt{9984} \approx \frac{3}{4}(99.91997) \approx 74.93998
     $$
   - Vertical difference: $\Delta y = 75.0000 - 74.93998 = 0.06002 \approx \frac{6}{100} = 0.06$
   The calculated distance agrees with the theoretical error formula $\frac{6}{x}$.

2. **Foci Calculation:**
   $$
   c = \sqrt{a^2 + b^2} = \sqrt{16 + 9} = \sqrt{25} = 5
   $$
   The foci are at $F_1(-5, 0)$ and $F_2(5, 0)$.
   Check focal distance difference for vertex $A_2(4, 0)$:
   - Distance to $F_1(-5, 0)$: $d_1 = |4 - (-5)| = 9$.
   - Distance to $F_2(5, 0)$: $d_2 = |4 - 5| = 1$.
   $$
   |d_1 - d_2| = |9 - 1| = 8 = 2a \quad (\checkmark)
   $$
   The hyperbola focal definition is satisfied.
