Juliaのロードを高速化するため，多くのコア機能が Juliaに付属する標準ライブラリに入っています．
これらの機能を使えるようにするには，`using PackageName` を使います．
以下に，標準ライブラリの一部と，よく使う関数を示します．


|                 |                                              |
| --------------- | -------------------------------------------- |
| `Random`        | `rand`, `randn`, `randsubseq`                |
| `Statistics`    | `mean`, `std`, `cor`, `median`, `quantile`   |
| `LinearAlgebra` | `I`, `eigvals`, `eigvecs`, `det`, `cholesky` |
| `SparseArrays`  | `sparse`, `SparseVector`, `SparseMatrixCSC`  |
| `Distributed`   | `@distributed`, `pmap`, `addprocs`           |
| `Dates`         | `DateTime`, `Date`                           |
