Los módulos son espacios de trabajo con variables globales que agrupan funcionalidades similares.

|                       |                                                      |
| --------------------- | ---------------------------------------------------- |
| Definición            | `module PackageName`<br>`# añadir las definiciones del módulo`<br>`# usar export para hacer las definiciones accesibles`<br>`end` |
| Incluir `filename.jl` | `include("filename.jl")`                             |
| Cargar                | `using ModuleName        # todos los nombres exportados`<br>`using ModuleName: x, y              # sólo x, y`<br>`using ModuleName.x, ModuleName.y:   # sólo x, y`<br>`import ModuleName       # sólo ModuleName`<br>`import ModuleName: x, y             # sólo x, y`<br>`import ModuleName.x, ModuleName.y   # sólo x, y` |
| Exportar              | `# Obtiene una matriz de nombres exportada por el módulo`<br>`names(Modulename)`<br><br>`# incluye no-exportables, obsoletos`<br>`# y nombres generados por el compilador`<br>`names(ModuleName, all:Bool)`<br><br>`# también muestra nombres importados`<br><br>`# explícitamente desde otros módulos`<br>`names(ModuleName, all::Bool, imported::Bool)` |

Sólo hay una diferencia entre `using` e `import` : con `using` es necesario escribir
`function Foo.bar(..` para extender la función `bar` del módulo `Foo` con un nuevo método, 
mientras que con `import Foo.bar` sólo se necesita escribir `function bar(...` y extenderá
automáticamente la función `bar` del módulo `Foo`.
