
|                                             |                                                                                              |
| ------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Dicionário                                  | `d = Dict(key1 => val1, key2 => val2, ...)`<br>`d = Dict(:key1 => val1, :key2 => val2, ...)` |
| Todas as chaves (iterador)                  | `keys(d)`                                                                                    |
| Todos os valores (iterador)                 | `values(d)`                                                                                  |
| Laços pelos pares de chave-valor            | `for (k,v) in d`<br>`println("chave: $k, valor: $v")`<br>`end`                               |
| Verifica existência de chave `:k`           | `haskey(d, :k)`                                                                              |
| Copiar chaves (ou valores) para um vetor    | `arr = collect(keys(d))`<br>`arr = [k for (k,v) in d]`                                       |

Dicionários são mutáveis; quando símbolos são usados como chaves, as chaves são imutáveis.
