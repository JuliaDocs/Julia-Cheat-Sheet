Para ayudar a carga Julia más rápido, muchas de las funciones principales están en
las bibliotecas incluídas por defecto con Julia. Para disponibilizarlas, use `using
PackageName`. A continuación algunas Bibliotecas Estándar y funciones populares.

|                 |                                              |
| --------------- | -------------------------------------------- |
| `Random`        | `rand`, `randn`, `randsubseq`                |
| `Statistics`    | `mean`, `std`, `cor`, `median`, `quantile`   |
| `LinearAlgebra` | `I`, `eigvals`, `eigvecs`, `det`, `cholesky` |
| `SparseArrays`  | `sparse`, `SparseVector`, `SparseMatrixCSC`  |
| `Distributed`   | `@distributed`, `pmap`, `addprocs`           |
| `Dates`         | `DateTime`, `Date`                           |
