|                                                 |                                                                                      |
| ----------------------------------------------- | ------------------------------------------------------------------------------------ |
| Declaração                                      | `arr = Float64[]`                                                                    |
| Pre-alocação                                    | `sizehint!(arr, 10^4)`                                                               |
| Acesso e atribuição	                          | `arr = Any[1,2]`<br>`arr[1] = "Some text"`                                           |
| Comparação                                      | `a = [1:10;]`<br>`b = a      # b points to a`<br>`a[1] = -99`<br>`a == b     # true` |
| Copiar elementos (não endereços)                | `b = copy(a)`<br>`b = deepcopy(a)`                                                   |
| Selecionar a subarray de m para n               | `arr[m:n]`                                                                           |
| n-elemento array com 0.0s                       | `zeros(n)`                                                                           |
| n-elemento array com 1.0s                       | `ones(n)`                                                                            |
| n-elemento array com #undefs                    | `Vector{Type}(undef,n)`                                                              |
| n números igualmente espaçados do início ao fim | `range(start,stop=stop,length=n)`                                                    |
| Array com n elementos aleatórios Int8           | `rand(Int8, n)`                                                                      |
| Preencher array com val                         | `fill!(arr, val)`                                                                    |
| Mostrar ultimo elemento                         | `pop!(arr)`                                                                          |
| Mostrar primeiro elemento                       | `popfirst!(a)`                                                                       |
| Enviar val como último elemento                 | `push!(arr, val)`                                                                    |
| Enviar val como primeiro elemento               | `pushfirst!(arr, val)`                                                               |
| Remover elemento em index idx                   | `deleteat!(arr, idx)`                                                                |
| Ordenar                                         | `sort!(arr)`                                                                         |
| Acrescentar a com b                             | `append!(a,b)`                                                                       |
| Verificar se val é um elemento                  | `in(val, arr) or val in arr`                                                         |
| Produto Escalar                                 | `dot(a, b) == sum(a .* b)`                                                           |
| Alterar dimensões (s possível)                  | `reshape(1:6, 3, 2)' == [1 2 3; 4 5 6]`                                              |
| Para String (com delimitador del entre elementos) | `join(arr, del)`                                                                     |
