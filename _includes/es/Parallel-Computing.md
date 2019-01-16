Las herramientas de cálculo en paralelo están disponibles en la biblioteca estándar `Distributed`.

|                                            |                                   |
| ------------------------------------------ | --------------------------------- |
| Ejecutar REPL con N workers                | `julia -p N`                      |
| Número de workers disponibles              | `nprocs()`                        |
| Añadir N workers                           | `addprocs(N)`                     |
| Ver todos los ids de los workers           | `for pid in workers()`<br>`    println(pid)`<br>`end` |
| Obtener el id de ejecución del worker      | `myid()`                          |
| Eliminar worker                              | `rmprocs(pid)`                    |
| Ejecutar f con los argumentos args en pid           | `r = remotecall(f, pid, args...)`<br>`# or:`<br>`r = @spawnat pid f(args)`<br>`...`<br>`fetch(r)` |
| Ejecutar f con los argumentos args en pid (más eficiente) | `remotecall_fetch(f, pid, args...)` |
| Ejecutar f con los argumentos args en cualquier worker    | `r = @spawn f(args) ... fetch(r)` |
| Ejecutar f con los argumentos args en todos los workers   | `r = [@spawnat w f(args) for w in workers()] ... fetch(r)` |
| Poner expr a disposición de todos los workers         | `@everywhere expr`                |
| Bucle for paralelo con función <a class="tooltip" href="#">reductora<span>Un reductor combina los resultados diferentes workers independientes.</span></a> red | `sum = @distributed (red) for i in 1:10^6`<br>`    # bloque de código paralelo`<br>`end` |
| Aplicar f a todos los elementos en la colección coll | `pmap(f, coll)`                   |

Los workers son también llamados procesos concurrentes/en paralelo.

Los módulos con capacidad de proceso en paralelo están mejor divididos
en un archivo de funciones que contiene todas las funciones y variables
que necesitan los workers, y un archivo driver que gestiona el procesamiento
de los datos. El archivo driver obviamente ha de importar el archivo de funciones.

Un ejemplo de función reductora para un contador de palabras no trivial es el proporcionado por
[Adam DeConinck](https://blog.ajdecon.org/parallel-word-count-with-julia-an-interesting).
