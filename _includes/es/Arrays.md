|                                   |                                             |
| --------------------------------- | ------------------------------------------- |
| Declaración                       | `arr = Float64[]`                           |
| Preasignación de memoria                    | `sizehint!(arr, 10^4)`                      |
| Acceso y asignación               | `arr = Any[1,2]`<br>`arr[1] = "Some text"`  |
| Comparación | `a = [1:10;]`<br>`b = a      # b points to a`<br>`a[1] = -99`<br>`a == b     # true` |
| Copiar elementos (no la dirección)       | `b = copy(a)`<br>`b = deepcopy(a)`          |
| Seleccionar submatriz de m hasta n       | `arr[m:n]`                                  |
| Matriz de n-elementos con 0.0s         | `zeros(n)`                                  |
| Matriz de n-elementos con 1.0s         | `ones(n)`                                   |
| Matriz de n-elementos #undefs      | `Vector{Type}(undef,n)`                     |
| n números separados igualmente desde start hasta stop | `range(start,stop=stop,length=n)` |
| Matriz con n elementos Int8 aleatorios | `rand(Int8, n)`                             |
| Llenar la matriz con el valor val               | `fill!(arr, val)`                           |
| Pop del último elemento                 | `pop!(arr)`                                 |
| Pop del primer elemento                 | `popfirst!(a)`                              |
| Push el valor val como último elemento          | `push!(arr, val)`                           |
| Push el valor val como primer elemento         | `pushfirst!(arr, val)`                      |
| Eliminar elelemto con índice idx       | `deleteat!(arr, idx)`                       |
| Ordenar                              | `sort!(arr)`                                |
| Añadir b al final de a                   | `append!(a,b)`                              |
| Verificar si arr contiene val      | `in(val, arr) or val in arr`                |
| Producto escalar                    | `dot(a, b) == sum(a .* b)`                  |
| Cambiar las dimensiones (si posible)   | `reshape(1:6, 3, 2)' == [1 2 3; 4 5 6]`     |
| Matriz a cadena de caracteres (con delimitador del entre elementos) | `join(arr, del)`              |
