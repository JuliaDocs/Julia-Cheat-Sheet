
|                                             |                                                                                              |
| ------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Dicionário                                  | `d = Dict(key1 => val1, key2 => val2, ...)`<br>`d = Dict(:key1 => val1, :key2 => val2, ...)` |
| Todas as chaves (iterador)                  | `keys(d)`                                                                                    |
| Todos os valores (iterador)                 | `values(d)`                                                                                  |
| Repetição através de pares de chave-valor   | `for (k,v) in d`<br>`println("key: $k, value: $v")`<br>`end`                                 |
| Verificar chave `:k`                        | `haskey(d, :k)`                                                                              |
| Copiar chaves (ou valores) para um vetor    | `arr = collect(keys(d))`<br>`arr = [k for (k,v) in d]`                                       |

Dicionários são mutáveis; quando símbolos são usados como chaves, as chaves são imutáveis.