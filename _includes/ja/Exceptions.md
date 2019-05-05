|                           |                                                 |
| ------------------------- | ----------------------------------------------- |
| 例外 SomeExcep を発生させる | `throw(SomeExcep())`                            |
| 現在の例外を再発生させる | `rethrow()`                                     |
| 新しい例外 NewExcep を定義する  | `struct NewExcep <: Exception`<br>`    v::String`<br>`end`<br><br>`Base.showerror(io::IO, e::NewExcep) = print(io, "A problem with $(e.v)!")`<br><br>`throw(NewExcep("x"))` |
| テキスト `msg` でエラーを発生させる | `error(msg)`                                    |
| 例外を捕捉する          | `try`<br>`    # do something potentially iffy`<br>`catch ex`<br>`    if isa(ex, SomeExcep)`<br>`        # handle SomeExcep`<br>`    elseif isa(ex, AnotherExcep)`<br>`        # handle AnotherExcep`<br>`    else`<br>`        # handle all others`<br>`    end`<br>`finally`<br>`    # do this in any case`<br>`end` |
