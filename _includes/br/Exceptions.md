|                                 |                                                 |
| ------------------------------- | ----------------------------------------------- |
| Lançar algumas exceções         | `throw(SomeExcep())`                            |
| Relançar exceção atual          | `rethrow()`                                     |
| Definir NewExcep                | `struct NewExcep <: Exception`<br>`    v::String`<br>`end`<br><br>`Base.showerror(io::IO, e::NewExcep) = print(io, "A problem with $(e.v)!")`<br><br>`throw(NewExcep("x"))` |
| Erro de lançamento com mensagem | `error(msg)`                              |
| Handler                         | `try`<br>`    # do something potentially iffy`<br>`catch ex`<br>`    if isa(ex, SomeExcep)`<br>`        # handle SomeExcep`<br>`    elseif isa(ex, AnotherExcep)`<br>`        # handle AnotherExcep`<br>`    else`<br>`        # handle all others`<br>`    end`<br>`finally`<br>`    # do this in any case`<br>`end` |
