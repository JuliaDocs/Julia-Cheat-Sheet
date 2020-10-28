Les paquets doivent être [enregistrés](https://pkg.julialang.org) avant de
pouvoir être désignés par leur nom en utilisant le gestionnaire de paquets. La
plupart des commandes ci-dessous acceptent aussi une URL de dépôt git pour
identifier un paquet non-enregistré. Le gestionnaire de paquets de Julia 1.0
peut être utilisé de deux manières : en tapant `using Pkg` puis en utilisant les
fonctions du module `Pkg`, ou bien en entrant dans le mode REPL dédié à la
gestion des paquets à l'aide de la touche `]` (Pour revenir au REPL Julia
standard, tapez `[BackSpace]` dans une ligne vide). NB: les nouvelles
fonctionnalités de `Pkg` arrivent souvent dans le mode REPL interactif, avant
d'intégrer l'API du module `Pkg`.

## Utiliser les fonctions de `Pkg` dans un code Julia

|                                                                   |                            |
| ------------------------------------------                        | -------------------------- |
| Lister les paquets installés (format pour humains)                | `Pkg.status()`             |
| Lister les paquets installés (format pour traitement automatique) | `Pkg.installed()`          |
| Mettre à jour les paquets                                         | `Pkg.update()`             |
| Installer `PackageName`                                           | `Pkg.add("PackageName")`   |
| Reconstruire `PackageName`                                        | `Pkg.build("PackageName")` |
| Utiliser `PackageName` (après installation)                       | `using PackageName`        |
| Supprimer `PackageName`                                           | `Pkg.rm("PackageName")`    |

## Dans le REPL interactif en mode `pkg`

|                                            |                                       |
| --------------------------------------     | ------------------------------------- |
| Installer `PackageName`                    | `add PackageName`                     |
| Supprimer `PackageName`                    | `rm PackageName`                      |
| Mettre à jour `PackageName`                | `update PackageName`                  |
| Utiliser une version de développement      | `dev PackageName` ou `dev GitRepoUrl` |
| Après `dev`, revenir à une version publiée | `free PackageName`                    |
