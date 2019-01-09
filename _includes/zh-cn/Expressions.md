Julia 具有同像性：程序被表示为语言本身的数据结构。
实际上 Julia 语言里的任何东西都是一个表达式 `Expr`。

符号(Symbols)是<a class="tooltip" href="#">受限的字符串
<span>不同的(不可变)字符串只存在一个副本。</span></a>，以冒号 `:` 为前缀。
相对于其他类型来说，符号效率更高。它也经常用作标识符、字典的键或者数据表里的列名。
符号不能进行拼接。

使用引用 `:( ... )` 或块引用 `quote ... end` 可以创建一个表达式，就像
<a class="tooltip" href="#">`parse(str)`<span> 
了解动态 SQL 的人可能会熟悉这种形式。
这里的 `parse` 函数类似于 Oracle 和 PostgreSQL 的 `EXECUTE IMMEDIATE` 语句，
或 SQL
Server 的 `sp_executesql()` 过程。</span></a>，和 `Expr(:call, ...)`。

```julia
x = 1
line = "1 + $x"         # 一些代码
expr = Meta.parse(line) # 生成一个 Expr 对象
typeof(expr) == Expr    # true
dump(expr)              # 打印生成抽象语法(AST)
eval(expr) == 2         # 对 Expr 对象求值: true
```
