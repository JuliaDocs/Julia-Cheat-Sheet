|                                            |                                    |
| ------------------------------------------ | ---------------------------------- |
| Aplicar f a todos los elementos de la colección coll | `map(f, coll)` or<br>`map(coll) do elem`<br>`    # hacer cosas con elem`<br>`    # debe contener return`<br>`end` |
| Filtra coll para los valores verdaderos de f           | `filter(f, coll)`                  |
| Lista por comprensión                         | `arr = [f(elem) for elem in coll]` |
