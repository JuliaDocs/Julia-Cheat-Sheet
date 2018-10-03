To help Julia load faster, many core functionalities exist in standard libraries that
come bundled with Julia. To make their functions available, use `using PackageName`. Here
are some Standard Libraries and popular functions.

|                 |                                              |
| --------------- | -------------------------------------------- |
| `Random`        | `rand`, `randn`, `randsubseq`                |
| `Statistics`    | `mean`, `std`, `cor`, `median`, `quantile`   |
| `LinearAlgebra` | `I`, `eigvals`, `eigvecs`, `det`, `cholesky` |
| `SparseArrays`  | `sparse`, `SparseVector`, `SparseMatrixCSC`  |
| `Distributed`   | `@distributed`, `pmap`, `addprocs`           |
| `Dates`         | `DateTime`, `Date`                           |

