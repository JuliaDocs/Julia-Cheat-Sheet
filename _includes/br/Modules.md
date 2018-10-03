Modules are separate global variable workspaces that group together similar functionality.

|                       |                                                                                                                                                                                                                                                                                                          |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition            | `module PackageName`<br>`# add module definitions`<br>`# use export to make definitions accessible`<br>`end`                                                                                                                                                                                             |
| Include `filename.jl` | `include("filename.jl")`                                                                                                                                                                                                                                                                                 |
| Load                  | `using ModuleName        # all exported names`<br>`using ModuleName: x, y  # only x, y`<br>`using ModuleName.x, ModuleName.y:     # only x, y`<br>`import ModuleName       # only ModuleName`<br>`import ModuleName: x, y# only x, y`<br>`import ModuleName.x, ModuleName.y     # only x, y`             |
| Exports               | `# Get an array of names exported by Module`<br>`names(ModuleName)`<br><br>`# include non-exports, deprecateds`<br>`# and compiler-generated names`<br>`names(ModuleName, all::Bool)`<br><br>`#also show namesexplicitely imported from other modules`<br>`names(ModuleName, all::Bool, imported::Bool)` |

There is only one difference between `using` and `import` : with `using` you need to say
`function Foo.bar(..` to extend module `Foo`'s function `bar` with a new method, but
with `import Foo.bar`, you only need to say `function bar(...` and it automatically
extends module `Foo`'s function `bar` .
