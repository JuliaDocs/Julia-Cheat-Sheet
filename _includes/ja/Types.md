Juliaにはクラスがなく，クラス固有のメソッドもありません．

型は，メソッドを持たないクラスのようなものです．

抽象(アブストラクト)型は下位型(サブタイプ)を作れますが，インスタンス化はできません．

具象(コンクリート)型は下位型(サブタイプ)を作れません．

既定(デフォルト)では，構造体はイミュータブル(不変，変更不能な)です．

イミュータブルな型は，性能を向上させ，スレッドセーフです．それらが，スレッド間で同期を行わずに共有できるからです．

型の集合の一つをとるようなオブジェクトは，共用(ユニオン)型と呼ばれます．

|                          |                                                   |
| ------------------------ | ------------------------------------------------- |
| 型注釈 (アノテーション) Type annotation          | `var::TypeName`                                   |
| 型宣言        | `struct Programmer`<br>`    name::String`<br>`    birth_year::UInt16`<br>`    fave_language::AbstractString`<br>`end` |
| ミュータブル(変更可能な)型の宣言 | replace struct with mutable struct                |
| 型の別名(エイリアス)         | `const Nerd = Programmer`                         |
| Type constructors        | `methods(TypeName)`                               |
| 型のインスタンス化    | `me = Programmer("Ian", 1984, "Julia")`<br>`me = Nerd("Ian", 1984, "Julia")` |
| 下位型(サブタイプ)の宣言  | `abstract type Bird end`<br>`struct Duck <: Bird`<br>`    pond::String`<br>`end` |
| パラメトリック型     | `struct Point{T <: Real}`<br>`    x::T`<br>`    y::T`<br>`end`<br><br>`p =Point{Float64}(1,2)`<br> |
| 共用(ユニオン)型   | `Union{Int, String}`                              |
| 型の階層を探索する | `supertype(TypeName)` and `subtypes(TypeName)`    |
| 既定の上位型 (スーパータイプ)   | `Any`                                             |
| 全てのフィールド名   | `fieldnames(TypeName)`                            |
| 全てのフィールドの型     | `TypeName.types`                                  |

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
