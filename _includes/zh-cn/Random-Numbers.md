许多随机数函数都需要 `using Random`。

|                               |                                                               |
| ----------------------------- | ------------------------------------------------------------- |
| 设置随机数种子                 | `seed!(seed)`                                                 |
| 产生随机数                     | `rand()   # 均匀分布 [0,1)`<br>`randn()  # 正态分布 (-Inf, Inf)` |
| 产生特定分布的随机数            | `using Distributions`<br>`my_dist = Bernoulli(0.2) # 举例`<br>`rand(my_dist)` |
| 以包含概率 p 从 A 中随机二次取样 | `randsubseq(A, p)`                                            |
| 随机重排 A 中的元素             | `shuffle(A)`                                                  |
