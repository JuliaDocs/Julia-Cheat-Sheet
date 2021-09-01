Pour des outils similaires à `dplyr`, voir
[DataFramesMeta.jl.](https://github.com/JuliaStats/DataFramesMeta.jl)

|                                  |                                           |
| -------------------------------- | ----------------------------------------- |
| Lire Stata, SPSS, etc.           | `StatFiles` Package                       |
| <a class="tooltip" href="#">Décrire<span>Similaire à `summary(df)` dans R.</span></a> un *data frame* | `describe(df)` |
| Obtenir la colonne `col` en vecteur     | `v = df[:col]`                            |
| Sort by `col`                    | `sort!(df, [:col])`                       |
| `col` <a class="tooltip" href="#">Catégorique<span>Similaire à `df$col = as.factor(df$col)` dans R.</span>  | `categorical!(df, [:col])` |
| Lister les niveaux de `col`      | `levels(df[:col])`                        |
| Toutes observations telles que `col==val` | `df[df[:col] .== val, :]`                 |
| Restructurer d'un format large à long | `stack(df, [1:n; ])`<br>`stack(df, [:col1, :col2, ...])`<br>`melt(df, [:col1, :col2])` |
| Restructurer d'un format long à large | `unstack(df, :id, :val)`                  |
| Rendre `Nullable`                | `allowmissing!(df)` or `allowmissing!(df, :col)` |
| Itérer par ligne                 | `for r in eachrow(df)`<br>`    # do stuff.`<br>`    # r is Struct with fields of col names.`<br>`end` |
| Itérer par colonne               | `for c in eachcol(df)`<br>`    # do stuff.`<br>`    # c is tuple with name, then vector`<br>`end` |
| Appliquer `func` par groupes     | `by(df, :group_col, func)`                |
| Interroger                       | `using Query`<br>`query = @from r in df begin`<br>`    @where r.col1 > 40`<br>`    @select {new_name=r.col1, r.col2}`<br>`    @collect DataFrame # Default: iterator`<br>`end` |
