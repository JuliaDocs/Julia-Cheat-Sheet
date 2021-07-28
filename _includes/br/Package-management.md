Pacotes devem ser [registrados](https://julialang.org/packages/) antes de 
serem visíveis ao gerenciador de pacotes.
Em Julia 1.0, existem duas formas de utilizar o gerenciador de pacotes:
Ou com `using Pkg` e usando funções `Pkg`, ou digitando `]` no REPL para entrar no
modo Gerenciamento de Pacotes Interativo. (Para voltar para o REPL normal, pressione
`BACKSPACE` em uma linha vazia no modo de gerenciamento de pacotes). Note que novas
ferramentas chegam no modo interativo primeiro, e depois se tornam disponíveis em sessões Julia
normais por meio do `módulo Pkg`

## Usando `Pkg` em uma sessão Julia

|                                            |                            |
| ------------------------------------------ | -------------------------- |
| Listar pacotes instalados (Legivel para humanos)   | `Pkg.status()`     |
| Atualizar todos os pacotes                 | `Pkg.update()`             |
| Instalar `NomedoPacote`                    | `Pkg.add("NomedoPacote")`  |
| Reconstruir `NomedoPacote`                 | `Pkg.build("NomedoPacote")`|
| Usar `NomedoPacote` (depois de instalação) | `using NomedoPacote`       |
| Remover `NomedoPacote`                     | `Pkg.rm("NomedoPacote")`   |

## No modo de Gerenciamento de Pacotes Interativo

|                                                          |                                       |
| -------------------------------------------------------- | ------------------------------------- |
| Adicionar `NomedoPacote`                                 | `add NomedoPacote`                    |
| Remover `NomedoPacote`                                   | `rm NomedoPacote`                     |
| Atualizar `NomedoPacote`                                 | `update NomedoPacote`                 |
| Usar versão de desenvolvimento                           | `dev NomedoPacote` or `dev URLdoRepositórioGit`|
| Parar de usar versão de desenvolvimento e reverter para versão pública | `free NomedoPacote`     |
