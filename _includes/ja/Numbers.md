|                                    |                                                                    |
| ---------------------------------- | ------------------------------------------------------------------ |
| 整数型         | `IntN` and `UIntN`, with `N ∈ {8, 16, 32, 64, 128}`, `BigInt`      |
| 浮動小数点型     | `FloatN` with `N ∈ {16, 32, 64}`<br>`BigFloat`                     |
| 型 type で表される最も小さい数、最も大きい数 | `typemin(Int8)`<br>`typemax(Int64)`                                |
| 複素数型                | `Complex{T}`                                                       |
| 虚数単位              | `im`                                                               |
| 計算機イプシロン      | `eps() # same as eps(Float64)`                                     |
| 丸める                    | `round()       # floating-point`<br>`round(Int, x) # integer`      |
| 型を変換する                | `convert(TypeName, val)  # attempt/error`<br>`typename(val)           # calls convert` |
| 全域の定数                | `pi # 3.1415...`<br>`π  # 3.1415...`<br>`im # real(im * im) == -1` |
| その他の定数        | `using Base.MathConstants`                                     |

Juliaは、桁あふれを自動的に検査しません。
整数の桁あふれを検査するには、[SaferIntegers](https://github.com/JeffreySarnoff/SaferIntegers.jl)パッケージを使ってください‥
