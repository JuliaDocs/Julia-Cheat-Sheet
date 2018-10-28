Julia não tem classes e, portanto, não há métodos específicos de classe.

Tipos são como classes sem métodos.

Os tipos abstratos podem ser subtipados, mas não instanciados.

Tipos concretos não podem ser subtipados.

Por padrão, `struct` s são imutáveis.

Os tipos imutáveis melhoram o desempenho e são seguros para threads, já que podem ser
compartilhada entre threads sem a necessidade de sincronização.

Objetos que podem ser de um conjunto de tipos são chamados de tipos `Union`.

|                          |                                                                                                                          |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| Anotação de tipo                     | `var::TypeName`                                                                                                          |
| Declaração de tipo                   | `struct Programmer`<br>`name::String`<br>`birth_year::UInt16`<br>`fave_language::AbstractString`<br>`end`                |
| Declaração de tipo mutável           | substituir `struct` por `mutable struct`                                                                                       |
| Pseudônimo de tipo                   | `const Nerd = Programmer`                                                                                                |
| Construtores de tipo                 | `methods(TypeName)`                                                                                                      |
| Instanciação de tipo                 | `me = Programmer("Ian", 1984, "Julia")`<br>`me = Nerd("Ian", 1984, "Julia")`                                             |
| Declaração de subtipo                | `abstract type Programmer`<br>`name::AbstractString`<br>`birth_year::UInt16`<br>`fave_language::AbstractString`<br>`end` |
| Tipo paramétrico                     | `struct Point{T <: Real}`<br>`x::T`<br>`y::T`<br>`end`<br><br>`p =Point{Float64}(1,2)`<br>                               |
| Tipos `Union`                        | `Union{Int, String}`                                                                                                     |
| Hierarquia de tipo transversal       | `supertype(TypeName)` e `subtypes(TypeName)`                                                                           |
| Supertipo padrão                     | `Any`                                                                                                                    |
| Todos os campos                      | `fieldnames(TypeName)`                                                                                                   |
| Todos os tipos de campo              | `TypeName.types`                                                                                                         |

Quando um tipo é definido com um construtor *interno*, os construtores padrões *externos* 
não estão disponíveis e devem ser definidos manualmente, se necessário.
Um construtor interno é melhor usado para verificar se os parâmetros 
estão em conformidade com certas condições (invariância). Obviamente, essas invariantes 
podem ser violadas acessando e modificando os campos diretamente, a menos 
que o tipo seja definido como imutável. A palavra-reservada `new` pode ser usada para 
criar um objeto do mesmo tipo.

Os parâmetros de tipo são invariantes, que significa que `Point{Float64} <: Point{Real}` é 
falso, embora `Float64 <: Real`.
Tipos de tupla, por outro lado, são covariantes: `Tuple{Float64} <: Tuple{Real}`.

A forma inferida de tipo da representação interna de Julia's pode ser encontrada
com `code_typed()`. Isso é útil para identificar onde é gerado o código nativo `Any` e não o tipo específico.
