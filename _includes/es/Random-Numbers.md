Many random number functions require `using Random`.

|                                           |                                                                   |
| ----------------------------------------- | ----------------------------------------------------------------- |
| Definir la semilla                        | `seed!(seed)`                                                     |
| Números aleatorios                        | `rand()   # uniform [0,1)`<br>`randn()  # normal (-Inf, Inf)`     |
| Aleatorio de otra distribución            | `using Distributions`<br>`my_dist = Bernoulli(0.2) # Por ejemplo`<br>`rand(my_dist)` |
| Submuestra aleatoria de elementos de A con probabilidad de inclusión p | `randsubseq(A, p)`                   |
| Permutación aleatória de elementos de A   | `shuffle(A)`                                                      |
