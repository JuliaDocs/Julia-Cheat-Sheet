|                                                |                                             |
| ---------------------------------------------- | ------------------------------------------- |
| Caractère                                      | `chr = 'C'`                                 |
| Chaîne de caractères                           | `str = "A string"`                          |
| Codage d'un caractère                          | `Int('J') == 74`                            |
| Caractère depuis son code                      | `Char(74) == 'J'`                           |
| Tout caractère UTF                             | `chr = '\uXXXX'     # 4-digit HEX`<br>`chr = '\UXXXXXXXX' # 8-digit HEX` |
| Itération sur une chaîne de caractère          | `for c in str`<br>`    println(c)`<br>`end` |
| Concaténation                                  | `str = "Learn" * " " * "Julia"`             |
| Interpolation de chaînes                       | `a = b = 2`<br>`println("a * b = $(a*b)")`  |
| Premier caractère ou expression régulière correspondant | `findfirst(isequal('i'), "Julia") == 4`     |
| Remplacer une une sous-chaîne ou expression régulière | `replace("Julia", "a" => "us") == "Julius"` |
| Dernier indice (d'une collection)              | `lastindex("Hello") == 5`                   |
| Nombre de caractères                           | `length("Hello") == 5`                      |
| Expression régulière                           | `pattern = r"l[aeiou]"`                     |
| Sous-expression                                | `str = "+1 234 567 890"`<br>`pat = r"\+([0-9]) ([0-9]+)"`<br>`m = match(pat, str)`<br>`m.captures == ["1", "234"]` |
| Toutes les occurrences                         | `[m.match for m = eachmatch(pat, str)]`     |
| Toutes les occurrences (en tant qu'itérateur)  | `eachmatch(pat, str)`                       |


Attention aux encodages Unicode multi-byte en UTF-8: <br>
`10 == lastindex("Ångström") != length("Ångström") == 8`

Les chaînes sont immuables.
