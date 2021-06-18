パッケージは，パッケージマネージャに表示される前に登録される([registered](https://pkg.julialang.org))必要があります．

Julia 1.0でパッケージマネージャを扱うには，２つの方法があります．
一つは，`using Pkg` と `Pkg` パッケージの関数を使う方法です．
もう一つは，REPLに `]` と入力して特別な対話型パッケージ管理モードに入る方法です (通常のREPLに戻るには，パッケージ管理モードで空行の`BACKSPACE`を押します )．

Juliaをインストールした直後はパッケージ管理モードを使います．`Pkg` モジュールをインストールすると，Juliaセッションで `Pkg` を利用できるようになります．

## Julia のセッションで，`Pkg` を使う方法

|                                            |                            |
| ------------------------------------------ | -------------------------- |
| インストール済のパッケージを列挙する (人間が読める形式)   | `Pkg.status()`             |
| 全てのパッケージを更新する              | `Pkg.update()`             |
| Install `PackageName` をインストールする   | `Pkg.add("PackageName")`   |
| `PackageName` を再構築(ビルド)する      | `Pkg.build("PackageName")` |
| `PackageName` を使用する (インストール後)    | `using PackageName`        |
| `PackageName` を削除する     | `Pkg.rm("PackageName")`    |

## 対話型パッケージ管理モードを使う方法

|                                                          |                                       |
| -------------------------------------------------------- | ------------------------------------- |
| `PackageName` を追加する         | `add PackageName`                     |
| `PackageName` を削除する         | `rm PackageName`                      |
| `PackageName` を更新する         | `update PackageName`                  |
| 開発版を使う    | `dev PackageName` または `dev GitRepoUrl` |
| 開発版の使用を中止し，公開版に戻す | `free PackageName`                    |

