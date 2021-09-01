Julia est homoiconique: les programmes sont représentés comme des structures de données 
du langage lui-même. De fait, tout est une expression `Expr`.

Les symboles sont <a class="tooltip" href="#">des chaînes internes <span> Une seule copie
 de chaque valeur de chaîne distincte (immuable) est stockée. </span></a> préfixés par deux points `:`.
Les symboles sont plus efficaces et ils sont typiquement utilisés comme identifiants, clés 
(dans les dictionnaires), ou colonnes dans les tableaux. Les symboles ne peuvent pas être concaténés.

Citer `:( ... )` ou `quote ... end` crée une expression, tout comme
<a class="tooltip" href="#">`Meta.parse(str)` <span> Cette forme est probablement 
plus familière aux personnes avec une connaissance du SQL dynamique. La fonction `Meta.parse` 
est similaire à `EXECUTE IMMEDIATE` dans Oracle et PostgreSQL ou la procédure 
`sp_executesql()` dans SQL Server. </span></a> , et `Expr(:call, ...)`.

```
x = 1
line = "1 + $x"         # some code
expr = Meta.parse(line) # make an Expr object
typeof(expr) == Expr    # true
dump(expr)              # generate abstract syntax tree
eval(expr) == 2         # evaluate Expr object: true
```
