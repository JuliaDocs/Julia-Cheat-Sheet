|                                 |                                                 |
| ------------------------------- | ----------------------------------------------- |
| Lançar AlgumaExcecao            | `throw(AlgumaExcecao())`                        |
| Relançar exceção atual          | `rethrow()`                                     |
| Definir NovaExcecao             | `struct NovaExcecao <: Exception`<br>`    v::String`<br>`end`<br><br>`Base.showerror(io::IO, e::NovaExcecao) = print(io, "Um problema com $(e.v)!")`<br><br>`throw(NovaExcecao("x"))` |
| Lançar erro com mensagem        | `error(mensagem)`                                    |
| Tratamento                      | `try`<br>`    # faca algo potencialmente duvidoso`<br>`catch ex`<br>`    if isa(ex, AlgumaExcecao)`<br>`        # tratar AlgumaExcecao`<br>`    elseif isa(ex, UmaOutraExcecao)`<br>`        # tratar UmaOutraExcecao`<br>`    else`<br>`        # tratar os restantes`<br>`    end`<br>`finally`<br>`    # faça isso em qualquer caso`<br>`end` |
