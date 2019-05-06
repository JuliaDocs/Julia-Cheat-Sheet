([訳注] R の) `dplyr` に似たツールについては，[DataFramesMeta.jl.](https://github.com/JuliaStats/DataFramesMeta.jl) を見てください．

|                                  |                                           |
| -------------------------------- | ----------------------------------------- |
| Stata, SPSS, などのファイルを読むには      | `StatFiles` Package                       |
| dataframeの<a class="tooltip" href="#">概要を得る<span>R の `summary(df)` に相当</span></a>  | `describe(df)` |
| 列 `col` のベクトルを作る  | `v = df[:col]`                            |
| 列 `col` に関して整列(ソート)する         | `sort!(df, [:col])`                       |
| 列 `col` を<a class="tooltip" href="#">categoricalする<span>R の `df$col = as.factor(df$col)` に相当</span></a> | `categorical!(df, [:col])` |
| `col` の level を列挙する    | `levels(df[:col])`                        |
| `col` の列の値が `val` と等しいデータを抜き出す | `df[df[:col] .== val, :]`                 |
| wide形式からlong形式に変換する | `stack(df, [1:n; ])`<br>`stack(df, [:col1, :col2, ...]`<br>`melt(df, [:col1, :col2]) [` |
| long形式からwide形式に変換する | `unstack(df, :id, :val)`                  |
| `Nullable` を許すように，列の型を変換する    | `allowmissing!(df)` or `allowmissing!(df, :col)` |
| 列に沿って繰り返す                  | `for r in eachrow(df)`<br>`    # do stuff.`<br>`    # r is Struct with fields of col names.`<br>`end` |
| 行に沿って繰り返す                | `for c in eachcol(df)`<br>`    # do stuff.`<br>`    # c is tuple with name, then vector`<br>`end` |
| :groups_col でグループ化してから，関数 func を適用する | `by(df, :group_col, func)`                |
| クエリ (Query)                   | `using Query`<br>`query = @from r in df begin`<br>`    @where r.col1 > 40`<br>`    @select {new_name=r.col1, r.col2}`<br>`    @collect DataFrame # Default: iterator`<br>`end` |
