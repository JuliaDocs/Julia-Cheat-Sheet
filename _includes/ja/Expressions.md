Julia is homoiconic: programs are represented as data structures of the
language itself. In fact, everything is an expression `Expr`.

Symbols are <a class="tooltip" href="#">interned strings <span> Only one copy of each distinct
(immutable) string value is stored. </span></a> prefixed with a colon.
Symbols are more efficient and they are typically used as identifiers,
keys (in dictionaries), or columns in data frames. Symbols cannot be
concatenated.

Quoting `:( ... )` or `quote ... end` creates an expression, just
like <a class="tooltip" href="#">`parse(str)` <span> This form is probably most familiar to
people with knowledge of dynamic SQL. The `parse` function is similar
to Oracle"s and PostgreSQL"s `EXECUTE IMMEDIATE` statement or SQL
Server's `sp_executesql()` procedure. </span></a> , and `Expr(:call, ...)`.

```
x = 1
line = "1 + $x"      # some code
expr = parse(line)   # make an Expr object
typeof(expr) == Expr # true
dump(expr)           # generate abstract syntax tree
eval(expr) == 2      # evaluate Expr object: true
```
