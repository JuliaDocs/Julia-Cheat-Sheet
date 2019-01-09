For `dplyr`-like tools, see
[DataFramesMeta.jl.](https://github.com/JuliaStats/DataFramesMeta.jl)

|                                  |                                           |
| -------------------------------- | ----------------------------------------- |
| Read Stata, SPSS, etc.           | `StatFiles` Package                       |
| <a class="tooltip" href="#">Describe<span>Similar to `summary(df)` in R.</span></a> data frame | `describe(df)` |
| Make vector of column `col`      | `v = df[:col]`                            |
| Sort by `col`                    | `sort!(df, [:col])`                       |
| <a class="tooltip" href="#">Categorical<span>Similar to `df$col = as.factor(df$col)` in R.</span> `col` | `categorical!(df, [:col])` |
| List `col` levels                | `levels(df[:col])`                        |
| All observations with `col==val` | `df[df[:col] .== val, :]`                 |
| Reshape from wide to long format | `stack(df, [1:n; ])`<br>`stack(df, [:col1, :col2, ...]`<br>`melt(df, [:col1, :col2]) [` |
| Reshape from long to wide format | `unstack(df, :id, :val)`                  |
| Make `Nullable`                  | `allowmissing!(df)` or `allowmissing!(df, :col)` |
| Loop over Rows                   | `for r in eachrow(df)`<br>`    # do stuff.`<br>`    # r is Struct with fields of col names.`<br>`end` |
| Loop over Columns                | `for c in eachcol(df)`<br>`    # do stuff.`<br>`    # c is tuple with name, then vector`<br>`end` |
| Apply func to groups             | `by(df, :group_col, func)`                |
| Query                            | `using Query`<br>`query = @from r in df begin`<br>`    @where r.col1 > 40`<br>`    @select {new_name=r.col1, r.col2}`<br>`    @collect DataFrame # Default: iterator`<br>`end` |
