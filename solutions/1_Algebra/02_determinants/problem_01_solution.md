## Problem

Compute
$$
\det\begin{pmatrix}3&-2\\5&4\end{pmatrix},\qquad \det\begin{pmatrix}1&7\\2&14\end{pmatrix}.
$$

Which matrix is invertible? Justify your answer.

## Solution

**Step 1 — calculate the determinants**

A $2 \times 2$ matrix is invertible exactly when its determinant is non-zero. Therefore, the first thing to calculate is the determinant for each matrix. The determinant of a general $2 \times 2$ matrix is calculated using the formula $ad - bc$.

For the first matrix:
$$
\det\begin{pmatrix}3&-2\\5&4\end{pmatrix} = 3 \cdot 4 - (-2) \cdot 5 = 12 + 10 = 22.
$$

For the second matrix:
$$
\det\begin{pmatrix}1&7\\2&14\end{pmatrix} = 1 \cdot 14 - 7 \cdot 2 = 14 - 14 = 0.
$$

**Conclusion**

The first matrix, $\begin{pmatrix}3&-2\\5&4\end{pmatrix}$, is the only invertible matrix. A square matrix is invertible if and only if its determinant is non-zero. Because the first matrix has a non-zero determinant of $22$, it has an inverse. The second matrix is not invertible (it is singular) because its determinant is exactly $0$.