Julia 没有类，因此也没有类相关的方法。

类型就像是没有方法的类。

抽象类型可以作为子类型，但不能被实例化。

具体的类型不能作为子类型。

`struct` 默认是不可变的。

不可变类型能能改善程序的性能，并且它们是线程安全的，因为它们在跨线程使用时不需要同步。

可能是一组类型之一的对象称为 `Union` (联合)类型。

|              |                                                                              |
| -------------| ---------------------------------------------------------------------------- |
| 类型注释      | `var::TypeName`                                                              |
| 类型声明      | `struct Programmer`<br>`    name::String`<br>`    birth_year::UInt16`<br>`    fave_language::AbstractString`<br>`end` |
| 可变类型声明  | 将 `struct` 替换为 `mutable struct`                                           |
| 类型别名      | `const Nerd = Programmer`                                                    |
| 类型构造器    | `methods(TypeName)`                                                          |
| 类型实例      | `me = Programmer("Ian", 1984, "Julia")`<br>`me = Nerd("Ian", 1984, "Julia")` |
| 子类型声明    | `abstract type Bird end`<br>`struct Duck <: Bird`<br>`    pond::String`<br>`end` |
| 参数化类型    | `struct Point{T <: Real}`<br>`    x::T`<br>`    y::T`<br>`end`<br><br>`p = Point{Float64}(1,2)`<br> |
| 联合类型      | `Union{Int, String}`                                                         |
| 遍历类型层级  | `supertype(TypeName)` 和 `subtypes(TypeName)`                                |
| 默认的超类型  | `Any`                                                                        |
| 所有字段      | `fieldnames(TypeName)`                                                       |
| 所有字段类型  | `TypeName.types`                                                             |

当使用 **内部** 构造器定义类型时，默认的 **外部** 构造器就不能用了，如果你还想用它就需要手工定义一下。
内部构造器非常适合于检查参数是否符合特定的(不变的)条件。
当然，可以通过直接访问并修改这些字段来改变这些不变量，除非类型定义为不可变。
关键字 `new` 可以用于创建相同类型的对象。

类型参数是不可变的，这意味着即使 `Float64 <: Real`，<br>`Point{Float64} <: Point{Real}` 依旧为假
对于元组类型(Tuple)正好相反，它们是协变的(covariant)： `Tuple{Float64} <: Tuple{Real}`

通过 `code_typed()` 函数可以查看 Julia 代码经过类型推断后的内部表示形式(IR)。
这个函数常用来确定本地代码中那些地方出现了 `Any` 类型而不是特定的类型。
