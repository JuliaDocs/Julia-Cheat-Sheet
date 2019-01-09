Many random number functions require `using Random`.

|                                  |                                                               |
| -------------------------------- | ------------------------------------------------------------- |
| Set seed                         | `seed!(seed)`                                                 |
| Random numbers                   | `rand()   # uniform [0,1)`<br>`randn()  # normal (-Inf, Inf)` |
| Random from Other Distribution   | `using Distributions`<br>`my_dist = Bernoulli(0.2) # For example`<br>`rand(my_dist)` |
| Random subsample elements from A with inclusion probability p | `randsubseq(A, p)`               |
| Random permutation elements of A | `shuffle(A)`                                                  |
