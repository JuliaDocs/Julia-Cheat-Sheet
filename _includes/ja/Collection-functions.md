|                                            |                                    |
| ------------------------------------------ | ---------------------------------- |
| コレクション coll の全ての要素にfを適用する | `map(f, coll)` or<br>`map(coll) do elem`<br>`    # do stuff with elem`<br>`    # must contain return`<br>`end` |
| coll にfを適用し true(真)となる要素のみ取り出す | `filter(f, coll)`                  |
| リスト内包表記      | `arr = [f(elem) for elem in coll]` |
