想要类似 `dplyr` 的工具，请使用 [DataFramesMeta.jl.](https://github.com/JuliaStats/DataFramesMeta.jl)

|                            |                                                 |
| -------------------------- | ----------------------------------------------- |
| 读取 Stata, SPSS, 等文件    | `using StatFiles`                               |
| <a class="tooltip" href="#">描述(describe)<span>类似于 R 中的 `summary(df)`。</span></a> data frame | `describe(df)` |
| 得到 `col` 列的向量         | `v = df[:col]`                                  |
| 按 `col` 排序              | `sort!(df, [:col])`                              |
| <a class="tooltip" href="#">分类(Categorical)<span>类似于 R 中的 `df$col = as.factor(df$col)`。</span> `col` | `categorical!(df, [:col])` |
| 列出 `col` 的级别          | `levels(df[:col])`                               |
| 所有满足 `col==val` 的结果  | `df[df[:col] .== val, :]`                       |
| 从宽格式转换为长格式        | `stack(df, [1:n; ])`<br>`stack(df, [:col1, :col2, ...]`<br>`melt(df, [:col1, :col2])` |
| 从长格式转换为宽格式        | `unstack(df, :id, :val)`                         |
| 让表格可以有空值 `Nullable` | `allowmissing!(df)` 或 `allowmissing!(df, :col)` |
| 在行上迭代                 | `for r in eachrow(df)`<br>`    # 干点啥`<br>`    # r 是带属性的行名`<br>`end` |
| 在列上迭代                 | `for c in eachcol(df)`<br>`    # 干点啥`<br>`    # c 是列名和列向量的元组`<br>`end` |
| 将函数应用到组              | `by(df, :group_col, func)`                      |
| 查询                       | `using Query`<br>`query = @from r in df begin`<br>`    @where r.col1 > 40`<br>`    @select {new_name=r.col1, r.col2}`<br>`    @collect DataFrame # 默认的迭代器`<br>`end` |