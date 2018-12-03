[Julia](https://julialang.org) 是一种为科学计算而生的，开源、多平台、高性能的高级编程语言。

Julia 有一个基于
<a class="tooltip" href="#">LLVM<span> 低级虚拟机(Low-Level Virtual Machine)是一个编译基础设施，用于构建中间代码(IR)或者二进制机器码。 </span></a>
的
<a class="tooltip" href="#">JIT<span> 即时编译(Just-In-Time compilation)发生在运行时而不是程序执行之前。这意味着它在保证编译后代码的运行速度的同时，还提供了代码解释的灵活性。编译器先解析代码并进行类型推断，然后生成 LLVM 代码，最后将其编译为本地代码(native code)。 </span></a>
编译器，这让使用者无需编写底层的代码也能拥有像 C 与 FORTRAN 那样的性能。因为代码在运行中编译，你可以在 shell 或
<a class="tooltip" href="#">REPL<span> 读取-执行-输出 循环(Read-Eval-Print-Loop) </span></a>中运行代码，这也是一种推荐的[工作流程](http://docs.juliacn.com/latest/manual/workflow-tips/)。

Julia 是动态类型的。并且提供了为并行计算和分布式运算设计的 <a class="tooltip" href="#">多重派发<span> 因为函数参数的类型是在运行时才能确定的，编译器可以为不同类型的参数，选择基于特定参数类型和处理器架构优化后的不同实现。</span></a> 机制。

Julia 自带包管理器。

Julia 有许多内置的数学函数，包括特殊函数 (例如：Gamma 函数)。并且支持开箱即用的复数运算。

Julia 允许你通过类似 Lisp 的宏来自动生成代码。

Julia 诞生于 2012 年。
