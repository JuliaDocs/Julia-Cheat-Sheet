Todos os argumentos das funções são passadas por referências.

Funções com `!` mudam pelo menos um argumento, tipicamente o primeiro:
`sort!(argumento)`.

Argumentos requiridos são separados por uma vírgula e usam a notação posicional

Argumentos opcionais precisam de um valor padrão na signatura, definido por `=`.

Argumentos de palavra-chave (keyword) usam a notação nomeada e são listados na signatura
depois da vírgula:

````
function func(req1, req2; key1=dflt1, key2=dflt2)
    # faça algo!
end
````

A vírgula *não* é necessária na chamada de uma função que aceita argumentos de palavra-chave (keyword)

O comando `return` é opcional, mas fortemente recomendado.

Multiplas estruturas de dados podem ser retornadas como uma tupla em um único comando `return`.

Argumentos de linha de comando `julia script.jl arg1 arg2...` podem ser processados pela constante 
global `ARGS`:

```
for arg in ARGS
    println(arg)
end
```

Funções anônimas podem ser melhor utilizadas em coleções de funções ou list comprehensions:
`x -> x^2`.

Funções podem aceitar uma quantidade variável de argumentos:

```
function func(a...)
    println(a)
end

func(1, 2, [3:5]) # tupla: (1, 2, UnitRange{Int64}[3:5])
```

Funções podem ser aninhadas:

```
function funcaoexterna()
    # faça coisas externas
    function funcaointerna()
        # faça coisas internas
        # pode acessar funções externas anteriores a ela
    end
    # faça mais coisas externas
end
```

Funções podem ter tipos de retorno explícitos

```
# pegue qualquer subtipo de número e retorne ele como uma String
function stringifynumber(num::T)::String where T <: Number
    return "$num"
end
```

Funções podem ser
[vetorizadas](https://docs.julialang.org/en/v1/manual/functions/#man-vectorized-1)
usando a Sintaxe de Ponto (Dot Syntax)

```
# aqui nós transmitimos a subtração de cada valor
# usando o operador (.)
julia> using Statistics
julia> A = rand(3, 4);
julia> B = A .- mean(A, dims=1)
3×4 Array{Float64,2}:
  0.0387438     0.112224  -0.0541478   0.455245
  0.000773337   0.250006   0.0140011  -0.289532
 -0.0395171    -0.36223    0.0401467  -0.165713
julia> mean(B, dims=1)
1×4 Array{Float64,2}:
 -7.40149e-17  7.40149e-17  1.85037e-17  3.70074e-17
```

Julia gera <a class="tooltip" href="#">versões especializadas<span>
 Multiple dispatch a type of
polymorphism that dynamically determines which version of a function to
call. In this context, dynamic means that it is resolved at run-time,
whereas method overloading is resolved at compile time. Julia manages
multiple dispatch completely in the background. Of course, you can
provide custom function overloadings with type annotations. </span></a>
em funções baseadas em tipos de dados. Quando uma função é executada com o
mesmo argumento novamente, Julia pode procurar o código de máquina nativo
e pular o processo de compilação.

Desde **Julia 0.5** a existência de potenciais
ambiguidades ainda é aceitável, mas executar 
um método ambíguo é um **erro imediato**

Transbordo de pilha (Stack overflow) é possível quando
funções recursivas aninham a varios níveis de profundidade.
[Trampolining](https://web.archive.org/web/20140420011956/http://blog.zachallaun.com/post/jumping-julia) pode
ser utilizado para a otimização chamadas recursivas, já que Julia não faz
isso automaticamente [ainda](https://github.com/JuliaLang/julia/issues/4964).

Alternativamente, você pode reescrever a recursão como uma iteração.