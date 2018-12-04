|                                            |                                    |
| ------------------------------------------ | ---------------------------------- |
| Apply f to all elements of collection coll | `map(f, coll)` or<br>`map(coll) do elem`<br>`    # do stuff with elem`<br>`    # must contain return`<br>`end` |
| Filter coll for true values of f           | `filter(f, coll)`                  |
| List comprehension                         | `arr = [f(elem) for elem in coll]` |
