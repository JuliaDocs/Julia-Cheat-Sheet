Les modules sont des espaces de noms séparés qui groupent des fonctionnalités similaires.

|                           |                                                                                                                                                                                                                                                                                                          |
| ---------------------     | ----------------------------------------------------                                                                                                                                                                                                                                                     |
| Définition de module      | `module PackageName`<br>`# déclarations de fonctions, types...`<br>`# 'export' rend les définitions accessibles`<br>`end`                                                                                                                                                                                |
| Inclure un fichier source | `include("filename.jl")`                                                                                                                                                                                                                                                                                 |
| Chargement                | `# tous les noms exportés`<br>`using ModuleName`<br>`# uniquement x, y`<br>`using ModuleName: x, y`<br>`# uniquement ModuleName`<br>`import ModuleName`<br>`# uniquement x, y`<br>`# accessibles à l'extension de méthodes`<br>`import ModuleName: x, y`<br>`import ModuleName.x, ModuleName.y`          |
| Liste des définitions     | `# Liste des noms exportés par ModuleName`<br>`names(ModuleName)`<br><br>`# y compris non-exportés, obsolètes`<br>`# et noms générés par le compilateur`<br>`names(ModuleName, all::Bool)`<br><br>`# y compris noms importés d'un autre module`<br>`names(ModuleName, all::Bool, imported::Bool)` |

Une fonction `foo` rendue visible par `using Foo` ne peut être étendue par une
nouvelle méthode qu'explicitement : `function Foo.bar(...)`.

Avec `import Foo.bar`, l'ajout de méthode peut être non qualifié :
`function bar(...)` suffit.
