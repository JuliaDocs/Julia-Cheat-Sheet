Las macros permiten que sea incluido en un programa código generado (o sea, expresiones).

|                       |                                                            |
| --------------------- | ---------------------------------------------------------- |
| Definición            | `macro macroname(expr)`<br>`    # bloque de código`<br>`end`       |
| Uso                   | `macroname(ex1, ex2, ...)` or `@macroname ex1, ex2, ...`   |
| Macros incorporadas   | `@test           # equal (exact)`<br>`@test_approx_eq # equal (modulo numerical errors)`<br>`@test x ≈ y    # isapprox(x, y)`<br>`@assert         # assert (unit test)`<br>`@which          # tipos utilizados`<br>`@time           # estadísticas de memoria y tiempo`<br>`@elapsed        # tiempo transcurrido`<br>`@allocated      # memoria asignada`<br>`@profile        # perfil`<br>`@spawn          # ejecutar en un worker`<br>`@spawnat        # ejecutar en worker específico`<br>`@async          # tarea asíncrona`<br>`@distributed    # bucle for paralelo`<br>`@everywhere     # poner a disposición de los workers` |


Reglas para crear macros *limpias*:

- Declarar las variables dentro de la macro con `local` .
- No llamar `eval` dentro de la macro.
- Hacer secuencia de escape sobre expresiones interpoladas para evitar expansión: `$(esc(expr))`
