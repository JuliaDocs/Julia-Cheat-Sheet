For most linear algebra tools, use `using LinearAlgebra`.

|                                |                                                                                                                                            |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Identity matrix                | `I  # just use variable I. Will automatically conform to dimensions required.         `                                                    |
| Define matrix                  | `M = [1 0; 0 1]         `                                                                                                                  |
| Matrix dimensions              | `size(M)         `                                                                                                                         |
| Select `i` th row              | `M[i, :]`                                                                                                                                  |
| Select `i` th column           | `M[:, i]`                                                                                                                                  |
| Concatenate horizontally       | `M = [a b]` or `M = hcat(a, b)`                                                                                                            |
| Concatenate vertically         | `M = [a ; b]` or `M = vcat(a, b)`                                                                                                           |
| Matrix transposition           | `transpose(M)`                                                                                                                             |
| Conjugate matrix transposition | `M'` or `adjoint(M)`                                                                                                                       |
| Matrix trace                   | `tr(M)`                                                                                                                                    |
| Matrix determinant             | `det(M)`                                                                                                                                   |
| Matrix rank                    | `rank(M)`                                                                                                                                  |
| Matrix eigenvalues             | `eigvals(M)`                                                                                                                               |
| Matrix eigenvectors            | `eigvecs(M)`                                                                                                                               |
| Matrix inverse                 | `inv(M)`                                                                                                                                   |
| Solve `M*x == v`               | `M\v         ` is <a class="tooltip" href="#">better <span> Numerically more stable and typically also faster. </span></a> than `inv(M)*v` |
| Moore-Penrose pseudo-inverse   | `pinv(M)`                                                                                                                                  |

Julia has built-in support for [matrix
decompositions](https://docs.julialang.org/en/v1.0.0/stdlib/LinearAlgebra/).

Julia tries to infer whether matrices are of a special type (symmetric,
hermitian, etc.), but sometimes fails. To aid Julia in dispatching the
optimal algorithms, special matrices can be declared to have a structure
with functions like `Symmetric` , `Hermitian` , `UpperTriangular`, `LowerTriangular`,
`Diagonal` , and more.
