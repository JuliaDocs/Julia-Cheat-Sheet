関数の全ての引数は、参照で渡されます。

名前の末尾に `!` がついた関数は、少なくとも１つの引数(通常は最初の引数)を変更します : `sort!(arr)`.

必須の引数は、コンマ `,` で区切ります。位置による表記が用いられます。

オプション引数は、既定値 (デフォルト値)が必要です。関数定義(シグネチャ)の中で `=` を用いて定義します。

キーワード引数は、キーワード名を付けた表記が用いられます。関数定義(シグネチャ)の中で、セミコロン `;` の後に列挙されます。

````
function func(req1, req2; key1=dflt1, key2=dflt2)
    # do stuff
end
````

キーワード引数を受け取る関数の呼び出しでは、セミコロン `;` は*不要です*。

`return` 文は必須ではありませんが、使うことが推奨されます。

複数のデータ構造を戻り値にできます。一つの `return` 文でタプルを使います。

コマンドライン引数 `julia script.jl arg1 arg2...` は、全域定数 `ARGS` を用いて読み出すことができます :

```
for arg in ARGS
    println(arg)
end
```

匿名関数は、コレクション関数またはリスト内包表記で使うのに適しています : `x -> x^2`.

関数は、可変長の引数を受け取ることもできます:

```
function func(a...)
    println(a)
end

func(1, 2, [3:5]) # tuple: (1, 2, UnitRange{Int64}[3:5])
```

関数定義は、入れ子に(ネスト)できます:

```
function outerfunction()
    # do some outer stuff
    function innerfunction()
        # do inner stuff
        # can access prior outer definitions
    end
    # do more outer stuff
end
```

関数定義は、戻り値の型を明示することもできます。

```
# take any Number subtype and return it as a String
function stringifynumber(num::T)::String where T <: Number
    return "$num"
end
```

関数呼び出しは、ドット構文を用いてベクトル化できます ([vectorized](https://docs.julialang.org/en/v1/manual/functions/#man-vectorized-1))。

```
# here we broadcast the subtraction of each mean value
# by using the dot operator
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

Julia は、引数のデータ型に基づき関数の<a class="tooltip" href="#">特殊なバージョン<span>「多重ディスパッチ」
どのバージョンを呼び出すかを「動的」に決める「ポリモーフィズム」の一種類です。
この文脈では、「動的」とは実行時に決定することを意味します。
これに対して、メソッド・オーバーロードは、コンパイル時に決定します。
Julia は、完全にバックグラウンドで多重ディスパッチを行います。
もちろん、型注釈(type annotation)を用いて、メソッド・オーバーロードを指定することもできます。</span></a>を生成します。
関数が同じ引数のデータ型で再び呼び出されたときには、
Julia は、同じ型のネイティブ・マシン・コードを検索して、
コンパイルのプロセスをスキップします。

**Julia 0.5** 以降も、潜在的な型の曖昧さの存在は許されますが、
曖昧なメソッドの呼び出しを呼び出すことは **即時エラー** となります。

再帰関数が多くのレベルを深くネストすると、スタックオーバーフローが発生する可能性があります。

末尾再帰の最適化は
[Trampolining](https://web.archive.org/web/20140420011956/http://blog.zachallaun.com/post/jumping-julia) と呼ばれる手法で可能ですが、
Julia では[自動的に行いません](https://github.com/JuliaLang/julia/issues/4964)。
あるいは、プログラマが、末尾再帰を繰返しとして書き直すこともできます。
