Ferramentas de computação paralela estão disponíveis na biblioteca padrão `Distributed`

|                                                                                                                                                              |                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| Iniciar RELP com N ``workers``                                                                                                                               | `julia -p N`                                                                                      |
| Número de ``workers`` disponíveis                                                                                                                            | `nprocs()`                                                                                        |
| Adicionar N ``workers``                                                                                                                                      | `addprocs(N)`                                                                                     |
| Mostrar os IDs de todos os `workers`                                                                                                                         | `for pid in `workers`()`<br>`println(pid)`<br>`end`                                                 |
| Mostrar os IDs dos `workers` em execução                                                                                                                     | `myid()`                                                                                          |
| Remover `worker`                                                                                                                                             | `rmprocs(pid)`                                                                                    |
| Executar f com argumentos args no PID                                                                                                                        | `r = remotecall(f, pid, args...)`<br>`# or:`<br>`r = @spawnat pid f(args)`<br>`...`<br>`fetch(r)` |
| Executar f com argumentos no PID (mais eficiente)                                                                                                            | `remotecall_fetch(f, pid, args...)`                                                               |
| Executar f com argumentos args em qualquer `worker`                                                                                                          | `r = @spawn f(args) ... fetch(r)`                                                                 |
| Executar f com argumentos args em todos os `workers`                                                                                                         | `r = [@spawnat w f(args) for w in `workers`()] ... fetch(r)`                                        |
| Fazer expr disponível para todos os `workers`                                                                                                                | `@everywhere expr`                                                                                |
| Ciclo paralelo com a função red, que é uma <a class="tooltip" href="#">reducer<span>Uma função reducer combina os resultados de diferentes (e independentes) workers.</span></a>| `sum = @distributed (red) for i in 1:10^6`<br>`# faça coisas paralelas`<br>`end`                       |
| Aplicar f para todos os elementos da coleção coll                                                                                                             | `pmap(f, coll)`                                                                                   |

`workers` também são conhecidos como processos paralelos ou concorrentes.

Modulos com capacidades de computação paralela são melhor
divididos em um arquivo de funções que contém todas as funções
e variáveis necessárias para todos `workers`, e um arquivo principal
que trata do processamento de dados. O arquivo principal obviamente
precisa importar o arquivo de funções.

Um exemplo não trivial de uma função `reducer` é provido por
[Adam DeConinck](https://blog.ajdecon.org/parallel-word-count-with-julia-an-interesting).
