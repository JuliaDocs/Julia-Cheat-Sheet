Les macros permettent à du code généré (i.e. expressions) d'être 
inclus dans un programme. Voir le chapitre sur la [métaprogrammation](https://docs.julialang.org/en/v1/manual/metaprogramming/).

|                 |                                                            |
| --------------- | ---------------------------------------------------------- |
| Définition      | `macro macroname(expr)`<br>`    # do stuff`<br>`end`       |
| Usage           | `macroname(ex1, ex2, ...)` or `@macroname ex1, ex2, ...`   |
| Macros intégrées | `@test           # equal (exact)`<br>`@test x ≈ y    # isapprox(x, y)`<br>`@assert         # assert (unit test)`<br>`@which          # types utilisés`<br>`@time           # statistiques de tmeps et mémoire`<br>`@elapsed        # temps écoulé`<br>`@allocated      # mémoire allouée`<br>`@profile        # profil`<br>`@spawn          # exécuter sur un travailleur quelconque`<br>`@spawnat        # exécuter sur un travailleur spécifique`<br>`@async          # tâche asynchrone`<br>`@distributed    # parallélisation pour boucles`<br>`@everywhere     # rendre disponible à tous les travailleurs` |


Règles pour créer des macros hygiéniques:

- Déclarer les variables internes à la macro avec `local` .
- Ne pas appeler `eval` au sein de la macro.
- Echapper les expressions interpolées pour éviter l'expansion: `$(esc(expr))`
