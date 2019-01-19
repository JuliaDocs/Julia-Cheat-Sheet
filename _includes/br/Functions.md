Todos os argumentos das funções são passados por referências.

Functions with `!` appended change at least one argument, typically the first:
`sort!(arr)`.


Required arguments are separated with a comma and use the positional notation.

Optional arguments need a default value in the signature, defined with `=`.

Keyword arguments use the named notation and are listed in the function's
signature after the semicolon:

````
function func(req1, req2; key1=dflt1, key2=dflt2)
    # do stuff
end
````

The semicolon is *not* required in the call to a function that accepts keyword arguments.

The `return` statement is optional but highly recommended.

Multiple data structures can be returned as a tuple in a single `return` statement.

Command line arguments `julia script.jl arg1 arg2...` can be processed from global
constant `ARGS`:

```
for arg in ARGS
    println(arg)
end
```

Anonymous functions can best be used in collection functions or list comprehensions:
`x -> x^2`.

Functions can accept a variable number of arguments:

```
function func(a...)
    println(a)
end

func(1, 2, [3:5]) # tuple: (1,2,[3,4,5])
```

Functions can be nested:

```
function outerfunction()
    # do some outer stuff
    function innerfunction()
        # do inner stuff
        # can access prior outer definitions
    end
    # do more outer stuff
end
```

Functions can have explicit return types

```
# take any Number subtype and return it as a String
function stringifynumber(num::T)::String where T <: Number
    return "$num"
```

Functions can be
[vectorized](https://docs.julialang.org/en/release-0.5/manual/functions/#dot-syntax-for-vectorizing-functions)
by using the Dot Syntax

```
# here we broadcast the subtraction of each mean value
# by using the dot operator
julia> A = rand(3,4);
julia> B = A .- mean(A,1)
3×4 Array{Float64,2}:
0.343976   0.427378  -0.503356  -0.00448691
-0.210096  -0.531489   0.168928  -0.128212
-0.13388    0.104111   0.334428   0.132699
julia> mean(B,1)
1×4 Array{Float64,2}:
0.0  0.0  0.0  0.0
```

Julia generates <a class="tooltip" href="#">specialized versions<span> Multiple dispatch a type of
polymorphism that dynamically determines which version of a function to
call. In this context, dynamic means that it is resolved at run-time,
whereas method overloading is resolved at compile time. Julia manages
multiple dispatch completely in the background. Of course, you can
provide custom function overloadings with type annotations. </span></a>
of functions based on data types. When a function is called with the
same argument types again, Julia can look up the native machine code and
skip the compilation process.

Since **Julia 0.5** the existence of potential
ambiguities is still acceptable, but actually calling an ambiguous
method is an **immediate error**.

Stack overflow is possible when recursive functions nest many levels
deep. [Trampolining](https://blog.zachallaun.com/post/jumping-julia) can
be used to do tail-call optimization, as Julia does not do that
automatically [yet](https://github.com/JuliaLang/julia/issues/4964).
Alternatively, you can rewrite the tail recursion as an iteration.
