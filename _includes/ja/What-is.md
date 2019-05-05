[Julia](https://julialang.org)は，技術計算のためのオープンソース，マルチプラットフォーム，高レベル，高性能なプログラミング言語です．

Juliaは<a class="tooltip" href="#">LLVM<span>Low-Level Virtual Machine (LLVM) は，
中間コードあるいはマシンコードを作るためのコンパイラ・インフラストラクチャです．</span></a>ベースの<a class="tooltip" href="#">JIT<span>
Just-In-Timeコンパイルは，実行前ではなく実行時に実行されます．
したがって，コンパイルされたコードの速度と解釈の柔軟性が得られます．
コンパイラはコードを解析して型を推定します．LLVMコードが生成された後に，ネイティブコードにコンパイルされます．</span></a>コンパイラを持ちます．
これは，低レベルコードの煩わしさなしに，
CやFORTRANなどの言語と同等の性能を引き出します．
コードは，その場でコンパイルされるため，シェルすなわち<a class="tooltip" href="#">REPL <span> Read-Eval-Print-Loop; 対話型評価ループ</span></a>内でコード（の断片）を実行できます．
これは推奨されるワークフロー([workflow](https://docs.julialang.org/en/stable/manual/workflow-tips)の一部です．

Juliaは動的型付けされていて，
<a class="tooltip" href="#">多重ディスパッチ<span>
関数の引数の型は実行時に決まるので，コンパイラは与えられた型に最適化された実装を選ぶことができます．</span></a>の機能を提供し，並列性と分散計算を目的に設計されました．

Juliaには，パッケージマネージャが組み込まれています．

Juliaには，特殊関数(例:ガンマ関数)を含む多くの数学関数が組み込まれています．また，複素数をすぐに利用できます．

Juliaでは，Lispに影響を受けたマクロのおかげでコードを自動生成することができます．

Juliaは2012年に生まれました．
