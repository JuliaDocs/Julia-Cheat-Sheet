Julia é homoicônico: Programas são representados como estruturas de dados
da própria linguaguem. De fato, tudo é uma expressão `Expr`.

Símbolos são <a class="tooltip" href="#">sequências de caracteres internas <span> 
Apenas uma cópia de cada cadeia de caracteres (imutável) distinta é armazenada.
</span></a> prefixadas com dois pontos.
Símbolos são mais eficientes e são tipicamente utilizados como identificadores,
chaves (em dicionários), ou colunas em _data frames_. Símbolos não podem ser concatenados.

Citação `:( ... )` ou `quote ... end` cria uma expressão, como 
<a class="tooltip" href="#">`parse(str)` <span> Essa forma é provavelmente a mais familiar
às pessoas com conhecimentos em SQL dinâmico. A função `parse` é similiar à declaração
`EXECUTE IMMEDIATE` da Oracle e da PostgreSQL ou do procedimento `sp_executesql()` do SQL _server_·</span></a>
e `Expr(:call, ...)`.

```
x = 1
line = "1 + $x"      # algum código
expr = parse(line)   # Cria um objeto de expressão (Expr)
typeof(expr) == Expr # Verdadeiro
dump(expr)           # Gera uma árvore de sintaxes abstratas
eval(expr) == 2      # Avalia um objeto Expr se é verdadeiro
```
