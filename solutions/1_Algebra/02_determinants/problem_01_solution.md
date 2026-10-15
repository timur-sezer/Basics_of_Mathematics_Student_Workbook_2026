```python
def det_2x2(a, b, c, d):
    return a*d - b*c

det1 = det_2x2(3, -2, 5, 4)
det2 = det_2x2(1, 7, 2, 14)
print(f"Det 1: {det1}, Det 2: {det2}")

```

```text
Det 1: 22, Det 2: 0


```

The determinant of a $2 \times 2$ matrix $\begin{pmatrix}a&b\\c&d\end{pmatrix}$ is calculated using the formula $ad - bc$.

For the first matrix:


$$\det\begin{pmatrix}3&-2\\5&4\end{pmatrix} = (3)(4) - (-2)(5) = 12 + 10 = 22$$

For the second matrix:


$$\det\begin{pmatrix}1&7\\2&14\end{pmatrix} = (1)(14) - (7)(2) = 14 - 14 = 0$$

The first matrix, $\begin{pmatrix}3&-2\\5&4\end{pmatrix}$, is the only invertible matrix. A square matrix is invertible if and only if its determinant is non-zero. Because the first matrix has a determinant of $22$, it has an inverse, whereas the second matrix is singular because its determinant is exactly $0$.