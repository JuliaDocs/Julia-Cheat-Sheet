
|                                |                                                                  |
| ------------------------------ | ---------------------------------------------------------------- |
| Dictionnaire                   | `d = Dict(key1 => val1, key2 => val2, ...)`<br>`d = Dict(:key1 => val1, :key2 => val2, ...)` |
| Toutes clés (itérateur)        | `keys(d)`                                                        |
| Toutes valeurs (itérateur)     | `values(d)`                                                      |
| Itérer par paire clé-valeur    | `for (k,v) in d`<br>`    println("key: $k, value: $v")`<br>`end` |
| Vérifier la présence de la clé `:k` | `haskey(d, :k)`                                                  |
| Copier les clés (ou valeurs) vers un tableau | `arr = collect(keys(d))`<br>`arr = [k for (k,v) in d]`           |

Les dictionnaires sont muables; quand des symboles sont utilisés comme clés, les clés sont immuables.
