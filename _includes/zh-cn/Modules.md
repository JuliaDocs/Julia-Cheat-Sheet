模块是独立的全局变量工作区，它们将类似的功能组合到一起。

|                           |                                                  |
| ------------------------- | ------------------------------------------------ |
| 定义                      | `module PackageName`<br>`# 添加模块定义`<br>`# 使用 export 让定义对外可见`<br>`end` |
| 包含文件<br>`filename.jl` | `include("filename.jl")`                          |
| 加载                      | `using ModuleName        # 导出所有名称`<br>`using ModuleName: x, y            # 仅导出 x, y`<br>`using ModuleName.x, ModuleName.y: # 仅导出 x, y`<br>`import ModuleName       # 仅导出 ModuleName`<br>`import ModuleName: x, y           # 仅导出 x, y`<br>`import ModuleName.x, ModuleName.y # 仅导出 x, y` |
| 导出                      | `# 得到模块导出名称的数组`<br>`names(ModuleName)`<br><br>`# 包含未导出的、弃用的`<br>`# 和编译器产生的名称`<br>`names(ModuleName, all::Bool)`<br><br>`# 也显示从其他模块显式导入的名称`<br>`names(ModuleName, all::Bool, imported::Bool)` |

`using` 和 `import` 只有一点区别：

使用 `using` 时，你需要写 `function Foo.bar(..` 来给 `Foo`模块的函数 `bar` 增添一个新方法；
而使用 `import Foo.bar` 时，只需写 `function bar(...` 就能达到同样的效果。
