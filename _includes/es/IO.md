|                      |                                                                                 |
| -------------------- | ------------------------------------------------------------------------------- |
| Leer flujo           | `stream = stdin`<br>`for line in eachline(stream)`<br>`    # do stuff`<br>`end` |
| Leer archivo         | `open(filename) do file`<br>`    for line in eachline(file)`<br>`        # do stuff`<br>`    end`<br>`end` |
| Leer archivo CSV     | `using CSV`<br>`data = CSV.read(filename)`                                      |
| Escribir archivo CSV | `using CSV`<br>`CSV.write(filename, data)`                                      |
| Salvar objeto Julia  | `using JLD`<br>`save(filename, "object_key", object, ...)`                      |
| Cargar objeto Julia  | `using JLD`<br>`d = load(filename) # Devuelve un dict de objetos`                 |
| Salvar HDF5          | `using HDF5`<br>`h5write(filename, "key", object)`                              |
| Cargar HDF5          | `using HDF5`<br>`h5read(filename, "key")`                                       |
