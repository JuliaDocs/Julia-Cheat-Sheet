|                       |                                         |
| --------------------- | --------------------------------------- |
| Programmers Null      | `nothing`                               |
| Missing Data          | `missing`                               |
| Not a Number in Float | `NaN`                                   |
| Filter missings       | `skipmissing([1, 2, missing]) == [1,2]` |
| Replace missings      | `collect((df[:col], 1))`                |
| Check if missing      | `ismissing(x) not x == missing`         |
