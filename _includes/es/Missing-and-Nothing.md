|                               |                                                  |
| ----------------------------- | ------------------------------------------------ |
| Null (programación)           | `nothing`                                        |
| Datos faltantes               | `missing`                                        |
| Not a Number en coma flotante | `NaN`                                            |
| Filtrar faltantes             | `collect(skipmissing([1, 2, missing])) == [1,2]` |
| Substituir faltantes          | `collect((df[:col], 1))`                         |
| Verificar faltantes           | `ismissing(x)` **not** `x == missing`            |
