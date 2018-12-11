想要使用线性代数相关的工具，请用：`using LinearAlgebra`。

|                      |                                             |
| -------------------- | ------------------------------------------- |
| 单位矩阵              | `I # 直接用 I 就好。会自动转换到所需的维数。`  |
| 定义矩阵              | `M = [1 0; 0 1]`                            |
| 矩阵维数              | `size(M)`                                   |
| 选出第 `i` 行         | `M[i, :]`                                   |
| 选出第 `j` 列         | `M[:, j]`                                   |
| 水平拼接              | `M = [a b]` 或 `M = hcat(a, b)`             |
| 竖直拼接              | `M = [a ; b]` 或 `M = vcat(a, b)`           |
| 矩阵转置              | `transpose(M)`                              |
| 共轭转置              | `M'` 或 `adjoint(M)`                        |
| 迹(trace)             | `tr(M)`                                     |
| 行列式                | `det(M)`                                    |
| 秩(rank)              | `rank(M)`                                   |
| 特征值                | `eigvals(M)`                                |
| 特征向量              | `eigvecs(M)`                                |
| 矩阵求逆              | `inv(M)`                                    |
| 解矩阵方程 `M*x == v` | `M\v` 比 `inv(M)*v` <a class="tooltip" href="#">更好<span> 数值上更稳定，通常速度也更快。 </span></a>。 |
| 求 Moore-Penrose 伪逆 | `pinv(M)`                                   |

Julia 有内置的[矩阵分解函数](http://docs.juliacn.com/latest/stdlib/LinearAlgebra/#%E7%9F%A9%E9%98%B5%E5%88%86%E8%A7%A3-1)。

Julia 会试图推断矩阵是否为特殊矩阵(对称矩阵、厄米矩阵等)，但有时会失败。
为了帮助 Julia 分派最优的算法，可以声明矩阵具有特殊的结构。如：对称矩阵、厄密矩阵(Hermitian)、上三角矩阵、下三角矩阵、对角矩阵等。
