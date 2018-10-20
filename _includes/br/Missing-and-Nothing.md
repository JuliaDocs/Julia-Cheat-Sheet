|                       |                                         |
| --------------------- | --------------------------------------- |
| Programadores Nulos     | `nothing`                               |
| Dados perdidos        | `missing`                               |
| Não é um número do tipo 'Float'| `NaN`                                   |
| Filtrar perdas     | `skipmissing([1, 2, missing]) == [1,2]` |
| Recoletar perdas      | `collect((df[:col], 1))`                |
| Checar se esta perdido   | `ismissing(x) not x == missing`         |
