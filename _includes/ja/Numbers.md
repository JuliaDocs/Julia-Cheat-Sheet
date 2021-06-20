|                                    |                                                                    |
| ---------------------------------- | ------------------------------------------------------------------ |
| 整数型         | `IntN` および `UIntN` ここで `N ∈ {8, 16, 32, 64, 128}`, `BigInt`      |
| 浮動小数点型     | `FloatN` ここで `N ∈ {16, 32, 64}`<br>`BigFloat`                     |
| 型で表される最も小さい数，最も大きい数 | `typemin(Int8)`<br>`typemax(Int64)`                                |
| 複素数型                | `Complex{T}`                                                       |
| 虚数単位              | `im`                                                               |
| 計算機イプシロン      | `eps() # eps(Float64)と同じ `                                     |
| 丸める                    | `round()       # 結果は浮動小数点数`<br>`round(Int, x) # 結果は整数`      |
| 型を変換する                | `convert(型名, val)  # 型変換を試みる`<br>`型名(val)           # convertを呼ぶ` |
| 全域の定数                | `pi # 3.1415...`<br>`π  # 3.1415...`<br>`im # real(im * im) == -1` |
| その他の定数        | `using Base.MathConstants`                                     |

Juliaは，桁あふれを自動的に検査しません．
整数の桁あふれを検査するには，[SaferIntegers](https://github.com/JeffreySarnoff/SaferIntegers.jl)パッケージを使ってください‥
