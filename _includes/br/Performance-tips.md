- Escreva
  [type-stable](https://www.johnmyleswhite.com/notebook/2013/12/06/writing-type-stable-code-in-julia)
  código.
- De fato, use tipos imutáveis sempre que possível.
- Use `sizehint` para grandes arrays.
- Libere memória de grandes arrays com `arr = nothing`.
- Acesse arrays a partir das colunas, pois arrays multidimensionais são armazenados em ordem da coluna principal.
- Pré-alocar estruturas de dados resultantes.
- Desabilite o coletor de lixo em aplicações em tempo real: `disable_gc ()`.
- Evite o operador splat (`...`) para argumentos de palavras-chave.
- Use APIs mutantes (isto é, funções com `!` para evitar cópiar estruturas de dados.
- Use operações de matriz (elemento a elemento) em vez de compreensões da lista.
- Evite 'try`-`catch` em loops (com computação intensiva).
- Evite `Any` em coleções.
- Evite tipos abstratos em coleções.
- Evite interpolação de string em I/O.
- [Vectorizing](https://www.johnmyleswhite.com/notebook/2013/12/22/the-relationship-between-vectorized-and-devectorized-code "https://www.johnmyleswhite.com/notebook/2013/12/22/the-relationship-between-vectorized-and-devectorized-code")
  não melhora a velocidade (ao contrário de R, MATLAB ou Python).
- Evite `eval` em tempo de execução..