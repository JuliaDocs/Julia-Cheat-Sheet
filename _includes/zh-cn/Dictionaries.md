
|                  |                                                           |
| ---------------- | --------------------------------------------------------- |
| 字典 | `d = Dict(key1 => val1, key2 => val2, ...)`<br>`d = Dict(:key1 => val1, :key2 => val2, ...)` |
| 所有的键 (迭代器) | `keys(d)`                                                 |
| 所有的值 (迭代器) | `values(d)`                                               |
| 按键值对迭代      | `for (k,v) in d`<br>`    println("key: $k, value: $v")`<br>`end` |
| 是否存在键 `:k`   | `haskey(d, :k)`                                           |
| 将键/值复制到数组 | `arr = collect(keys(d))`<br>`arr = [k for (k,v) in d]`     |

字典是可变的。当使用符号(:symbol)作为键时，键不可变。
