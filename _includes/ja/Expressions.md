Julia は同図像性を持ちます．すなわち，プログラムは Julia言語自体のデータ構造として表されます．実際，すべてが式 `Expr` です．

シンボルは，先頭にコロン `:` がついた
<a class="tooltip" href="#">インターン化された文字列<span>
それぞれ異なる(イミュータブルな, 変更不能な)文字列につき，ただ一つの文字列だけが保存されることをいいます．</span></a>です．
シンボルは，より効率的で，識別子，(辞書の)キー，あるいは，データ・フレームの列として，よく使用されます．
シンボル同士は連結できません．

クォート化 `:( ... )` あるいは `quote ... end` も，式を作ります．
<a class="tooltip" href="#">`parse(str)`
<span>この形式は，動的SQLの知識があるユーザーに最もなじみがあります．`parse` 関数は，Oracle や PostgreSQLの `EXECUTE IMMEDIATE`文，あるいは，
SQL サーバの `sp_executesql()` プロシージャと同様です．</span></a> と `Expr(:call, ...)` も，同様に式を作ります．

```
x = 1
line = "1 + $x"      # some code
expr = parse(line)   # make an Expr object
typeof(expr) == Expr # true
dump(expr)           # generate abstract syntax tree
eval(expr) == 2      # evaluate Expr object: true
```
