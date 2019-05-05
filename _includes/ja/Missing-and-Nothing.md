|                       |                                                  |
| --------------------- | ------------------------------------------------ |
| 存在しない値  | `nothing`                                        |
| 欠落したデータ   | `missing`                                        |
| Float型の，数でない値 | `NaN`                                            |
| `missing` を取り除く | `collect(skipmissing([1, 2, missing])) == [1,2]` |
| `missings` を置換する   | `collect((df[:col], 1))`                         |
| `missing` か否かをチェックする | `ismissing(x)` **not** `x == missing`            |
