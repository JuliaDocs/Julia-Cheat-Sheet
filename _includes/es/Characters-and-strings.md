|                                                 |                                             |
| ----------------------------------------------- | ------------------------------------------- |
| Carácter                                        | `chr = 'C'`                                 |
| Cadena de texto                                 | `str = "A string"`                          |
| Código del carácter                             | `Int('J') == 74`                            |
| Carácter del código                             | `Char(74) == 'J'`                           |
| Cualquier carácter UTF                          | `chr = '\uXXXX'     # HEX 4-dígitos`<br>`chr = '\UXXXXXXXX' # HEX 8-dígitos` |
| Bucle por los caracteres de la cadena           | `for c in str`<br>`    println(c)`<br>`end` |
| Concatenación                                   | `str = "Learn" * " " * "Julia"`             |
| Interpolación de cadena                         | `a = b = 2`<br>`println("a * b = $(a*b)")`  |
| Primer carácter coincidente o expresión regular | `findfirst(isequal('i'), "Julia") == 4`     |
| Substituir subcadena o expresión regular        | `replace("Julia", "a" => "us") == "Julius"` |
| Último índice (de la colección)                 | `lastindex("Hello") == 5`                   |
| Número de caracteres                            | `length("Hello") == 5`                      |
| Expresión regular                               | `pattern = r"l[aeiou]"`                     |
| Subexpresiones                                  | `str = "+1 234 567 890"`<br>`pat = r"\+([0-9]) ([0-9]+)"`<br>`m = match(pat, str)`<br>`m.captures == ["1", "234"]` |
| Todas las ocurrencias                           | `[m.match for m = eachmatch(pat, str)]`     |
| Todas las ocurrencias (como iterador)           | `eachmatch(pat, str)`                       |


Atención a las codificaciones Unicode multi-byte en UTF-8: <br>
`10 == lastindex("Ångström") != length("Ångström") == 8`

Las cadenas de texto son inmutables.
