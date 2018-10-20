Muitas funções de números aleatórios requerem `using Random`.

|                                                               |                                                                                      |
| ------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Definir semente                                               | `seed!(seed)`                                                                        |
| Números aleatórios                                            | `rand()   # uniforme [0,1)`<br>`randn()  # normal (-Inf, Inf)`                        |
| Aleatório de outras distribuições                             | `using Distributions`<br>`minha_dist = Bernoulli(0.2) # Por exemplo`<br>`rand(minha_dist)` |
| Subamostra aleatória de elementos de A com probabilidade p de inclusão | `randsubseq(A, p)`                                                                   |
| Permutação aleatória de elementos de A                              | `shuffle(A)`                                                                         |
