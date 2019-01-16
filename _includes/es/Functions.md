Todos los argumentos se pasan a la función por referencia.

Las funciones con un `!` añadido cambian por lo menos uno de los argumentos,
habitualmente el primero: `sort!(arr)`.

Los argumentos obligatorios son separados por una coma y usan la notación posicional.

Los argumentos opcionales necesitan un valor en la firma de la función, definida con `=`.

Los argumentos clave-valor utilizan la notación nominativa y son listados en la firma
de la función después del punto y coma:

````
function func(req1, req2; key1=dflt1, key2=dflt2)
    # do stuff
end
````

El punto y coma *no* es necesario en una llamada a una función que acepta argumentos clave-valor.

La sentencia `return` es opcional pero altamente recomendable.

Se pueden devolver estructuras de datos múltiples como un tuple e una única sentencia `return`.

Los argumentos de la línea de comandos `julia script.jl arg1 arg2...` pueden ser procesados con
la constante global `ARGS`:

```
for arg in ARGS
    println(arg)
end
```

Las funciones anónimas son óptimas para funciones de colecciones o listas por comprensión:
`x -> x^2`.

Las funciones pueden aceptar un número variable de argumentos:

```
function func(a...)
    println(a)
end

func(1, 2, [3:5]) # tuple: (1, 2, UnitRange{Int64}[3:5])
```

Las funciones pueden ser anidadas:

```
function outerfunction()
    # bloque de código de función outerfunction
    function innerfunction()
        # bloque de código de función innerfunction
        # puede acceder definiciones anteriores de outerfunction
    end
    # bloque de código adicional de función outerfunction
end
```

Las funciones pueden devolver tipos explícitos

```
# take any Number subtype and return it as a String
function stringifynumber(num::T)::String where T <: Number
    return "$num"
end
```

Las funciones son
[vectorizables](https://docs.julialang.org/en/v1/manual/functions/#man-vectorized-1)
por medio de la sintaxis de punto (Dot Syntax)

```
# aqui emitimos la resta de cada valor medio
# por medio del operador punto
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

Julia crea <a class="tooltip" href="#">versiones especializadas<span> El despacho múltiple es un tipo
polimorfismo que determina dinámicamente qué versión de una función debe ser llamada.
En este contexto significa que es resuelto en tiempo de ejecución, mientras que la
sobrecarga de métodos es resuelta en tiempo de compilado. Julia gestiona el despacho
múltiple completamente en segundo plano. Por supuesto, se pueden proporcionar
sobrecargas de función personalizadas con anotaciones de tipo. </span></a>
de funciones basada en los tipos de los datos. Cuando una función es llamada con
los mismos tipos de argumento de nuevo, Julia puede consultar el código 
máquina nativo y saltarse el proceso de compilado.

Desde **Julia 0.5** la existencia de ambigüedades potenciales de tipo 
es aún aceptable, pero llamar um método ambiguo supone un **error inmediato**.

El desbordamiento de pila es posible en el caso de funciones recursivas se anidan
a lo largo de varios niveles. El ["Trampolining"](https://web.archive.org/web/20140420011956/http://blog.zachallaun.com/post/jumping-julia) 
se puede utilizar para hacer una optimización de recursión con llamadas de cola, ya que Julia no lo hace automáticamente
[aún](https://github.com/JuliaLang/julia/issues/4964).
Como alternativa, puede reescribir la recursión de cola como una iteración.
