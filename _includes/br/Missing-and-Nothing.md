|                         |                                         |
| ------------------------| --------------------------------------- |
| Programmers Null        | `nothing`                               |
| Informação faltante     | `missing`                               |
| Não numero em flutuante | `NaN`                                   |
| Filtrar faltas          | `skipmissing([1, 2, missing]) == [1,2]` |
| Retirar faltas          | `collect((df[:col], 1))`                |
| Checar faltas           | `ismissing(x) not x == missing`         |
