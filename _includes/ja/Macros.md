マクロは，生成されたコード (すなわち，式)をプログラム内に挿入することを可能とします．

|                 |                                                            |
| --------------- | ---------------------------------------------------------- |
| 定義      | `macro macroname(expr)`<br>`    # do stuff`<br>`end`       |
| 使い方        | `macroname(ex1, ex2, ...)` or `@macroname ex1, ex2, ...`   |
| 組み込みのマクロ | `@test x == y    # 値が等しい(正確に)`<br>`@test x ≈ y     # isapprox(x, y) 値がほぼ等しい`<br>`@assert         # assert (unit test)`<br>`@which          # types used`<br>`@time           # time and memory statistics`<br>`@elapsed        # time elapsed`<br>`@allocated      # memory allocated`<br>`@profile        # profile`<br>`@spawn          # run at some worker`<br>`@spawnat        # run at specified worker`<br>`@async          # asynchronous task`<br>`@distributed    # parallel for loop`<br>`@everywhere     # make available to workers` |

*衛生的な* マクロを作るための約束は，以下のとおりです:
- マクロ内では，変数を `local` で宣言する.
- マクロ内で `eval` を呼び出さない．
- 補間された式をエスケープして展開を避ける: `$(esc(expr))`
