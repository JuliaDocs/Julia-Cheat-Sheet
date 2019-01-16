Julia no tiene clases y por tanto no tiene métodos específicos de clase.

Los tipos son como clases sin métodos.

Los tipos abstractos pueden ser subtipados pero no instanciados.

Tipos concretos no pueden ser instanciados.

Por defecto los `struct` s son inmutables.

Los tipos inmutables mejoran el rendimiento y son seguros para hilos de ejecución,
ya que pueden ser compartidos entre diferentes hilos sin necesidad de sincronización

Los objetos formados por un conjunto de tipos se denominan tipos `Union`.

|                          |                                                   |
| ------------------------ | ------------------------------------------------- |
| Anotación de tipo        | `var::TypeName`                                   |
| Declaración de tipo      | `struct Programmer`<br>`    name::String`<br>`    birth_year::UInt16`<br>`    fave_language::AbstractString`<br>`end` |
| Declaración de tipo mutable | replace struct with mutable struct                |
| Alias de tipo            | `const Nerd = Programmer`                         |
| Constructores de tipo    | `methods(TypeName)`                               |
| Instanciado de tipo      | `me = Programmer("Ian", 1984, "Julia")`<br>`me = Nerd("Ian", 1984, "Julia")` |
| Declaración de subtipo   | `abstract type Bird end`<br>`struct Duck <: Bird`<br>`    pond::String`<br>`end` |
| Tipo paramétrico         | `struct Point{T <: Real}`<br>`    x::T`<br>`    y::T`<br>`end`<br><br>`p =Point{Float64}(1,2)`<br> |
| Tipos union              | `Union{Int, String}`                              |
| Traverse type hierarchy  | `supertype(TypeName)` and `subtypes(TypeName)`    |
| Supertipo por defecto         | `Any`                                             |
| Todos los campos          | `fieldnames(TypeName)`                            |
| Tipos de todos los campos     | `TypeName.types`                                  |

Cuando un tipo es definido con un constructor *interno*, los constructores
*externos* por defecto no están disponibles y deben ser definidos manualmente
si fuese necesario. Un constructor interno es mejor usarlo para verificar si
los parámetros están conformes a ciertas condiciones (invarianza). Obviamente, 
estas invariantes pueden ser quebradas accesando y modificando los campos directamente, 
a menos que el tipo esté definido como inmutable. Se puede usar la palabra
clave `new` para crear un objeto del mismo tipo.

Los parámetros de tipos son invariantes, es decir que `Point{Float64} <: Point{Real}` es
falso, a pesar de `Float64 <: Real`.
Los tipos Tuple, por otro lado, son covariantes: `Tuple{Float64} <: Tuple{Real}`.

Se puede obtener la forma de tipos inferidos de la representación interna de Julia
con `code_typed()`. Esto es útil para identificar donde se genera `Any` en vez de
código nativo de tipo específico.
