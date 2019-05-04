擬似乱数関数の多くは `using Random` が必要です。

|                                  |                                                               |
| -------------------------------- | ------------------------------------------------------------- |
| 乱数の種を設定する             | `seed!(seed)`                                                 |
| 一様乱数，正規乱数  | `rand()   # uniform [0,1)`<br>`randn()  # normal (-Inf, Inf)` |
| それ以外の分布の乱数  | `using Distributions`<br>`my_dist = Bernoulli(0.2) # For example`<br>`rand(my_dist)` |
| 包含確率 p の下で，A の要素を無作為抽出する | `randsubseq(A, p)`               |
| A の要素の順番をランダムにする | `shuffle(A)`                                                  |
