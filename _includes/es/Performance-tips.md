- Escriba código con 
  [tipos estables](https://www.johnmyleswhite.com/notebook/2013/12/06/writing-type-stable-code-in-julia).
- De hecho, utilice tipos inmutábles cuando sea posible.
- Use `sizehint` para matrices grandes.
- Libere memoria para matrices grandes con `arr = nothing`.
- Accese las matrices por medio de columnas, ja que las matrices multidimensionales son guardadas por orden de columna.
- Pre-asigne las estructuras de datos resultantes.
- Desactive el recolector de basura e operaciones en tiempo real: `disable_gc()`.
- Evite el operador de propagación (`...`) para argumentos clave-valor.
- Use APIs mutables (es decir, funciones con `!` para evitar la copia de estructuras de datos).
- Utilice operaciones de matrices de elemento a elemento matriz en lugar de listas por comprensión.
- Evite `try`-`catch` en bucles de cálculo intensivo.
- Evite `Any` en colecciones.
- Evite tipos abstractos en colecciones.
- Evite interpolación de cadenas de texto en E/S.
- La [Vectorización](https://www.johnmyleswhite.com/notebook/2013/12/22/the-relationship-between-vectorized-and-devectorized-code "https://www.johnmyleswhite.com/notebook/2013/12/22/the-relationship-between-vectorized-and-devectorized-code")
  no mejora la velocidad (a diferencia de R, MATLAB o Python).
- Evite `eval` en tiempo de ejecución.
