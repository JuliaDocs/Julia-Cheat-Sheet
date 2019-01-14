
|                                |                                                                  |
| ------------------------------ | ---------------------------------------------------------------- |
| Diccionario | `d = Dict(key1 => val1, key2 => val2, ...)`<br>`d = Dict(:key1 => val1, :key2 => val2, ...)` |
| Todas las claves (iterador)            | `keys(d)`                                                        |
| Todos los valores (iterador)          | `values(d)`                                                      |
| Bucle por los pares clave-valor   | `for (k,v) in d`<br>`    println("key: $k, value: $v")`<br>`end` |
| Verificar la clave `:k`             | `haskey(d, :k)`                                                  |
| Copiar claves (o valores) a la matriz | `arr = collect(keys(d))`<br>`arr = [k for (k,v) in d]`           |

Los diccionarios son mutables; cuando se utilizan símbolos como claves, las claves son inmutábles.
