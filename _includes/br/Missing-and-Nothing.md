|                       |                                         |
| --------------------- | --------------------------------------- |
| Null do programador   | `nothing`                               |
| Dados `missing`        | `missing`                              |
| `Não é um Número` em float | `NaN`                              |
| Filtrar `missing`        | `skipmissing([1, 2, missing]) == [1,2]` |
| Substituir `missing`     | `collect((df[:col], 1))`                |
| Checkar se variável tem valor de `missing` | `ismissing(x) not x == missing`|
