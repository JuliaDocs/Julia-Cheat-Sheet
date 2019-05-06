|                                                |                                             |
| ---------------------------------------------- | ------------------------------------------- |
| 文字                           | `chr = 'C'`                                 |
| 文字列                        | `str = "A string"`                          |
| 文字コード                         | `Int('J') == 74`                            |
| 文字コードから文字を得る                    | `Char(74) == 'J'`                           |
| UTF 文字                 | `chr = '\uXXXX'     # 4-digit HEX`<br>`chr = '\UXXXXXXXX' # 8-digit HEX` |
| 文字列を一文字ごとに繰り返す               | `for c in str`<br>`    println(c)`<br>`end` |
| 文字列の連結                    | `str = "Learn" * " " * "Julia"`             |
| 文字列の補間    | `a = b = 2`<br>`println("a * b = $(a*b)")`  |
| 文字または正規表現にマッチした最初の文字のインデックス | `findfirst(isequal('i'), "Julia") == 4`     |
| (サブ)文字列または正規表現にマッチした文字列を置換する  | `replace("Julia", "a" => "us") == "Julius"` |
| 最後のインデックス     | `lastindex("Hello") == 5`                   |
| 文字数      | `length("Hello") == 5`                      |
| 正規表現         | `pattern = r"l[aeiou]"`                     |
| match オブジェクト             | `str = "+1 234 567 890"`<br>`pat = r"\+([0-9]) ([0-9]+)"`<br>`m = match(pat, str)`<br>`m.captures == ["1", "234"]` |
| pat にマッチした全てのサブ文字列からなる配列      | `[m.match for m = eachmatch(pat, str)]`     |
| pat にマッチする全ての match オブジェクトによるイテレータ  | `eachmatch(pat, str)`                       |

UTF-8 は，多バイトで Unicode エンコードされることに注意してください．([訳注] 文字列の最後のインデックスと文字数は異なる場合があります) <br>
`10 == lastindex("Ångström") != length("Ångström") == 8`

文字列はイミュータブル(不変, 変更不能)です．
