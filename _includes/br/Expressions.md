Julia é homoicônico: Programas são representados como estruturas de dados
da própria linguaguem. De fato, tudo é uma expressão `Expr`.

Símbolos são <a class="tooltip" href="#">sequências internas <span> 
Apenas uma cópia de cada valor de sequência distinta é armazenado.
  (Imutável).</span></a> preficaso com dois pontos.
  
Símbolos são mais eficientes e são tipicamente utilizado como identificadores,
chaves (em dicionários), ou colunas em `data frames`. Símbolos não podem ser concatenados.
Citação `:( ... )` ou `quote ... end` cria uma expressão, como 
<a class="tooltip" href="#">`parse(str)` <span> Essa forma é provávelmente a mais familiar
  a pessoas com conhecimento de Dinâmicas em SQL. A função `parse` é similiar à declaração
  `EXECUTE IMMEDIATE` da Oracle e da PostgreSQL ou do procedimento `sp_executesql()` do servidor SQL·</span></a>
  e `Expr(:call, ...)`.

```
x = 1
line = "1 + $x"      # algum código
expr = parse(line)   # Cria um objeto de expressão (Expr)
typeof(expr) == Expr # Verdadeiro
dump(expr)           # Gera uma árvore de sintaxes abstratas
eval(expr) == 2      # Avalia um objeto Expr se é verdadeiro
```
