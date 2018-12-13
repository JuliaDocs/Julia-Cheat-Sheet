
| ------------------------------------------ | ---------------------------------- |
| 将 f 应用到 Collection coll 中的每一个元素上 | `map(f, coll)` 或<br>`map(coll) do elem`<br>`    # 处理 elem`<br>`    # 必须有返回值`<br>`end` |
| 滤出 coll 中使 f 为真的每一个元素            | `filter(f, coll)`                  |
| 列表推导                                   | `arr = [f(elem) for elem in coll]` |
