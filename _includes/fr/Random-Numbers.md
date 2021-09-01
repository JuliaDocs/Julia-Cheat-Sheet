Plusieurs fonctions de nombre aléatoire requièrent `using Random`.

|                                  |                                                               |
| -------------------------------- | ------------------------------------------------------------- |
| Définir la graine                | `seed!(seed)`                                                 |
| Nombres aléatoires               | `rand()   # uniform [0,1)`<br>`randn()  # normal (-Inf, Inf)` |
| Aléatoire depuis une autre distribution | `using Distributions`<br>`my_dist = Bernoulli(0.2) # For example`<br>`rand(my_dist)` |
| Sous-échantillon aléatoire dans A avec une probabilité d'inclusion p | `randsubseq(A, p)`               |
| Permutation aléatoire d'éléments de A | `shuffle(A)`                                                  |
