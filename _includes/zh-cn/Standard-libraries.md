为了让 Julia 能加载的更快，许多核心组件都放在与 Julia 捆绑在一起的标准库中。
当你想用某一个标准库时，就输入 `using PackageName`。
以下是一些标准库及其常用的函数。

|                 |                                              |
| --------------- | -------------------------------------------- |
| `Random`        | `rand`, `randn`, `randsubseq`                |
| `Statistics`    | `mean`, `std`, `cor`, `median`, `quantile`   |
| `LinearAlgebra` | `I`, `eigvals`, `eigvecs`, `det`, `cholesky` |
| `SparseArrays`  | `sparse`, `SparseVector`, `SparseMatrixCSC`  |
| `Distributed`   | `@distributed`, `pmap`, `addprocs`           |
| `Dates`         | `DateTime`, `Date`                           |

