Los paquetes han de estar [registrados](https://pkg.julialang.org) antes de ser visibles
para el gestor de paquetes. En Julia 1.0, hay dos formas de trabajar con el gestor de
paquetes: bien con las funciones `using Pkg` y `Pkg`, o bien tecleando `]` en el REPL
para entrar en el modo especial Gestión de Paquetes Interactiva. (Para volver al REPL
normal sólo hay que presionar `BACKSPACE` en una línea vacía en el modo de gestión de
paquetes). Tenga en cuenta que las herramientas nuevas llegan antes al modo interactivo,
y después usualmente también se hacen disponibles en sesiones normales de Julia por
medio del módulo `Pkg`.

## Utilizando `Pkg` en una sesión Julia

|                                               |                            |
| --------------------------------------------- | -------------------------- |
| Listar paquetes instalados (human-readable)   | `Pkg.status()`             |
| Listar paquetes instalados (machine-readable) | `Pkg.installed()`          |
| Actualizar todos los paquetes                 | `Pkg.update()`             |
| Instalar `PackageName`                        | `Pkg.add("PackageName")`   |
| Compilar `PackageName`                        | `Pkg.build("PackageName")` |
| Utilizar `PackageName` (después de instalar)  | `using PackageName`        |
| Eliminar `PackageName`                        | `Pkg.rm("PackageName")`    |

## En Modo Gestión de Paquetes Interactiva

|                                                                 |                                       |
| --------------------------------------------------------------- | ------------------------------------- |
| Instalar `PackageName`                                          | `add PackageName`                     |
| Eliminar `PackageName`                                          | `rm PackageName`                      |
| Actualizar `PackageName`                                        | `update PackageName`                  |
| Usar versión de desarrollo                                      | `dev PackageName` o `dev GitRepoUrl`  |
| Parar el uso de versión de desarrollo, volver a versión pública | `free PackageName`                    |
