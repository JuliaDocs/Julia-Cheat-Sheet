Para a maioria das ferramentas de Álgebra Linear, use `using LinearAlgebra`.

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

Julia tenta inferir se as matrizes são de tipos especiais (Simétricas,
Hermitianas, etc.), mas as vezes falha. Para ajudar Julia a despachar
algoritmos ótimos, matrizes especiais podem ser declaradas para ter uma
estrutura de funções como `Symmetric` , `Hermitian` , `UpperTriangular`, `LowerTriangular`,
`Diagonal`, e muito mais.
