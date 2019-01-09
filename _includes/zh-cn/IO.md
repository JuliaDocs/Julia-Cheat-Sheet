
| -------------- | ------------------------------------------------------------------------------- |
| 读取流          | `stream = stdin`<br>`for line in eachline(stream)`<br>`    # 做点啥`<br>`end` |
| 读取文件        | `open(filename) do file`<br>`    for line in eachline(file)`<br>`        # 做点啥`<br>`    end`<br>`end` |
| 读取 CSV 文件   | `using CSV`<br>`data = CSV.File(filename)`                                      |
| 写入 CSV 文件   | `using CSV`<br>`CSV.write(filename, data)`                                      |
| 保存 Julia 对象 | `using JLD`<br>`save(filename, "object_key", object, ...)`                      |
| 读取 Julia 对象 | `using JLD`<br>`d = load(filename) # 返回对象的字典`                 |
| 保存 HDF5       | `using HDF5`<br>`h5write(filename, "key", object)`                              |
| 读取 HDF5       | `using HDF5`<br>`h5read(filename, "key")`                                       |
