函数的所有参数都是传参(passed by reference)。

以 `!` 结尾的函数会改变至少一个参数，一般是改变第一个参数：`sort!(arr)`。

必须的参数以逗号分隔，通过位置传入。

可选的参数均需要一个默认值，用 `=` 定义。


关键字参数使用名称标记，它们放在函数签名中的分号后面：

````julia
function func(req1, req2; key1=dflt1, key2=dflt2)
    # 做点啥
end
````

在调用函数时，关键字参数前的分号 **不是** 必须的。

`return` 语句是可选的，但我们强烈建议你为每一个函数都加上 `return`。

在单一的 `return` 语句中，可以通过元组返回多种数据结构。

从命令行输入的参数 `julia script.jl arg1 arg2...`，可以通过常量 `ARGS` 访问：

```julia
for arg in ARGS
    println(arg)
end
```

匿名函数可以用于收集函数(collection functions)或列表推断(list comprehensions)：
`x -> x^2`.

函数可以接收可变数量的参数

```julia
function func(a...)
    println(a)
end

func(1, 2, [3:5]) # tuple: (1, 2, UnitRange{Int64}[3:5])
```

函数可以嵌套

```julia
function outerfunction()
    # 在外面做点啥
    function innerfunction()
        # 在内面做点啥
        # 可以访问之前在外部定义的东西
    end
    # 在外面继续做点啥
end
```

函数可以显示指定返回类型

```julia
# 接收 Number 的任何子类型，返回一个字符串
function stringifynumber(num::T)::String where T <: Number
    return "$num"
end
```

函数可以通过[点语法](http://docs.juliacn.com/latest/manual/functions/#man-vectorized-1)
向量化

```julia
# 这里通过点语法广播了减去均值的操作
julia> using Statistics
julia> A = rand(3, 4);
julia> B = A .- mean(A, dims=1)
3×4 Array{Float64,2}:
  0.0387438     0.112224  -0.0541478   0.455245
  0.000773337   0.250006   0.0140011  -0.289532
 -0.0395171    -0.36223    0.0401467  -0.165713
julia> mean(B, dims=1)
1×4 Array{Float64,2}:
 -7.40149e-17  7.40149e-17  1.85037e-17  3.70074e-17
```

Julia 会根据数据类型生成相应的
<a class="tooltip" href="#">特化版本<span> 
多重分派(Multiple dispatch)某种多态的类型，会动态的决定调用函数的哪个版本。
这里“动态”意味着在运行时做出选择，而方法重载则是在编译时完成的。
Julia 自动在后台管理多重分派。
当然你也可以使用类型注释提供自定义函数重载。
</span></a>函数。
当一个函数再次以同样的参数调用时，Julia 会跳过编译过程，
直接查找对应的本地机器码(native machine code)。

从  **Julia 0.5** 之后，定义有潜在歧义是可接受的。
但实际上调用一个不明确的方法是一种 **直接错误**(immediate error)。

当递归函数的调用很深之后会发生栈溢出(Stack overflow)。
[Trampolining](https://web.archive.org/web/20140420011956/http://blog.zachallaun.com/post/jumping-julia) 
可以用来做尾递归优化，实际上 Julia [还不能](https://github.com/JuliaLang/julia/issues/4964)
自动完成这种优化。
或者你也可以将尾递归重写为迭代。
