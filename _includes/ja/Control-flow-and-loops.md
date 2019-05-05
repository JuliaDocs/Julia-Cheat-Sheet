|                   |                                                          |
| ----------------- | -------------------------------------------------------- |
| 条件分岐       | `if-elseif-else-end`                                     |
| 単純な `for` ループ | `for i in 1:10`<br>`    println(i)`<br>`end`             |
| ２つのループ変数を，一つの `for` 文に書く | `for i in 1:10, j = 1:5`<br>`    println(i*j)`<br>`end`  |
| 数えながら繰り返す  | `for (idx, val) in enumerate(arr)`<br>`    println("the $idx-th element is $val")`<br>`end` |
| `while` ループ    | `while bool_expr`<br>`    # do stuff`<br>`end`           |
| ループから抜け出す     | `break`                                                  |
| 残りの処理をスキップする | `continue`                                               |
