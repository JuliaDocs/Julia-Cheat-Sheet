Para a maioria das ferramentas de Álgebra Linear, use `using LinearAlgebra`.

|                                   |                                                                                                                                            |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Matriz Identidade                 | `I  # use somente a variável I. Será automaticamente ajustada conforme as dimensões requeridas.         `                                  |
| Definir Matriz                    | `M = [1 0; 0 1]         `                                                                                                                  |
| Dimensão da Matriz                | `size(M)         `                                                                                                                         |
| Selecionar `i`-ésima linha        | `M[i, :]`                                                                                                                                  |
| Selecionar `i`-ésima coluna       | `M[:, i]`                                                                                                                                  |
| Concatenar horizontalmente        | `M = [a b]` ou `M = hcat(a, b)`                                                                                                            |
| Concatenar verticalmente          | `M = [a ; b]` ou `M = vcat(a, b)`                                                                                                          |
| Matriz Transposta                 | `transpose(M)`                                                                                                                             |
| Matriz Transposta Conjugada       | `M'` ou `adjoint(M)`                                                                                                                       |
| Traço da Matriz                   | `tr(M)`                                                                                                                                    |
| Determinante                      | `det(M)`                                                                                                                                   |
| Posto da Matriz                   | `rank(M)`                                                                                                                                  |
| Autovalores                       | `eigvals(M)`                                                                                                                               |
| Autovetores                       | `eigvecs(M)`                                                                                                                               |
| Matriz Inversa                    | `inv(M)`                                                                                                                                   |
| Resolver `M*x == v`               | `M\v         ` é <a class="tooltip" href="#"> melhor <span> Numericamente mais estável e tipicamente mais rápido. </span></a> que `inv(M)*v`     |
| Pseudo-inversa de Moore-Penrose   | `pinv(M)`                                                                                                                                  |

Julia tem suporte nativo a [decomposições matriciais](https://docs.julialang.org/en/v1.0.0/stdlib/LinearAlgebra/).

Julia tenta inferir se as matrizes são de tipos especiais (Simétricas, Hermitianas, etc.), mas as vezes falha. Para ajudar Julia a despachar algoritmos ótimos, matrizes especiais podem ser declaradas para ter uma estrutura com funções como `Symmetric` , `Hermitian` , `UpperTriangular`, `LowerTriangular`, `Diagonal`, e mais.
