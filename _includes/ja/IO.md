|                   |                                                                                 |
| ----------------- | ------------------------------------------------------------------------------- |
| stream を読む  | `stream = stdin`<br>`for line in eachline(stream)`<br>`    # do stuff`<br>`end` |
| file を読む        | `open(filename) do file`<br>`    for line in eachline(file)`<br>`        # do stuff`<br>`    end`<br>`end` |
| CSV ファイルを読む  | `using CSV`<br>`data = CSV.read(filename)`                                      |
| CSV ファイルとして書き出す  | `using CSV`<br>`CSV.write(filename, data)`                                      |
| Julia オブジェクトをファイルに保存する | `using JLD`<br>`save(filename, "object_key", object, ...)`                      |
| Julia Object をファイルから読み込む | `using JLD`<br>`d = load(filename) # Returns a dict of objects`                 |
| HDF5 ファイルとして保存する | `using HDF5`<br>`h5write(filename, "key", object)`                              |
| HDF5 ファイルを読み込む | `using HDF5`<br>`h5read(filename, "key")`                                       |
