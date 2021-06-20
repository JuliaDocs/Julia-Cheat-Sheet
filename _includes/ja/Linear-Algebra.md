線形代数のツールの多くを使う場合には，`using LinearAlgebra` してください．

|                                |                                             |
| ------------------------------ | ------------------------------------------- |
| 単位行列        | `I  # 定数 LinearAlgebra.I. 任意の寸法の行列に対して恒等変換となる.` |
| 行列を定義する              | `M = [1 0; 0 1]`                            |
| 行列の寸法        | `size(M)`                                   |
| インデックス `i` の列を選ぶ      | `M[i, :]`                                   |
| インデックス `i` の列を選ぶ  | `M[:, i]`                                   |
| 水平方向に連結する   | `M = [a b]` または `M = hcat(a, b)`             |
| 垂直方向に連結する    | `M = [a ; b]` または `M = vcat(a, b)`           |
| 行列の転置       | `transpose(M)`                              |
| 行列の共役転置 | `M'` or `adjoint(M)`                        |
| 行列の跡 (トレース)                   | `tr(M)`                                     |
| 行列式   | `det(M)`                                    |
| 行列の階数 (ランク)       | `rank(M)`                                   |
| 行列の固有値       | `eigvals(M)`                                |
| 行列の固有ベクトル        | `eigvecs(M)`                                |
| 逆行列         | `inv(M)`                                    |
| 行列方程式 `M*x == v` を解く              | `M\v` の方が<a class="tooltip" href="#">優れる．<span>逆行列を使うより，数値的に安定で，計算が速い</span></a>，`inv(M)*v` |
| Moore-Penrose の擬似逆行列  | `pinv(M)`                                   |

Julia は，行列の分解([matrix
decompositions](https://docs.julialang.org/en/v1/stdlib/LinearAlgebra/))を組み込みで用意しています．

Julia は，行列が特別な種類(対称，エルミートなど)であるかを推定しようとしますが，
失敗することもあります．
Julia が，最適なアルゴリズムを選択するのを助けるために，
特別な行列は，その構造を表した関数 (`Symmetric`, `Hermitian`, `UpperTriangular`, `LowerTriangular`, `Diagonal` など) を用いて定義できます．
