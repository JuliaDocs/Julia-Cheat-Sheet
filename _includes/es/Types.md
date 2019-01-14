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
| Type annotation          | `var::TypeName`                                   |
| Type declaration         | `struct Programmer`<br>`    name::String`<br>`    birth_year::UInt16`<br>`    fave_language::AbstractString`<br>`end` |
| Declaración de tipo mutable | replace struct with mutable struct                |
| Alias de tipo               | `const Nerd = Programmer`                         |
| Constructores de tipo        | `methods(TypeName)`                               |
| Instanciado de tipo       | `me = Programmer("Ian", 1984, "Julia")`<br>`me = Nerd("Ian", 1984, "Julia")` |
| Declaración de subtipo      | `abstract type Bird end`<br>`struct Duck <: Bird`<br>`    pond::String`<br>`end` |
| Tipo Paramétrico         | `struct Point{T <: Real}`<br>`    x::T`<br>`    y::T`<br>`end`<br><br>`p =Point{Float64}(1,2)`<br> |
| Tipos union              | `Union{Int, String}`                              |
| Traverse type hierarchy  | `supertype(TypeName)` and `subtypes(TypeName)`    |
| Default supertype        | `Any`                                             |
| All fields               | `fieldnames(TypeName)`                            |
| All field types          | `TypeName.types`                                  |

When a type is defined with an *inner* constructor, the default *outer*
constructors are not available and have to be defined manually if need
be. An inner constructor is best used to check whether the parameters
conform to certain (invariance) conditions. Obviously, these invariants
can be violated by accessing and modifying the fields directly, unless
the type is defined as immutable. The `new` keyword may be used to
create an object of the same type.

Type parameters are invariant, which means that `Point{Float64} <: Point{Real}` is
false, even though `Float64 <: Real`.
Tuple types, on the other hand, are covariant: `Tuple{Float64} <: Tuple{Real}`.

The type-inferred form of Julia's internal representation can be found
with `code_typed()`. This is useful to identify where `Any` rather
than type-specific native code is generated.
