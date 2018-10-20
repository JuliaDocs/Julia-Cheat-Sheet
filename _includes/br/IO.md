|                        |                                                                                                     |
| ---------------------- | --------------------------------------------------------------------------------------------------- |
| Ler fluxo de dado      | `stream = stdin`<br>`for line in eachline(stream)`<br>`# faça alguma coisa`<br>`end`                |
| Ler arquivo            | `open(filename) do file`<br>`for line in eachline(file)`<br>`# faça alguma coisa`<br>`end`<br>`end` |
| Ler arquivo CSV        | `using CSV`<br>`CSV.read(filename)`                                                                 |
| Salvar Julia Object    | `using JLD`<br>`save(filename, "object_key", object, ...)`                                          |
| Carregar Julia Object  | `using JLD`<br>`d = load(filename) # Returns a dict of objects`                                     |
| Salvar HDF5            | `using HDF5`<br>`h5write(filename, "key", object)`                                                  |
| Carregar HDF5          | `using HDF5`<br>`h5read(filename, "key")`                                                           |
