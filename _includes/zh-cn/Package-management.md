一个程序包必须先[注册](https://github.com/JuliaLang/METADATA.jl)，然后才能在包管理器中看到它。

在 Julia 1.0 中，有两种使用包管理器的方法：
- 一是通过 `using Pkg` 导入 `Pkg` 模块，然后用它的函数管理其他包；
- 或者在 REPL 中输入 `]`，然后按回车。进入特殊的交互式包管理模式。
  (要从包管理模式返回 REPL，只需要在空行上按退格键 `BACKSPACE` 就行了) 

注意新的工具总是先添加到交互式模式中，然后才会加入 `Pkg` 模块。

## 在 Julia 会话中使用 `Pkg` 管理包

|                                  |                            |
| -------------------------------- | -------------------------- |
| 列出已安装的包 (人类可读版)        | `Pkg.status()`             |
| 列出已安装的包 (机器可读版)        | `Pkg.installed()`          |
| 更新所有包                       | `Pkg.update()`             |
| 安装包                           | `Pkg.add("PackageName")`   |
| 重新构建包                       | `Pkg.build("PackageName")` |
| (在安装之后) 使用包               | `using PackageName`        |
| 删除包                           | `Pkg.rm("PackageName")`    |

## 交互式包管理模式

|                               |                                       |
| ----------------------------- | ------------------------------------- |
| 添加包                         | `add PackageName`                     |
| 删除包                         | `rm PackageName`                      |
| 更新包                         | `update PackageName`                  |
| 使用开发版本                   | `dev PackageName` 或 `dev GitRepoUrl` |
| 停止使用开发板，返回普通的发行版 | `free PackageName`                    |
