|                       |                                                  |
| --------------------- | ------------------------------------------------ |
| 存在しない値  | `nothing`                                        |
| 欠損値 欠落したデータ   | `missing`                                        |
| Float型の，数でない値 | `NaN`                                            |
| `missing` を取り除く | `collect(skipmissing([1, 2, missing])) == [1,2]` |
| `missings` を置換する   | `collect((df[:col], 1))`  [訳注] (NG)                      |
| `missing` か否かをチェックする | `ismissing(x)` ( `x == missing` **ではない** )           |
