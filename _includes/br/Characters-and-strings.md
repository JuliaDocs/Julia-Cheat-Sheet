|                                                |                                                                                                                    |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Charactere                                     | `chr = 'C'`                                                                                                        |
| String                                         | `str = "Uma string"`                                                                                               |
| Código do caractere                            | `Int('J') == 74`                                                                                                   |
| Caractere atrelado ao código                   | `Char(74) == 'J'`                                                                                                  |
| Qualquer caractere UTF                         | `chr = '\uXXXX'     # HEX de 4 digitos`<br>`chr = '\UXXXXXXXX' # HEX de 8 digitos`                                 |
| Ciclar entre caractéres                        | `for c in str`<br>`    println(c)`<br>`end`                                                                        |
| Concatenação                                   | `str = "Aprenda" * " " * "Julia"`                                                                                  |
| Interpolação de Strings                        | `a = b = 2`<br>`println("a * b = $(a*b)")`                                                                         |
| Primeiro caractere ou expressão regular encontrada | `findfirst(isequal('i'), "Julia") == 4`                                                                        |
| Substituir substring ou expressão regular      | `replace("Julia", "a" => "us") == "Julius"`                                                                        |
| Ultimo índice (de uma coleção)                 | `lastindex("Hello") == 5`                                                                                          |
| Numero de caracteres                           | `length("Hello") == 5`                                                                                             |
| Expressão regular (REGEX)                      | `pattern = r"l[aeiou]"`                                                                                            |
| Subexpressões                                  | `str = "+1 234 567 890"`<br>`pat = r"\+([0-9]) ([0-9]+)"`<br>`m = match(pat, str)`<br>`m.captures == ["1", "234"]` |
| Todas ocorrências                              | `[m.match for m = eachmatch(pat, str)]`                                                                            |
| Todas ocorrências (como iterador)              | `eachmatch(pat, str)`                                                                                              |

Cuidado com codificações Unicode com varios bytes em UTF-8:
`10 == lastindex("Ångström") != length("Ångström") == 8`
Strings são imutáveis.
