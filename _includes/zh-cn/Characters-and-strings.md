|                               |                                              |
| ----------------------------- | -------------------------------------------- |
| 字符                          | `chr = 'C'`                                   |
| 字符串                        | `str = "A string"`                            |
| 字符 => 编码                  | `Int('J') == 74`                              |
| 编码 => 字符                  | `Char(74) == 'J'`                             |
| 任意的 UTF 字符               | `chr = '\uXXXX'     # 4 位 HEX`<br>`chr = '\UXXXXXXXX' # 8 位 HEX` |
| 逐字符迭代                    | `for c in str`<br>`    println(c)`<br>`end`   |
| 字符串拼接                    | `str = "Learn" * " " * "Julia"`               |
| 字符插值                      | `a = b = 2`<br>`println("a * b = $(a*b)")`    |
| 第一个匹配的子串或正则表达式    | `findfirst(isequal('i'), "Julia") == 4`       |
| 替换字串或正则表达式           | `replace("Julia", "a" => "us") == "Julius"`   |
| 收集的最后一个索引值           | `lastindex("Hello") == 5`                     |
| 字符串的长度                  | `length("Hello") == 5`                        |
| 正则表达式                    | `pattern = r"l[aeiou]"`                       |
| 字字符串                      | `str = "+1 234 567 890"`<br>`pat = r"\+([0-9]) ([0-9]+)"`<br>`m = match(pat, str)`<br>`m.captures == ["1", "234"]` |
| 所有匹配                      | `[m.match for m = eachmatch(pat, str)]`       |
| 所有匹配的迭代器               | `eachmatch(pat, str)`                         |

要当心 UTF-8 中的多字节 Unicode 编码：<br>
```julia
julia> lastindex("Ångström")
10

julia> length("Ångström")
8
```


字符串是不可变的。
