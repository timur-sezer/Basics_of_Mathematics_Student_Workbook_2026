# Solution to Problem 15: Integral Physics, Fluid Mechanics & Gravitational Work (Enrichment)

## 1. Problem Statement

### 1.1 Curriculum Structure Note
In the official course syllabus (`exercises/3_Calculus/05_applications_en.md`), module **05. Applications of Differential and Integral Calculus** serves as a synthetic capstone and officially concludes with **Problem 12** (*Complete Model and Computer Verification*).

To achieve 100% completion across all 15 template files in the repository and provide a complete reference for classical physics applications, this file presents: **Gravitational Work Required to Empty a Conical Reservoir via Riemann Slice Integration and Centroid Verification**.

---

### 1.2 Problem Formulation
An inverted right circular conical water reservoir has:
- A top rim radius of $R = 4\ \mathrm{m}$,
- A total vertical height of $H = 6\ \mathrm{m}$ (with the vertex pointing downwards at ground level).

The tank is initially filled with water to a depth of $h_0 = 4\ \mathrm{m}$ (measured upward from the vertex). The density of water is $\rho = 1\,000\ \mathrm{kg/m}^3$, and the acceleration due to gravity is taken as $g = 9.8\ \mathrm{m/s}^2$.

All the water in the tank must be pumped out over the top rim of the reservoir.

1. Establish a coordinate system along the vertical axis of symmetry and express the radius $r(y)$ of an arbitrary horizontal circular cross-section at height $y$.
2. Formulate the differential volume $dV$, mass $dm$, and gravitational force $dF$ of a thin horizontal water layer of thickness $dy$.
3. Determine the vertical lifting distance $D(y)$ required to elevate this water layer over the top rim.
4. Construct the definite Riemann integral representing the total mechanical work $W$.
5. Evaluate the integral to determine the exact work in Joules ($\mathrm{J}$) and kilojoules ($\mathrm{kJ}$).
6. Provide an independent verification using the fluid centroid (center of mass) principle.

---

## 2. Theoretical Background and Concepts

### 2.1 Gravitational Work as a Definite Integral
In classical mechanics, mechanical work done by a variable force along a displacement path is given by $W = \int F\,ds$. For a continuous body of fluid, the total gravitational work required to lift the mass against gravity is constructed as the limit of Riemann sums partitioning the fluid into infinitesimally thin horizontal slices:
$$
W = \int_{y_{\text{bottom}}}^{y_{\text{top}}} D(y) \, dF = \int_{y_{\text{bottom}}}^{y_{\text{top}}} D(y) \, \rho \, g \, A(y) \, dy,
$$
where:
- $A(y)$ is the horizontal cross-sectional area at height $y$,
- $D(y)$ is the vertical distance through which the slice at height $y$ must be lifted,
- $\rho g$ is the specific weight (weight density) of the fluid.

### 2.2 Similar Triangles in Conical Geometry
In an inverted circular cone of base radius $R$ and altitude $H$, the radius $r(y)$ of the horizontal cross-section at height $y \in [0, H]$ from the vertex satisfies the geometric proportionality:
$$
\frac{r(y)}{y} = \frac{R}{H} \implies r(y) = \frac{R}{H}y.
$$

### 2.3 Centroid Principle of Fluid Mechanics
The total work required to pump a homogeneous body of fluid of total mass $M$ to a discharge height $y_{\text{rim}}$ is identically equal to the work required to lift a point mass $M$ from the fluid's vertical center of mass $\bar{y}$ to the discharge elevation:
$$
W = M \cdot g \cdot (y_{\text{rim}} - \bar{y}),
$$
where the center of mass coordinate is defined by:
$$
\bar{y} = \frac{1}{V} \int_{y_{\text{bottom}}}^{y_{\text{top}}} y \, A(y) \, dy.
$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Geometric Setup and Coordinate Representation
We choose a vertical $y$-axis with:
- The origin $y = 0$ located at the bottom vertex of the inverted cone.
- The top rim of the tank located at $y = H = 6\ \mathrm{m}$.
- The water occupies the region from $y = 0$ to $y = h_0 = 4\ \mathrm{m}$.

```
                 y = 6 m  [Top Rim of Tank]
          ---------------------------------  R = 4 m
          \                               /
           \    Empty Region (h=4 to 6)  /
            \---------------------------/    y = 4 m  [Water Surface]
             \                         /
              \   Water Layer (dy)    /      y
               \   r(y) = (2/3)y     /
                \                   /
                 \                 /
                  \               /
                   \             /
                    \           /
                     \         /
                      \       /
                       \     /
                        \   /
                          v                  y = 0 m  [Vertex Origin]
```

By similar triangles, the radius of the circular cross-section at height $y$ is:
$$
r(y) = \frac{R}{H} y = \frac{4}{6} y = \frac{2}{3}y\quad [\mathrm{m}].
$$

The horizontal cross-sectional area of the slice is:
$$
A(y) = \pi [r(y)]^2 = \pi \left(\frac{2}{3}y\right)^2 = \frac{4\pi}{9}y^2\quad [\mathrm{m}^2].
$$

### Step 2: Differential Slice Properties
Consider a thin horizontal slice of water between elevations $y$ and $y + dy$:
- **Volume of the slice:**
  $$
  dV = A(y) \, dy = \frac{4\pi}{9}y^2 \, dy\quad [\mathrm{m}^3].
  $$
- **Mass of the slice:**
  $$
  dm = \rho \, dV = 1000 \cdot \frac{4\pi}{9}y^2 \, dy = \frac{4000\pi}{9}y^2 \, dy\quad [\mathrm{kg}].
  $$
- **Weight (downward gravitational force) of the slice:**
  $$
  dF = dm \cdot g = \rho g \frac{4\pi}{9} y^2 \, dy\quad [\mathrm{N}].
  $$

### Step 3: Vertical Lifting Distance
To pump the water slice out over the top rim located at $y = 6\ \mathrm{m}$, the slice must be lifted vertically by:
$$
D(y) = 6 - y\quad [\mathrm{m}].
$$

### Step 4: Formulation of the Total Work Integral
The differential work $dW$ needed to pump this single layer to the rim is:
$$
dW = D(y) \cdot dF = (6 - y) \cdot \left(\rho g \frac{4\pi}{9} y^2 \, dy\right) = \rho g \frac{4\pi}{9} (6y^2 - y^3) \, dy.
$$

Since water fills the reservoir from height $y = 0$ to $y = 4$, the total work is the definite integral:
$$
W = \int_0^4 dW = \rho g \frac{4\pi}{9} \int_0^4 (6y^2 - y^3) \, dy.
$$

### Step 5: Evaluation of the Definite Integral
We compute the antiderivative:
$$
\int (6y^2 - y^3) \, dy = 6 \cdot \frac{y^3}{3} - \frac{y^4}{4} = 2y^3 - \frac{y^4}{4}.
$$

Evaluating at the integration limits $0$ and $4$:
$$
\left[ 2y^3 - \frac{y^4}{4} \right]_0^4 = \left(2(4)^3 - \frac{4^4}{4}\right) - 0 = \left(2(64) - 64\right) = 128 - 64 = 64.
$$

Multiplying by the pre-integral constant:
$$
W = \rho g \frac{4\pi}{9} \cdot 64 = \frac{256\pi}{9} \rho g\quad [\mathrm{J}].
$$

### Step 6: Numerical Calculation
Substituting the physical constants $\rho = 1000\ \mathrm{kg/m}^3$ and $g = 9.8\ \mathrm{m/s}^2$:
$$
\rho g = 1000 \times 9.8 = 9\,800\ \mathrm{N/m}^3.
$$
Then:
$$
W = \frac{256 \pi}{9} \times 9\,800 = \frac{2\,508\,800 \pi}{9} \approx 278\,755.56 \pi\ \mathrm{J}.
$$

Using $\pi \approx 3.14159265$:
$$
W \approx 278\,755.56 \times 3.14159265 \approx 875\,736\ \mathrm{J} \approx 875.74\ \mathrm{kJ}.
$$

---

## 4. Verification and Consistency Checks

### 4.1 Independent Verification via Center of Mass Principle

#### Part A: Total Volume of Contained Water
The total volume $V$ of the conical water body (a cone of base radius $r(4) = \frac{2}{3}(4) = \frac{8}{3}\ \mathrm{m}$ and height $h_0 = 4\ \mathrm{m}$) is:
$$
V = \int_0^4 A(y) \, dy = \frac{4\pi}{9} \int_0^4 y^2 \, dy = \frac{4\pi}{9} \left[ \frac{y^3}{3} \right]_0^4 = \frac{4\pi}{9} \cdot \frac{64}{3} = \frac{256\pi}{27}\ \mathrm{m}^3.
$$
Using the standard geometric formula for a cone $V = \frac{1}{3}\pi r^2 h$:
$$
V_{\text{geom}} = \frac{1}{3} \pi \left(\frac{8}{3}\right)^2 (4) = \frac{1}{3}\pi \cdot \frac{64}{9} \cdot 4 = \frac{256\pi}{27}\ \mathrm{m}^3.
$$
The geometric and integral volumes match exactly.

#### Part B: Total Mass of Contained Water
$$
M = \rho V = 1000 \cdot \frac{256\pi}{27} = \frac{256\,000\pi}{27}\ \mathrm{kg}.
$$

#### Part C: Vertical Center of Mass $\bar{y}$
By definition:
$$
\bar{y} = \frac{1}{V} \int_0^4 y \, A(y) \, dy = \frac{1}{\frac{256\pi}{27}} \cdot \frac{4\pi}{9} \int_0^4 y^3 \, dy.
$$
Evaluating the integral:
$$
\int_0^4 y^3 \, dy = \left[ \frac{y^4}{4} \right]_0^4 = \frac{256}{4} = 64.
$$
Then:
$$
\bar{y} = \frac{27}{256\pi} \cdot \frac{4\pi}{9} \cdot 64 = \frac{27}{9} \cdot \frac{4 \cdot 64}{256} = 3 \cdot \frac{256}{256} = 3\ \mathrm{m}.
$$
This coincides with the well-known theorem that the centroid of a solid cone lies at $\frac{3}{4}$ of its height from the vertex:
$$
\bar{y} = \frac{3}{4} h_0 = \frac{3}{4}(4) = 3\ \mathrm{m}.
$$

#### Part D: Total Work by Centroid Elevation
The vertical distance from the center of mass $\bar{y} = 3\ \mathrm{m}$ to the discharge rim $y = 6\ \mathrm{m}$ is:
$$
\bar{D} = 6 - \bar{y} = 6 - 3 = 3\ \mathrm{m}.
$$
By the centroid principle:
$$
W = M \cdot g \cdot \bar{D} = \left(\frac{256\,000\pi}{27}\right) \cdot g \cdot 3 = \frac{256\,000\pi}{9} g = \frac{256\pi}{9} \rho g.
$$
This is algebraically identical to the result obtained by slice integration:
$$
W = \frac{256\pi}{9} \rho g = \frac{2\,508\,800 \pi}{9}\ \mathrm{J} \approx 875.74\ \mathrm{kJ}.
$$

### 4.2 Dimensional and Physical Consistency
- $[dV] = \mathrm{m}^3$
- $[\rho g] = \frac{\mathrm{kg}}{\mathrm{m}^3} \cdot \frac{\mathrm{m}}{\mathrm{s}^2} = \frac{\mathrm{N}}{\mathrm{m}^3}$
- $[dW] = [D(y)] \cdot [\rho g] \cdot [dV] = \mathrm{m} \cdot \frac{\mathrm{N}}{\mathrm{m}^3} \cdot \mathrm{m}^3 = \mathrm{N} \cdot \mathrm{m} = \mathrm{J}$ (Joules).

The units and mathematical results are completely verified.
