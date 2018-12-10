并行计算相关的工具可以在标准库 `Distributed` 里找到。

|                                            |                                 |
| ------------------------------------------ | ------------------------------- |
| 启动带 N 各 worker 的 REPL                  | `julia -p N`                    |
| 可用的 worker 数量                          | `nprocs()`                      |
| 添加 N 个 worker                            | `addprocs(N)`                   |
| 查看所有 worker 的 pid                      | `for pid in workers()`<br>`    println(pid)`<br>`end` |
| 获得正在执行的 worker 的 id                 | `myid()`                         |
| 移除 worker                                | `rmprocs(pid)`                   |
| 在特定 pid 的 worker 上运行 f(args)         | `r = remotecall(f, pid, args...)`<br>`# 或:`<br>`r = @spawnat pid f(args)`<br>`...`<br>`fetch(r)` |
| 在特定 pid 的 worker 上运行 f(args) (更高效) | `remotecall_fetch(f, pid, args...)` |
| 在任意 worker 上运行 f(args)                | `r = @spawn f(args) ... fetch(r)` |
| 在所有 worker 上运行 f(args)                | `r = [@spawnat w f(args) for w in workers()] ... fetch(r)` |
| 让表达式 expr 在所有 worker 上执行           | `@everywhere expr`              |
| 并行化带<a class="tooltip" href="#">规约函数<span> 一个规约函数(reducer function)将不同独立 worker 的结果结合起来。 </span></a> red 的循环 | `sum = @distributed (red) for i in 1:10^6`<br>`    # 进行并行任务`<br>`end` |
| 将 f 用用到集合 coll 中的所有元素上           | `pmap(f, coll)`                 |

Worker 就是人们所说的并行/并发的进程。

需要并行化的模块，最好拆分成包含所有功能与变量的函数文件，和一个用于处理数据的驱动文件。
很明显驱动文件需要导入函数文件。

一个有实际意义的规约函数的例子：单词计数 by 
[Adam DeConinck](https://blog.ajdecon.org/parallel-word-count-with-julia-an-interesting).
