# Solution to Exercise 1: Matrix Size and Entries

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 2 & -1 & 3 \\ 0 & 4 & 5 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 0 \\ -2 & 3 \\ 4 & 1 \end{pmatrix}
$$

1. State the sizes of matrices $A$ and $B$.
2. Read off the entries $a_{12}$, $a_{23}$, $b_{21}$, and $b_{32}$.
3. Write the second row of $A$ and the first column of $B$ as vectors.

---

## 2. Theoretical Background and Concepts

1. **Matrix Dimensions (Size):**
   A matrix of size $m \times n$ (read "$m$ by $n$") consists of $m$ horizontal rows and $n$ vertical columns:
   $$
   M = \begin{pmatrix}
   m_{11} & m_{12} & \cdots & m_{1n} \\
   m_{21} & m_{22} & \cdots & m_{2n} \\
   \vdots & \vdots & \ddots & \vdots \\
   m_{m1} & m_{m2} & \cdots & m_{mn}
   \end{pmatrix}
   $$

2. **Index Notation:**
   The entry in row $i$ (counting from the top, $1 \le i \le m$) and column $j$ (counting from the left, $1 \le j \le n$) is denoted by $m_{ij}$. The first index $i$ always specifies the row, while the second index $j$ specifies the column.

3. **Row and Column Vectors:**
   - The $i$-th **row vector** of a matrix $M$ is formed by taking all entries along row $i$:
     $$
     \mathbf{r}_i(M) = \begin{pmatrix} m_{i1} & m_{i2} & \cdots & m_{in} \end{pmatrix} \in \mathbb{R}^{1 \times n}
     $$
   - The $j$-th **column vector** of a matrix $M$ is formed by taking all entries down column $j$:
     $$
     \mathbf{c}_j(M) = \begin{pmatrix} m_{1j} \\ m_{2j} \\ \vdots \\ m_{mj} \end{pmatrix} \in \mathbb{R}^{m \times 1}
     $$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Determine the Sizes of Matrices $A$ and $B$

- **Matrix $A$:**
  $$
  A = \begin{pmatrix} 2 & -1 & 3 \\ 0 & 4 & 5 \end{pmatrix}
  $$
  Counting the rows (horizontal lines) gives $2$ rows.
  Counting the columns (vertical lines) gives $3$ columns.
  Therefore, the size of matrix $A$ is **$2 \times 3$**.

- **Matrix $B$:**
  $$
  B = \begin{pmatrix} 1 & 0 \\ -2 & 3 \\ 4 & 1 \end{pmatrix}
  $$
  Counting the rows gives $3$ rows.
  Counting the columns gives $2$ columns.
  Therefore, the size of matrix $B$ is **$3 \times 2$**.

### Step 2: Read Off the Entries

Using the standard index convention $(i, j) = (\text{row}, \text{column})$:

- **$a_{12}$:** Entry in row $1$, column $2$ of matrix $A$:
  - Row $1$ is $\begin{pmatrix} 2 & -1 & 3 \end{pmatrix}$.
  - The second element in this row is $-1$.
  $$a_{12} = -1$$

- **$a_{23}$:** Entry in row $2$, column $3$ of matrix $A$:
  - Row $2$ is $\begin{pmatrix} 0 & 4 & 5 \end{pmatrix}$.
  - The third element in this row is $5$.
  $$a_{23} = 5$$

- **$b_{21}$:** Entry in row $2$, column $1$ of matrix $B$:
  - Row $2$ is $\begin{pmatrix} -2 & 3 \end{pmatrix}$.
  - The first element in this row is $-2$.
  $$b_{21} = -2$$

- **$b_{32}$:** Entry in row $3$, column $2$ of matrix $B$:
  - Row $3$ is $\begin{pmatrix} 4 & 1 \end{pmatrix}$.
  - The second element in this row is $1$.
  $$b_{32} = 1$$

### Step 3: Write the Specified Rows and Columns as Vectors

- **Second row of $A$:**
  Extracting the entries of row $2$ from $A$:
  $$
  \mathbf{r}_2(A) = \begin{pmatrix} 0 & 4 & 5 \end{pmatrix}
  $$
  *(or in standard tuple notation: $(0, 4, 5)$)*.

- **First column of $B$:**
  Extracting the entries of column $1$ from $B$:
  $$
  \mathbf{c}_1(B) = \begin{pmatrix} 1 \\ -2 \\ 4 \end{pmatrix}
  $$
  *(or written as the transpose of a row vector: $\begin{pmatrix} 1 & -2 & 4 \end{pmatrix}^T$)*.

---

## 4. Verification and Consistency Checks

1. **Dimensional Consistency:**
   - Matrix $A$ has $2 \times 3 = 6$ total scalar entries:
     $$a_{11}=2,\; a_{12}=-1,\; a_{13}=3,\; a_{21}=0,\; a_{22}=4,\; a_{23}=5.$$
     This confirms that $a_{12}=-1$ and $a_{23}=5$ are within valid index bounds and correctly identified.
   - Matrix $B$ has $3 \times 2 = 6$ total scalar entries:
     $$b_{11}=1,\; b_{12}=0,\; b_{21}=-2,\; b_{22}=3,\; b_{31}=4,\; b_{32}=1.$$
     This confirms that $b_{21}=-2$ and $b_{32}=1$ are within valid index bounds and correctly identified.

2. **Vector Dimension Check:**
   - Any row vector of $A$ must have length equal to the number of columns of $A$ ($n = 3$). Indeed, $\mathbf{r}_2(A)$ has $3$ components: $(0, 4, 5)$.
   - Any column vector of $B$ must have length equal to the number of rows of $B$ ($m = 3$). Indeed, $\mathbf{c}_1(B)$ has $3$ components: $\begin{pmatrix} 1 \\ -2 \\ 4 \end{pmatrix}$.

3. **Multiplication Compatibility Check:**
   - Since $A$ is $2 \times 3$ and $B$ is $3 \times 2$, their product $AB$ is well-defined.
   - Specifically, entry $(AB)_{21} = \mathbf{r}_2(A) \cdot \mathbf{c}_1(B) = 0 \cdot 1 + 4 \cdot (-2) + 5 \cdot 4 = 0 - 8 + 20 = 12$, directly confirming the inner consistency of the extracted row $\mathbf{r}_2(A)$ and column $\mathbf{c}_1(B)$.

