# Solution to Exercise 1: Recognizing Curves from Canonical Form

## 1. Problem Statement

Identify and characterize each of the following second-degree curves given in canonical form:

1. $x^2 + y^2 = 9$
2. $\frac{x^2}{16} + \frac{y^2}{9} = 1$
3. $y^2 = 8x$
4. $\frac{x^2}{9} - \frac{y^2}{4} = 1$

For each curve:
- State its geometric classification (type of conic section).
- Identify its principal geometric features (center/vertex, semiaxes/radius, axis of symmetry, intercepts).
- Explain which specific algebraic features of the equation reveal its type.

---

## 2. Theoretical Background and Concepts

1. **Classification of Plane Conic Sections:**
   In Cartesian coordinates, second-degree polynomial equations in two variables take the canonical forms:
   - **Circle:** $x^2 + y^2 = R^2$ (both quadratic variables present, identical positive coefficients).
   - **Ellipse:** $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$ (both quadratic variables present with positive but unequal coefficients).
   - **Parabola:** $y^2 = 2px$ or $x^2 = 2py$ (exactly one quadratic variable and one linear variable).
   - **Hyperbola:** $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$ or $\frac{y^2}{a^2} - \frac{x^2}{b^2} = 1$ (both quadratic variables present with opposite signs).

2. **Symmetries:**
   - Replacing $x$ with $-x$ without altering the equation indicates reflectional symmetry across the $y$-axis.
   - Replacing $y$ with $-y$ without altering the equation indicates reflectional symmetry across the $x$-axis.
   - Curves with both symmetries possess point symmetry across the origin $(0, 0)$.

---

## 3. Detailed Step-by-Step Solution

### Curve 1: $x^2 + y^2 = 9$

1. **Classification:**
   This is a **circle** centered at the origin.
2. **Key Geometric Features:**
   - **Center:** $S = (0, 0)$
   - **Radius:** $R = \sqrt{9} = 3$
   - **Intercepts:**
     - $x$-intercepts ($y = 0$): $x = \pm 3 \implies (-3, 0)$ and $(3, 0)$
     - $y$-intercepts ($x = 0$): $y = \pm 3 \implies (0, -3)$ and $(0, 3)$
   - **Symmetry:** Complete circular symmetry about the origin.
3. **Algebraic Identification:**
   Both $x^2$ and $y^2$ appear with **identical positive coefficients** ($+1$), and their sum equals a positive constant ($R^2 = 9$).

---

### Curve 2: $\frac{x^2}{16} + \frac{y^2}{9} = 1$

1. **Classification:**
   This is an **ellipse** with a horizontal major axis.
2. **Key Geometric Features:**
   - **Center:** $S = (0, 0)$
   - **Semiaxis Lengths:**
     - Major semiaxis along the $x$-axis: $a = \sqrt{16} = 4$
     - Minor semiaxis along the $y$-axis: $b = \sqrt{9} = 3$
   - **Intercepts:**
     - $x$-intercepts ($y = 0$): $(\pm 4, 0)$
     - $y$-intercepts ($x = 0$): $(0, \pm 3)$
   - **Linear Eccentricity and Foci:**
     $$
     c = \sqrt{a^2 - b^2} = \sqrt{16 - 9} = \sqrt{7} \approx 2.646 \implies F_{1,2} = (\pm \sqrt{7}, 0)
     $$
3. **Algebraic Identification:**
   Both variables are squared, their coefficients are **both positive but unequal** ($\frac{1}{16} \ne \frac{1}{9}$), and they sum to $+1$. Because the denominator under $x^2$ is larger ($16 > 9$), the ellipse is horizontally elongated.

---

### Curve 3: $y^2 = 8x$

1. **Classification:**
   This is a **parabola** opening to the right along the positive $x$-axis.
2. **Key Geometric Features:**
   - **Vertex:** $V = (0, 0)$
   - **Axis of Symmetry:** The line $y = 0$ ($x$-axis).
   - **Opening Direction:** Positive $x$-direction ($x \ge 0$), because $x = \frac{y^2}{8} \ge 0$.
   - **Focal Parameter and Focus:**
     Canonical form is $y^2 = 2px \implies 2p = 8 \implies p = 4$.
     - Focus: $F = \left(\frac{p}{2}, 0\right) = (2, 0)$
     - Directrix line: $x = -\frac{p}{2} = -2$
   - **Characteristic Points:**
     At $x = 2$: $y^2 = 16 \implies y = \pm 4$, yielding points $(2, 4)$ and $(2, -4)$ (the ends of the latus rectum).
3. **Algebraic Identification:**
   **Exactly one variable is squared ($y^2$)** while the other appears to the **first power ($x$)**.

---

### Curve 4: $\frac{x^2}{9} - \frac{y^2}{4} = 1$

1. **Classification:**
   This is a **hyperbola** opening horizontally.
2. **Key Geometric Features:**
   - **Center:** $S = (0, 0)$
   - **Semiaxis Lengths:**
     - Real (transverse) semiaxis: $a = \sqrt{9} = 3$
     - Imaginary (conjugate) semiaxis: $b = \sqrt{4} = 2$
   - **Vertices:** $(\pm 3, 0)$
   - **$y$-Intercepts:** None, because setting $x = 0$ gives $-\frac{y^2}{4} = 1 \implies y^2 = -4$ (no real solutions).
   - **Asymptotes:**
     Obtained by replacing $1$ with $0$:
     $$
     \frac{x^2}{9} - \frac{y^2}{4} = 0 \implies y = \pm \frac{b}{a} x = \pm \frac{2}{3}x
     $$
   - **Foci:**
     $$
     c = \sqrt{a^2 + b^2} = \sqrt{9 + 4} = \sqrt{13} \approx 3.606 \implies F_{1,2} = (\pm \sqrt{13}, 0)
     $$
3. **Algebraic Identification:**
   Both variables are squared, but they have **opposite algebraic signs** ($+$ on $x^2$, $-$ on $y^2$). The positive sign on $x^2$ indicates that the transverse axis lies along the $x$-axis.

---

### Step 5: Required Geometric Sketches of the Four Curves

#### 1. Circle: $x^2 + y^2 = 9$ ($R = 3$)
```
                 y
                 ^
                 | (0, 3)
             .---+---.
           /     |     \
          |      |      |
  --------+------+------+--------> x
   (-3, 0)|    (0,0)    | (3, 0)
          |      |      |
           \     |     /
             '---+---'
                 | (0, -3)
                 |
```
*Labels:* Center $(0, 0)$, Radius $R = 3$, Intercepts at $(\pm 3, 0)$ and $(0, \pm 3)$.

#### 2. Ellipse: $\frac{x^2}{16} + \frac{y^2}{9} = 1$ ($a = 4, b = 3$)
```
                   y
                   ^
                   | (0, 3) [Co-vertex]
              .----+----.
           .       |       .
         /         |         \
  ------+----------+----------+------> x
 (-4, 0)|        (0,0)        | (4, 0) [Vertex]
         \         |         /
           .       |       .
              '----+----'
                   | (0, -3) [Co-vertex]
                   |
```
*Labels:* Center $(0, 0)$, Major semiaxis $a = 4$ along $x$-axis, Minor semiaxis $b = 3$ along $y$-axis, Vertices $(\pm 4, 0)$, Co-vertices $(0, \pm 3)$.

#### 3. Parabola: $y^2 = 8x$ (Opens Right, $p = 4$)
```
           directrix         y
             x = -2          ^
               :             |
               :             |           * (2, 4)
               :             |         /
               :             |       /
               :             |     /
   ------------:-------------+----+------*------> x
               :             |V(0,0)   F(2,0)
               :             |     \
               :             |       \
               :             |         \
               :             |           * (2, -4)
               :             |
```
*Labels:* Vertex $V(0, 0)$ at the coordinate axes intersection $(0, 0)$; axis of symmetry $y = 0$; opens right ($x \ge 0$); focus $F(2, 0)$ aligned vertically below $(2, 4)$ and above $(2, -4)$; directrix $x = -2$ positioned to the left of the vertex.

#### 4. Hyperbola: $\frac{x^2}{9} - \frac{y^2}{4} = 1$ ($a = 3, b = 2$, Asymptotes $y = \pm \frac{2}{3}x$)
```
              y
       \      ^      /  Asymptote y = 2x/3
         \    |    /
       .   \  |  /   .
     /       \|/       \
  --+---------+---------+--> x
   /(-3,0)  (0,0)   (3,0)\
     \       /|\       /
       '   /  |  \   '
         /    |    \
       /      |      \  Asymptote y = -2x/3
```
*Labels:* Center $(0, 0)$, Vertices $(\pm 3, 0)$, Semiaxes $a = 3, b = 2$, Asymptotes $y = \pm \frac{2}{3}x$, Branches opening horizontally left and right.

---

## 4. Verification and Consistency Checks

1. **Comparative Overview Table:**

| Curve Equation | Geometric Classification | Center / Vertex | Orientation / Direction | Semiaxes / Scale |
| :--- | :--- | :--- | :--- | :--- |
| $x^2 + y^2 = 9$ | **Circle** | Center $(0, 0)$ | Isotropic | Radius $R = 3$ |
| $\frac{x^2}{16} + \frac{y^2}{9} = 1$ | **Ellipse** | Center $(0, 0)$ | Horizontal elongation | $a = 4, b = 3$ |
| $y^2 = 8x$ | **Parabola** | Vertex $(0, 0)$ | Opens right ($+x$) | Parameter $p = 4$, Focus $(2, 0)$ |
| $\frac{x^2}{9} - \frac{y^2}{4} = 1$ | **Hyperbola** | Center $(0, 0)$ | Horizontal branches | $a = 3, b = 2$, Asymptotes $y = \pm \frac{2}{3}x$ |

2. **Parabola Focus-Directrix Equidistance Check:**
   For point $P(2, 4)$ on $y^2 = 8x$:
   - Distance to focus $F(2, 0)$: $d(P, F) = \sqrt{(2 - 2)^2 + (4 - 0)^2} = 4$.
   - Distance to directrix $x = -2$: $d(P, \text{dir}) = |2 - (-2)| = 4$.
   $d(P, F) = d(P, \text{dir}) = 4 \quad (\checkmark)$.
