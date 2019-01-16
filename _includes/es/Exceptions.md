|                               |                                                 |
| ----------------------------- | ----------------------------------------------- |
| Lanzar SomeExcep              | `throw(SomeExcep())`                            |
| Relanzar la excepción actual  | `rethrow()`                                     |
| Definir NewExcep              | `struct NewExcep <: Exception`<br>`    v::String`<br>`end`<br><br>`Base.showerror(io::IO, e::NewExcep) = print(io, "A problem with $(e.v)!")`<br><br>`throw(NewExcep("x"))` |
| Lanzar error con mensaje msg  | `error(msg)`                                    |
| Gestor de excepción           | `try`<br>`    # código dudoso`<br>`catch ex`<br>`    if isa(ex, SomeExcep)`<br>`        # gestionar SomeExcep`<br>`    elseif isa(ex, AnotherExcep)`<br>`        # gestionar AnotherExcep`<br>`    else`<br>`        # gestionar las restantes`<br>`    end`<br>`finally`<br>`    # hacer esto en cualquier caso`<br>`end` |
