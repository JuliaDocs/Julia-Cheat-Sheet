模块是独立的全局变量工作区，它们将类似的功能组合到一起。

|                       |                                                      |
| --------------------- | ---------------------------------------------------- |
| 定义                  | `module PackageName`<br>`# 添加模块定义`<br>`# 使用 export 让定义对外可见`<br>`end` |
| 包含文件 `filename.jl` | `include("filename.jl")`                             |
| 加载                  | `using ModuleName        # 导出所有名称`<br>`using ModuleName: x, y            # 仅导出 x, y`<br>`using ModuleName.x, ModuleName.y: # 仅导出 x, y`<br>`import ModuleName       # 仅导出 ModuleName`<br>`import ModuleName: x, y           # 仅导出 x, y`<br>`import ModuleName.x, ModuleName.y # 仅导出 x, y` |
| 导出                  | `# Get an array of names exported by Module`<br>`names(ModuleName)`<br><br>`# include non-exports, deprecateds`<br>`# and compiler-generated names`<br>`names(ModuleName, all::Bool)`<br><br>`#also show namesexplicitely imported from other modules`<br>`names(ModuleName, all::Bool, imported::Bool)` |

There is only one difference between `using` and `import` : with `using` you need to say
`function Foo.bar(..` to extend module `Foo`'s function `bar` with a new method, but
with `import Foo.bar`, you only need to say `function bar(...` and it automatically
extends module `Foo`'s function `bar` .
