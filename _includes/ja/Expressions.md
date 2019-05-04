Julia は同図像性を持ちます。すなわち、プログラムは　Julia言語自体のデータ構造として表されます。実際、すべてが式 `Expr` です。

Symbols are <a class="tooltip" href="#">interned strings <span> Only one copy of each distinct
(immutable) string value is stored. </span></a> prefixed with a colon.
Symbols are more efficient and they are typically used as identifiers,
keys (in dictionaries), or columns in data frames. Symbols cannot be
concatenated.

シンボルは、<a class="tooltip" href="#">インターン化された文字列<span>
それぞれ異なる(イミュータブルな, 変更不能な)文字列につき、ただ一つの文字列だけが保存されることをいいます。</span></a>で、名前の先頭にコロンが付いています。
シンボルはより効率的です。
識別子、(辞書の)キー、またはデータ・フレームの列として、よく使用されます。
シンボル同士を連結できません。


Quoting `:( ... )` or `quote ... end` creates an expression, just
like <a class="tooltip" href="#">`parse(str)` <span> This form is probably most familiar to
people with knowledge of dynamic SQL. The `parse` function is similar
to Oracle"s and PostgreSQL"s `EXECUTE IMMEDIATE` statement or SQL
Server's `sp_executesql()` procedure. </span></a> , and `Expr(:call, ...)`.

クォート化 `:( ... )` あるいは `quote ... end` も、式となります。
<a class="tooltip" href="#">`parse(str)` <span>この形式は、動的SQLの知識があるユーザーに最もなじみがあります。
`parse` 関数は、Oracle や PostgreSQLの `EXECUTE IMMEDIATE`文、あるいは、
SQL サーバの `sp_executesql()` プロシージャと。</span></a> や `Expr(:call, ...)` と同様です。

```
x = 1
line = "1 + $x"      # some code
expr = parse(line)   # make an Expr object
typeof(expr) == Expr # true
dump(expr)           # generate abstract syntax tree
eval(expr) == 2      # evaluate Expr object: true
```
