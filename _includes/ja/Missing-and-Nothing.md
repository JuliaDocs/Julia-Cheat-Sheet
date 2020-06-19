|                       |                                                  |
| --------------------- | ------------------------------------------------ |
| 存在しない値  | `nothing`                                        |
| 欠落したデータ   | `missing`                                        |
| Float型の，数でない値 | `NaN`, `NaN16`, `NaN32`, `NaN64`, `big"NaN"`  <br /> `NaN === NaN64` |
| `missing` を取り除く | `collect(skipmissing([1, 2, missing])) == [1, 2]` |
| `missings` を置換する   | `replace([1, missing, 2], missing=>0) == [1, 0, 2]` |
| `missing` か否かを検査する | `ismissing(x)`．注意: `x == missing` では検査できません |
