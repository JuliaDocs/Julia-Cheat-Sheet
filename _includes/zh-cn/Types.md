Julia has no classes and thus no class-specific methods.

Types are like classes without methods.

Abstract types can be subtyped but not instantiated.

Concrete types cannot be subtyped.

By default, `struct` s are immutable.

Immutable types enhance performance and are thread safe, as they can be
shared among threads without the need for synchronization.

Objects that may be one of a set of types are called `Union` types.

|                          |                                                                                                                          |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| Type annotation          | `var::TypeName`                                                                                                          |
| Type declaration         | `struct Programmer`<br>`name::String`<br>`birth_year::UInt16`<br>`fave_language::AbstractString`<br>`end`                |
| Mutable type declaration | replace struct with mutable struct                                                                                       |
| Type alias               | `const Nerd = Programmer`                                                                                                |
| Type constructors        | `methods(TypeName)`                                                                                                      |
| Type instantiation       | `me = Programmer("Ian", 1984, "Julia")`<br>`me = Nerd("Ian", 1984, "Julia")`                                             |
| Subtype declaration      | `abstract type Bird end`<br>`struct Duck <: Bird`<br>`pond::String`<br>`end`                                             |
| Parametric type          | `struct Point{T <: Real}`<br>`x::T`<br>`y::T`<br>`end`<br><br>`p =Point{Float64}(1,2)`<br>                               |
| Union types              | `Union{Int, String}`                                                                                                     |
| Traverse type hierarchy  | `supertype(TypeName)` and `subtypes(TypeName)`                                                                           |
| Default supertype        | `Any`                                                                                                                    |
| All fields               | `fieldnames(TypeName)`                                                                                                   |
| All field types          | `TypeName.types`                                                                                                         |

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
