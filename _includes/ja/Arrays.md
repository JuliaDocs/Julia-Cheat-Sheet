|                                   |                                             |
| --------------------------------- | ------------------------------------------- |
| 配列の宣言            | `arr = Float64[]`                           |
| メモリ確保の準備                  | `sizehint!(arr, 10^4)`                      |
| (配列要素の)アクセス(読み出し)と代入        | `arr = Any[1,2]`<br>`arr[1] = "Some text"`  |
| 比較 | `a = [1:10;]`<br>`b = a      # b points to a`<br>`a[1] = -99`<br>`a == b     # true` |
| 全ての要素を複製する (not address)       | `b = copy(a)`<br>`b = deepcopy(a)`          |
| インデックス m から n までのサブ配列を選ぶ   | `arr[m:n]`                                  |
| 寸法 n で、要素が全て 0.0 の配列を作る    | `zeros(n)`                                  |
| 寸法 n で、要素が全て 1.0 の配列を作る        | `ones(n)`                                   |
| 寸法 n で、要素が全て #undef の配列を作る    | `Vector{Type}(undef,n)`                     |
| start から stop まで、等間隔の n 個の数字の列を作る | `range(start,stop=stop,length=n)` |
| n 個のInt8 型の乱数からなる配列を作る | `rand(Int8, n)`                             |
| 配列 arr を値 val で満たす   | `fill!(arr, val)`                           |
| 末尾の配列要素をポップする         | `pop!(arr)`                                 |
| 最初の配列要素をポップする                 | `popfirst!(a)`                              |
| val を末尾の要素としてプッシュする  | `push!(arr, val)`                           |
| val を最初の要素としてプッシュする         | `pushfirst!(arr, val)`                      |
| インデックス idx の要素を削除する  | `deleteat!(arr, idx)`                       |
| 整列する ([訳注] 元の配列を変更する)     | `sort!(arr)`                                |
| 配列 a に 配列 b を連結する ([訳注] a は書き換わる)      | `append!(a,b)`                              |
| val が要素として含まれているかを検査する | `in(val, arr) or val in arr`                |
| スカラー積 (内積)    | `dot(a, b) == sum(a .* b)`                  |
| (可能なら)寸法を変える  | `reshape(1:6, 3, 2)' == [1 2 3; 4 5 6]`     |
| 配列を文字列に変える (要素の間にデリミタ del を挿入する | `join(arr, del)`              |
