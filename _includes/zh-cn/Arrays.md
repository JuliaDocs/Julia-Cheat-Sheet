|                                 |                                             |
| ------------------------------- | ------------------------------------------- |
| 声明数组                         | `arr = Float64[]`                           |
| 预分配内存                       | `sizehint!(arr, 10^4)`                      |
| 访问与赋值                       | `arr = Any[1,2]`<br>`arr[1] = "Some text"`  |
| 数组比较                         | `a = [1:10;]`<br>`b = a      # b 指向 a`<br>`a[1] = -99`<br>`a == b     # true` |
| 复制元素(而不是地址)/深拷贝       | `b = copy(a)`<br>`b = deepcopy(a)`          |
| 从 m 到 n 的子数组               | `arr[m:n]`                                  |
| n 个 0.0 填充的数组              | `zeros(n)`                                  |
| n 个 1.0 填充的数组              | `ones(n)`                                   |
| n 个 #undef 填充的数组           | `Vector{Type}(undef,n)`                     |
| n 个从 start 到 stop 的等间距数  | `range(start,stop=stop,length=n)`           |
| n 个随机 Int8 填充的数组         | `rand(Int8, n)`                             |
| 用值 val 填充数组                | `fill!(arr, val)`                           |
| 弹出最后一个元素                 | `pop!(arr)`                                 |
| 弹出第一个元素                   | `popfirst!(a)`                              |
| 将值 val 作为最后一个元素压入数组 | `push!(arr, val)`                           |
| 将值 val 作为第一个元素压入数组   | `pushfirst!(arr, val)`                      |
| 删除指定索引值的元素             | `deleteat!(arr, idx)`                       |
| 数组排序                        | `sort!(arr)`                                |
| 将 b 连接到 a 后                | `append!(a,b)`                              |
| 检查值 val 是否在数组 arr 中     | `in(val, arr)` 或 `val in arr`              |
| 改变维数                        | `reshape(1:6, 3, 2)' == [1 2 3; 4 5 6]`     |
| 转化为字符串，并以 del 分隔      | `join(arr, del)`                            |
