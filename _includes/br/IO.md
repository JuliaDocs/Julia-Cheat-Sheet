|                          |                                                                                                     |
| ------------------------ | --------------------------------------------------------------------------------------------------- |
| Ler fluxo de dado        | `stream = stdin`<br>`for line in eachline(stream)`<br>`# faça alguma coisa`<br>`end`                |
| Ler arquivo              | `open(filename) do file`<br>`for line in eachline(file)`<br>`# faça alguma coisa`<br>`end`<br>`end` |
| Ler arquivo CSV          | `using CSV`<br>`CSV.read(filename)`                                                                 |
| Salvar objeto do Julia   | `using JLD`<br>`save(filename, "object_key", object, ...)`                                          |
| Carregar objeto do Julia | `using JLD`<br>`d = load(filename) # Retorna um dicionario de objetos`                              |
| Salvar HDF5              | `using HDF5`<br>`h5write(filename, "key", object)`                                                  |
| Carregar HDF5            | `using HDF5`<br>`h5read(filename, "key")`                                                           |
