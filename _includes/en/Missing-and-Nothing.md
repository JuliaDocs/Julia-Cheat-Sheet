|                       |                                                     |
| --------------------- | --------------------------------------------------- |
| Programmers Null      | `nothing`                                           |
| Missing Data          | `missing`                                           |
| Not a Number in Float | `NaN` and `NaN16`, `NaN32`, `NaN64`, `big"NaN"`  <br /> `NaN === NaN64` |
| Filter missings       | `collect(skipmissing([1, missing, 2])) == [1, 2]`   |
| Replace missings      | `replace([1, missing, 2], missing=>0) == [1, 0, 2]` |
| Check if missing      | `ismissing(x)` **not** `x == missing`               |
