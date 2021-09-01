|                   |                                                                                 |
| ----------------- | ------------------------------------------------------------------------------- |
| Lire un flux      | `stream = stdin`<br>`for line in eachline(stream)`<br>`    # do stuff`<br>`end` |
| Lire un fichier   | `open(filename) do file`<br>`    for line in eachline(file)`<br>`        # do stuff`<br>`    end`<br>`end` |
| Lire un fichier CSV   | `using CSV`<br>`data = CSV.read(filename)`                                      |
| Ecrire un fichier CSV    | `using CSV`<br>`CSV.write(filename, data)`                                      |
| Sauvegarder un objet Julia | `using JLD`<br>`save(filename, "object_key", object, ...)`                      |
| Charger un objet Julia | `using JLD`<br>`d = load(filename) # Returns a dict of objects`                 |
| Sauvegarder un fichier HDF5   `using HDF5`<br>`h5write(filename, "key", object)`                              |
| Charger un fichier HDF5 | `using HDF5`<br>`h5read(filename, "key")`                                       |
