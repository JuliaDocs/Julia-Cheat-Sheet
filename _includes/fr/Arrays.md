|                                                                   |                                                                                        |
| ---------------------------------                                 | -------------------------------------------                                            |
| Déclaration                                                       | `arr = Float64[]`                                                                      |
| Pré-allocation                                                    | `sizehint!(arr, 10^4)`                                                                 |
| Accès et mutation                                                 | `arr = Any[1,2]`<br>`arr[1] = "Some text"`                                             |
| Comparaison                                                       | `a = [1:10;]`<br>`b = a      # b pointe vers a`<br>`a[1] = -99`<br>`a == b     # true` |
| Copie des éléments (distincte en mémoire)                         | `b = copy(a)     # un seul niveau`<br>`b = deepcopy(a) # récursivement`                |
| Sous-tableau de `m` à `n`                                         | `arr[m:n]`                                                                             |
| Tableau de `n` éléments, rempli de `0.0`                          | `zeros(n)`                                                                             |
| Tableau de `n` éléments, rempli de `1.0`                          | `ones(n)`                                                                              |
| Tableau de `n` éléments, non initialisé                           | `Vector{Type}(undef,n)`                                                                |
| `n` nombres équi-répartis entre `start` et `stop`                 | `range(start,stop=stop,length=n)`                                                      |
| `n` nombres (`Int8`) aléatoires                                   | `rand(Int8, n)`                                                                        |
| Remplir `arr` avec des `val`                                      | `fill!(arr, val)`                                                                      |
| Suppression d'un élément en fin de tableau                        | `pop!(arr)`                                                                            |
| Suppression d'un élément en début de tableau                      | `popfirst!(a)`                                                                         |
| Ajout d'un élément en fin de tableau                              | `push!(arr, val)`                                                                      |
| Ajout d'un élément en début de tableau                            | `pushfirst!(arr, val)`                                                                 |
| Suppression de l'élément d'indice `idx`                           | `deleteat!(arr, idx)`                                                                  |
| Tri (en place)                                                    | `sort!(arr)`                                                                           |
| Concaténation de `b` à la suite de `a` (en place)                 | `append!(a,b)`                                                                         |
| Test si `val` est un élément de `arr`                             | `in(val, arr)` ou `val in arr`                                                           |
| Produit scalaire                                                  | `dot(a, b) == sum(a .* b)`                                                             |
| Changement de dimensions (si possible)                            | `reshape(1:6, 3, 2)' == [1 2 3; 4 5 6]`                                                |
| Conversion en chaîne de caractères (éléments séparés par `delim`) | `join(arr, delim)`                                                                     |
