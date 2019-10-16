並列計算ツールは，標準ライブラリ `Distributed` を用いて利用できます．

|                                            |                                   |
| ------------------------------------------ | --------------------------------- |
| N個のワーカーを含む REPLを開始する     | `julia -p N`                      |
| 利用可能なワーカーの数       | `nprocs()`                        |
| N 個のワーカーを追加する                   | `addprocs(N)`                     |
| 全てのワーカー id を印字する         | `for pid in workers()`<br>`    println(pid)`<br>`end` |
| 実行中のワーカーの id を得る         | `myid()`                          |
| ワーカーを削除する                | `rmprocs(pid)`                    |
| pid に対して，引数 args で f を実行する       | `r = remotecall(f, pid, args...)`<br>`# or:`<br>`r = @spawnat pid f(args)`<br>`...`<br>`fetch(r)` |
| 上と同じ (より効率のよい方法) | `remotecall_fetch(f, pid, args...)` |
| 任意のワーカーに対して，引数 args で f を実行する  | `r = @spawn f(args) ... fetch(r)` |
| 全てのワーカーに対して，引数 args で f を実行する   | `r = [@spawnat w f(args) for w in workers()] ... fetch(r)` |
| 全てのワーカーに対して，式 expr を利用可能とする   | `@everywhere expr`                |
| <a class="tooltip" href="#">reducer<span>reducerは，異なる(独立な)ワーカーからの結果を結合します</span></a>関数 red を用いた並列ループ | `sum = @distributed (red) for i in 1:10^6`<br>`    # do parallelstuff`<br>`end` |
| コレクション coll の全ての要素に対して，f を適用する | `pmap(f, coll)`                   |

ワーカーは，並行(コンカレント)あるいは並列(パラレル)なプロセスとしても知られています．

並列処理機能を備えたモジュールは，
「関数ファイル」と「ドライバファイル」に最もよく分割できます．
「関数ファイル」は，全てのワーカーで必要とされる関数と変数の全てを含みます．
データ処理を扱う「ドライバファイル」は「関数ファイル」にインポートされる必要があります．

reducer 関数に関する例 (word count)は，こちらを参照してください．
[Adam DeConinck](https://blog.ajdecon.org/parallel-word-count-with-julia-an-interesting).
