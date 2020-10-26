Julia n'a pas de classes, et par conséquent pas de méthodes de classe. Les types
Julia sont similaires à des classes sans méthode.

Les types abstraits peuvent être sous-typés, mais pas instanciés. Les types
concrets ne peuvent être sous-typés.

Par défaut, les `struct`s sont immutables. Les types immutables améliorent la
performance et sont *thread-safe* puisqu'on ne peut accéder à leurs instances
qu'en lecture.

Les types `Union` permettent de représenter un ensemble de types.

|                                                        |                                                                                                                       |
| ------------------------                               | -------------------------------------------------                                                                     |
| Assertion de type, annotation                          | `var::TypeName`                                                                                                       |
| Déclaration de type                                    | `struct Programmer`<br>`    name::String`<br>`    birth_year::UInt16`<br>`    fave_language::AbstractString`<br>`end` |
| Déclaration de type mutable                            | remplacer `struct` par `mutable struct`                                                                               |
| Alias de type                                          | `const Nerd = Programmer`                                                                                             |
| Liste des constructeurs d'un type                      | `methods(TypeName)`                                                                                                   |
| Instanciation d'un type  (construction d'une instance) | `me = Programmer("Ian", 1984, "Julia")`<br>`me = Nerd("Ian", 1984, "Julia")`                                          |
| Déclaration d'un sous-type                             | `abstract type Bird end`<br>`struct Duck <: Bird`<br>`    pond::String`<br>`end`                                      |
| Type paramétrique                                      | `struct Point{T <: Real}`<br>`    x::T`<br>`    y::T`<br>`end`<br><br>`p =Point{Float64}(1,2)`<br>                    |
| Type union                                             | `Union{Int, String}`                                                                                                  |
| Parcours de la hiérarchie de types                     | `supertype(TypeName)` and `subtypes(TypeName)`                                                                        |
| Supertype universel                                    | `Any`                                                                                                                 |
| Liste des champs                                       | `fieldnames(TypeName)`                                                                                                |
| Liste des types des champs                             | `TypeName.types`                                                                                                      |

Lorsqu'une définition de type inclut un constructeur *interne*, les
constructeurs *externes* par défaut ne sont plus disponibles. Ils doivent être
définis manuellement si nécessaire. Un constructeur interne est utile pour
garantir des invariants sur les champs d'un type. (Ces invariants pourront quand
même être enfreints par une modification directe des champs, à moins que le type
soit immutable). Le mot-clé `new` utilisé dans un constructeur interne permet de
créer un objet du type adéquat.

Les paramètres de type sont invariants, c'est à dire que `Point{Float64} <:
Point{Real}` est faux, alors même que `Float64 <: Real`.
En revanche, les `Tuple` sont covariants : `Tuple{Float64} <: Tuple{Real}`.

La représentation interne d'un morceau de code après inférence de types peut
être consultée grâce à `code_typed()`. Ceci est en particulier utile pour
identifier les endroits où des expressions de type `Any` sont manipulées plutôt
que du code natif de type spécifique.
