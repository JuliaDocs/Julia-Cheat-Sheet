Para la mayoría de las herramientas de álgebra lineal, use `using LinearAlgebra`.

|                                       |                                             |
| ------------------------------------- | ------------------------------------------- |
| Matriz Identidad                      | `I  # Simplemente use la variable I. Se ajustará automáticamente a las dimensiones requeridas.` |
| Definir matriz                        | `M = [1 0; 0 1]`                            |
| Dimensiones de la matriz              | `size(M)`                                   |
| Seleccionar la fila `i`               | `M[i, :]`                                   |
| Seleccionar la columna `i`            | `M[:, i]`                                   |
| Concatenar horizontalmente            | `M = [a b]` or `M = hcat(a, b)`             |
| Concatenar verticalmente              | `M = [a ; b]` or `M = vcat(a, b)`           |
| Transposición de matriz               | `transpose(M)`                              |
| Transposición y conjugada de matriz   | `M'` or `adjoint(M)`                        |
| Traza de matriz                       | `tr(M)`                                     |
| Determinante de matriz                | `det(M)`                                    |
| Rango de matriz                       | `rank(M)`                                   |
| Valores propios de matriz             | `eigvals(M)`                                |
| Vectores propios de matriz            | `eigvecs(M)`                                |
| Inversa de la matriz                  | `inv(M)`                                    |
| Resolver `M*x == v`                   | `M\v` es <a class="tooltip" href="#">mejor <span> Numéricamente más estable y normalmente más rápida. </span></a> que `inv(M)*v` |
| Pseudoinversa de Moore-Penrose        | `pinv(M)`                                   |

Julia incorpora soporte para [factorización de matrices](https://docs.julialang.org/en/v1.0.0/stdlib/LinearAlgebra/).

Julia intenta inferir si las matrices son de un tipo especial (simétrica,
hermítica, etc.), pero falla algunas veces. Para ayudar a Julia a seleccionar
los mejores algoritmos, las matrices especiales pueden ser declaradas explícitamente
con una estructura, por medio de las funciones `Symmetric` , `Hermitian` , 
`UpperTriangular`, `LowerTriangular`, `Diagonal` , etc.