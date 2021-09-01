|                       |                                                  |
| --------------------- | ------------------------------------------------ |
| Null des programmeurs | `nothing`                                        |
| Donnée manquante      | `missing`                                        |
| Pas un Nombre Flottant | `NaN`                                            |
| Filtrer les manquants | `collect(skipmissing([1, 2, missing])) == [1,2]` |
| Remplacer les manquants | `collect((df[:col], 1))`                         |
| Vérifier les manquants | `ismissing(x)` **pas** `x == missing`            |
