Les outils de calcul parallèle sont disponibles dans la librairie standarde `Distributed`.

|                                            |                                   |
| ------------------------------------------ | --------------------------------- |
| Lancer REPL avec N travailleurs            | `julia -p N`                      |
| Nombre de travailleurs disponibles         | `nprocs()`                        |
| Ajouter N travailleurs                     | `addprocs(N)`                     |
| Voir tous les IDs des travailleurs         | `for pid in workers()`<br>`    println(pid)`<br>`end` |
| Obtenir l'ID du travailleur exécutant      | `myid()`                          |
| Enlever travailleur                        | `rmprocs(pid)`                    |
| Exécuter f avec les arguments args via pid | `r = remotecall(f, pid, args...)`<br>`# ou:`<br>`r = @spawnat pid f(args)`<br>`...`<br>`fetch(r)` |
| Exécuter f avec les arguments args via pid (plus efficace) | `remotecall_fetch(f, pid, args...)` |
| Exécuter f avec les arguments args via n'importe quel travailleur | `r = @spawn f(args) ... fetch(r)` |
| Exécuter f avec les arguments args via tous les travailleurs | `r = [@spawnat w f(args) for w in workers()] ... fetch(r)` |
| Rendre expr disponible à  tous les travailleurs | `@everywhere expr`                |
| Parallélisation pour boucle avec la fonction <a class="tooltip" href="#">réductrice<span>Un réducteur combine les résultats de différents travailleurs (indépendants).</span></a> red | `sum = @distributed (red) for i in 1:10^6`<br>`    # travail parallèle `<br>`end` |
| Applique f à tous les éléments de la collection coll | `pmap(f, coll)`                   |

Les travailleurs sont aussi appelés processus concurrents/parallèles.

Il vaut mieux que les modules avec des capacités de processus parallèle 
soient partagés au sein d'un fichier de fonctions qui contient toutes les 
fonctions et variables requises par tous les travailleurs, et un fichier pilote
qui gère le traitement de la donnée. Le pilote doit évidemment importer le 
fichier de fonctions.

Un exemple non-trivial (décompte de mots) d'une fonction reductrice est procuré par
[Adam DeConinck](https://blog.ajdecon.org/parallel-word-count-with-julia-an-interesting).
