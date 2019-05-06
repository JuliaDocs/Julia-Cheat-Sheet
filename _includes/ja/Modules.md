モジュールとは，個別の全域変数の作業領域で，似たような機能を一箇所にまとめたものです．

|                       |                                                      |
| --------------------- | ---------------------------------------------------- |
| 定義        | `module PackageName`<br>`# add module definitions`<br>`# use export to make definitions accessible`<br>`end` |
| `filename.jl` を取り込む(インクルードする) | `include("filename.jl")`                             |
| 読み込む         | `using ModuleName        # all exported names`<br>`using ModuleName: x, y              # only x, y`<br>`using ModuleName.x, ModuleName.y:   # only x, y`<br>`import ModuleName       # only ModuleName`<br>`import ModuleName: x, y             # only x, y`<br>`import ModuleName.x, ModuleName.y   # only x, y` |
| 輸出(エクスポート)する          | `# Get an array of names exported by Module`<br>`names(ModuleName)`<br><br>`# include non-exports, deprecateds`<br>`# and compiler-generated names`<br>`names(ModuleName, all::Bool)`<br><br>`#also show namesexplicitely imported from other modules`<br>`names(ModuleName, all::Bool, imported::Bool)` |

`using` と `import` の違いは，ただ一つです :
`using Foo` では，
`Foo` モジュールの関数 `bar` を新しいメソッドとして拡張する場合に
`function Foo.bar(..` と書く必要があります．
これに対して，`import Foo.bar` では，
`function bar(...` と，そのまま書けばよいです．モジュール `Foo` の関数 `bar` は自動的に拡張されます．
