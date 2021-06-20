Juliaにはクラスがなく，クラス固有のメソッドもありません．

型は，メソッドを持たないクラスのようなものです．

抽象（アブストラクト）型は下位型（サブタイプ）を作れますが，インスタンス化はできません．

具象（コンクリート）型は下位型（サブタイプ）を作れません．

既定（デフォルト）では，構造体はイミュータブル（不変，変更不能）です．

イミュータブルな型は，性能を向上でき，スレッド間で同期を行わずに共有できるので，スレッドセーフです．

型の集合の一つをとるようなオブジェクトは，共用（ユニオン）型と呼ばれます．

|                          |                                                   |
| ------------------------ | ------------------------------------------------- |
| 型注釈（アノテーション）   | `var::TypeName`                                   |
| 型宣言        | `struct Programmer`<br>`    name::String`<br>`    birth_year::UInt16`<br>`    fave_language::AbstractString`<br>`end` |
| ミュータブル（変更可能な）型の宣言 | `struct` を `mutable struct` に置き換える                |
| 型の別名（エイリアス）         | `const Nerd = Programmer`                         |
| Type constructors        | `methods(TypeName)`                               |
| 型のインスタンス化    | `me = Programmer("Ian", 1984, "Julia")`<br>`me = Nerd("Ian", 1984, "Julia")` |
| 下位型（サブタイプ）の宣言  | `abstract type Bird end`<br>`struct Duck <: Bird`<br>`    pond::String`<br>`end` |
| パラメトリック型     | `struct Point{T <: Real}`<br>`    x::T`<br>`    y::T`<br>`end`<br><br>`p =Point{Float64}(1,2)`<br> |
| 共用（ユニオン）型   | `Union{Int, String}`                              |
| 型の階層を探索する | `supertype(TypeName)` and `subtypes(TypeName)`    |
| 既定の上位型（スーパータイプ）   | `Any`                                             |
| 全てのフィールド名   | `fieldnames(TypeName)`                            |
| 全てのフィールドの型     | `TypeName.types`                                  |

型宣言の内部で*内部*コンストラクタを定義すると，
既定の*外部*コンストラクタは使用できません
（必要に応じて手動で定義する必要があります）．
内部コンストラクタの利用は，
型引数（型パラメータ）が invariant（不変性）か否かを検査する場合に
適しています．なぜなら，
型をイミュータブル（不変，変更不能）として定義しない限り，
型のフィールドに直接アクセスして変更しようとすると，この不変性が破られるからです．
`new`キーワードは，同じ型のオブジェクトを作成するために用いられます．

ここで，型引数が invariant（不変）であるとは，
（`Float64 <: Real` にもかかわらず）
`Point{Float64} <: Point{Real}` が成り立たないことを意味します．

型推論がなされた Juliaの内部表現は `code_typed()` で見ることができます．
これは，特定の型向けのネイティブコードではなく，
`Any`型向けのコードが，どこで生成させたのかを突き止めるのに役に立ちます．
