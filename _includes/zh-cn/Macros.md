宏允许你在程序中自动生成代码（如：表达式）。

|         |                                                            |
| ------- | ---------------------------------------------------------- |
| 定义    | `macro macroname(expr)`<br>`    # 做点啥`<br>`end`          |
| 使用    | `macroname(ex1, ex2, ...)` 或 `@macroname ex1, ex2, ...`    |
| 内置的宏 | `@test           # 精确相等`<br>`@test x ≈ y    # 近似相等 isapprox(x, y)`<br>`@assert         # assert (单元测试)`<br>`@which          # 查看对特定参数使用的方法/查找函数所在的模块`<br>`@time           # 运行时间与内存分配统计`<br>`@elapsed        # 返回执行用时`<br>`@allocated      # 查看内存分配`<br>`@async          # 异步任务` |


创建 *卫生宏* (hygienic macros)的规则：

- 在宏的内部只通过 `local` 声明本地变量。
- 在宏的内部不使用 `eval`。
- 转义插值表达式以避免宏变大：`$(esc(expr))`
