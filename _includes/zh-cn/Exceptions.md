|                    |                                                 |
| ------------------ | ----------------------------------------------- |
| 抛出异常 SomeExcep  | `throw(SomeExcep())`                            |
| 再次引发当前的异常   | `rethrow()`                                     |
| 定义新异常 NewExcep | `struct NewExcep <: Exception`<br>`    v::String`<br>`end`<br><br>`Base.showerror(io::IO, e::NewExcep) = print(io, "A problem with $(e.v)!")`<br><br>`throw(NewExcep("x"))`                               |
| 抛出带文本的异常     | `error(msg)`                                   |
| 异常处理流程         | `try`<br>`    # 进行一些可能会失败的操作`<br>`catch ex`<br>`    if isa(ex, SomeExcep)`<br>`        # 处理异常 SomeExcep`<br>`    elseif isa(ex, AnotherExcep)`<br>`        # 处理另一个异常 AnotherExcep`<br>`    else`<br>`        # 处理其余的异常`<br>`    end`<br>`finally`<br>`    # 永远执行这些语句`<br>`end` |
