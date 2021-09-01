- Eviter les variables globales.
- Ecrire du code
  [type-stable](https://www.johnmyleswhite.com/notebook/2013/12/06/writing-type-stable-code-in-julia).
- Utiliser des types immuables autant que possible.
- Utiliser `sizehint!` pour les tableaux larges.
- Libérer de la mémoire pour les tableaux larges ainsi: `arr = nothing`.
- Accéder aux tableaux par les colonnes, dans la mesure où les tableaux multi-dimensionnels sont stockés en premier lieu en fonction des colonnes.
- Pre-allouer les structures de donnée résultantes.
- Désactiver le ramasse-miettes dans les applications en temps réel: `disable_gc()`.
- Eviter d'utiliser l'opérateur *splat* (`...`) comme mot-clé d'argument.
- Utiliser des APIs transformantes (i.e. fonctions avec `!`) pour éviter de copier des structures de données.
- Utiliser des opérations de tableau (par élément) au lieu de sous-parties (*comprehensions*).
- Eviter les `try`-`catch` dans les boucles (notamment de calcul intensif).
- Eviter les `Any` dans les collections.
- Eviter les types abstraits dans les collections.
- Eviter l'interpolation de chaînes en Entrée/Sortie.
- [Vectoriser](https://www.johnmyleswhite.com/notebook/2013/12/22/the-relationship-between-vectorized-and-devectorized-code "https://www.johnmyleswhite.com/notebook/2013/12/22/the-relationship-between-vectorized-and-devectorized-code")
  n'améliore pas la rapidité (au contraire de R, MATLAB ou Python).
- Eviter `eval` lors de l'exécution.
