- 编写
  [类型稳定](https://www.johnmyleswhite.com/notebook/2013/12/06/writing-type-stable-code-in-julia)
  的代码
- 尽可能使用不可变类型
- 大数组用 `sizehint!` 预分配内存
- 用 `arr = nothing` 释放大数组的内存
- 使用列访问数组，因为多维数组总是以列优先的顺序储存
- 预分配储存结果用的数据结构
- 在实时应用中使用 `disable_gc()` 关闭垃圾收集器
- 避免使用关键字参数的 splat 操作符(`...`)
- 使用会改变参数的 APIs 以避免复制数据结构。(例如：以 `!` 结尾的函数)
- 使用逐元素的数组操作，而不是列表推断(list comprehensions)
- 避免在计算密集的循环中使用 `try`-`catch`
- 避免在收集(collections)中出现 `Any`
- 避免在收集(collections)中使用抽象类型
- 避免在 I/O 中使用字符串插值
- 不像 R, MATLAB 或 Python，在 Julia 中[向量化](https://www.johnmyleswhite.com/notebook/2013/12/22/the-relationship-between-vectorized-and-devectorized-code "https://www.johnmyleswhite.com/notebook/2013/12/22/the-relationship-between-vectorized-and-devectorized-code")
  并不会提升运行速度
- 避免在运行时使用 `eval`
