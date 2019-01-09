
| ----------------- | ------------------------------------------------------------------ |
| 整数类型           | `IntN` 和 `UIntN`, 且 `N ∈ {8, 16, 32, 64, 128}`, `BigInt`         |
| 浮点类型           | `FloatN` 且 `N ∈ {16, 32, 64}`<br>`BigFloat`                       |
| 类型的最大和最小值  | `typemin(Int8)`<br>`typemax(Int64)`                                |
| 复数类型           | `Complex{T<:Real}`                                                       |
| 虚数单位           | `im`                                                               |
| 机器精度           | `eps() # 等价于 eps(Float64)`                                      |
| 圆整               | `round()       # 浮点数圆整`<br>`round(Int, x) # 整数圆整`          |
| 类型转换           | `convert(TypeName, val) # 尝试进行转换/可能会报错`<br>`TypeName(val) # 调用类型构造器转换` |
| 全局常量           | `pi # 3.1415...`<br>`π  # 3.1415...`<br>`im # real(im * im) == -1` |
| 更多常量           | `using Base.MathConstants`                                         |

Julia 不会自动检测数值溢出。
使用 [SaferIntegers](https://github.com/JeffreySarnoff/SaferIntegers.jl)
包可以得到带溢出检查的整数。
