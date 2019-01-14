Julia es homoicónico: los programas son representados como
estructuras de datos del propio lenguaje. De hecho, todo es
una expresion `Expr`.

Los símbolos son <a class="tooltip" href="#">cadenas de texto internas <span>
Sólo se almacena una copia de cada cadena de texto (inmutable).</span></a> 
prefijadas con dos puntos. Los símbolos son más eficientes y son habitualmente
usados como identificadores, claves (en diccionarios), o columnas en data frames.
Los símbolos no pueden concatenarse.

Las citas `:( ... )` o `quote ... end` crean una expresión, igual a 
<a class="tooltip" href="#">`parse(str)` <span> Esta forma es probablemente
más familiar para personas con conocimiento de SQL dinámico. La función `parse` es
similar a la sentencia SQL `EXECUTE IMMEDIATE` de Oracle y PostgreSQL o el procedimiento
de servidor SQL `sp_executesql()`. </span></a> , y `Expr(:call, ...)`.

```
x = 1
line = "1 + $x"      # bloque de código
expr = parse(line)   # crear un objeto Expr
typeof(expr) == Expr # verdadero
dump(expr)           # generar arbol de sintaxis abstracta
eval(expr) == 2      # evaluar el objeto Expr: verdadero
```
