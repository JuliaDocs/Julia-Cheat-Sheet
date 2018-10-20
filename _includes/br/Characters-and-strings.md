|                                                |                                                                                                                    |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Caractere                                      | `chr = 'C'`                                                                                                        |
| String                                         | `str = "A string"`                                                                                                 |
| Caractere do código                            | `Int('J') == 74`                                                                                                   |
| Caractere apartir do código                    | `Char(74) == 'J'`                                                                                                  |
| Qualquer caractere UTF                         | `chr = '\uXXXX'     # 4-digit HEX`<br>`chr = '\UXXXXXXXX' # 8-digit HEX`                                           |
| Fazer loop pelos caracteres                    | `for c in str`<br>`    println(c)`<br>`end`                                                                        |
| Concatenação                                   | `str = "Learn" * " " * "Julia"`                                                                                    |
| Interpolação de String                         | `a = b = 2`<br>`println("a * b = $(a*b)")`                                                                         |
| Primeiro caractere correspondente ou expressão regular  | `findfirst(isequal('i'), "Julia") == 4`                                                                            |
| Substituir substring ou expressão regular        | `replace("Julia", "a" => "us") == "Julius"`                                                                        |
| Último índice (da coleção)                     | `lastindex("Hello") == 5`                                                                                          |
| Número de caracteres                             | `length("Hello") == 5`                                                                                             |
| Expressão regular                              | `pattern = r"l[aeiou]"`                                                                                            |
| Sub-expressões                                 | `str = "+1 234 567 890"`<br>`pat = r"\+([0-9]) ([0-9]+)"`<br>`m = match(pat, str)`<br>`m.captures == ["1", "234"]` |
| Todas as ocorrêcias                            | `[m.match for m = eachmatch(pat, str)]`                                                                            |
| Todas as ocorrêcias (como iterador)            | `eachmatch(pat, str)`                                                                                              |


Cuidado com multi-byte Unicode codificações em UTF-8:
`10 == lastindex("Ångström") != length("Ångström") == 8`
Strings são imutáveis.
