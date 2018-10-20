For most linear algebra tools, use `using LinearAlgebra`.
Para mais ferramentas de Álgebra Linear, use `using LinearAlgebra`.

|                                |                                                                                                                                            |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Matriz Identidade                | `I  # just use variable I. Will automatically conform to dimensions required.         `                                                    |
| Definir Matriz                 | `M = [1 0; 0 1]         `                                                                                                                  |
| Dimensão da Matriz              | `size(M)         `                                                                                                                         |
| Selecionar `i`-ésima linha             | `M[i, :]`                                                                                                                                  |
| Slecionar `i`-ésima coluna          | `M[:, i]`                                                                                                                                  |
| Concatenar horizontalmente      | `M = [a b]` or `M = hcat(a, b)`                                                                                                            |
| Concatenar verticalmente         | `M = [a ; b` or `M = vcat(a, b)`                                                                                                           |
| Matriz Transposta           | `transpose(M)`                                                                                                                             |
| Matriz Transposta Hermitiana | `M'` or `adjoint(M)`                                                                                                                       |
| Traço da Matriz                  | `tr(M)`                                                                                                                                    |
| Determinante             | `det(M)`                                                                                                                                   |
| Posto da Matriz                   | `rank(M)`                                                                                                                                  |
| Autovalores             | `eigvals(M)`                                                                                                                               |
| Autovetores            | `eigvecs(M)`                                                                                                                               |
| Matriz Inversa                 | `inv(M)`                                                                                                                                   |
| Resolver `M*x == v`               | `M\v         ` é <a class="tooltip" href="#">melhor <span> Numericamente mais estável e também mais rápido. </span></a> than `inv(M)*v` |
| Moore-Penrose pseudo-inverse   | `pinv(M)`                                                                                                                                  |

Julia foi construída para dar suporte a [decomposições matriciais](https://docs.julialang.org/en/v1.0.0/stdlib/LinearAlgebra/).

Julia tries to infer whether matrices are of a special type (symmetric,
hermitian, etc.), but sometimes fails. To aid Julia in dispatching the
optimal algorithms, special matrices can be declared to have a structure
with functions like `Symmetric` , `Hermitian` , `UpperTriangular`, `LowerTriangular`,
`Diagonal` , and more.
