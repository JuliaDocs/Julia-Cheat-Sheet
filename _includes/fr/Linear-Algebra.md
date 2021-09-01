Pour accéder à la plupart des outils d'algèbre linéaire, utiliser `using LinearAlgebra`.

|                                |                                             |
| ------------------------------ | ------------------------------------------- |
| Matrice identité               | `I  # utiliser seulement la variable I. Se conformera automatiquement aux dimensions requises.` |
| Définir une matrice            | `M = [1 0; 0 1]`                            |
| Dimensions d'une matrice       | `size(M)`                                   |
| Sélectionner la `i`-ème ligne  | `M[i, :]`                                   |
| Sélectionner la `i`-ème colonne | `M[:, i]`                                  |
| Concaténer horizontalement     | `M = [a b]` or `M = hcat(a, b)`             |
| Concaténer verticalement       | `M = [a ; b]` or `M = vcat(a, b)`           |
| Transposition de matrice       | `transpose(M)`                              |
| Transposition de matrice conjuguée | `M'` or `adjoint(M)`                    |
| Trace de la matrice            | `tr(M)`                                     |
| Déterminant de la matrice      | `det(M)`                                    |
| Rang de la matrice             | `rank(M)`                                   |
| Valeurs propres de la matrice  | `eigvals(M)`                                |
| Vecteurs propres de la matrice | `eigvecs(M)`                                |
| Matrice inverse                | `inv(M)`                                    |
| Résoudre `M*x == v`            | `M\v` est <a class="tooltip" href="#">meilleur <span>Numériquement plus stable et aussi plus rapide. </span></a> que `inv(M)*v` |
| Pseudo-inverse de Moore-Penrose | `pinv(M)`                                  |

Julia supporte nativement la [décomposition 
de matrice](https://docs.julialang.org/en/v1.0.0/stdlib/LinearAlgebra/).

Julia essaie d'inférer le type d'une matrice (si elle est symétrique,
hermitienne, etc.), mais y échoue parfois. Pour aider Julia à exécuter 
les algorithmes optimaux, des matrices spéciales peuvent être déclarées 
pour avoir une structure avec des fonctions comme `Symmetric` , `Hermitian` ,
 `UpperTriangular`, `LowerTriangular`, `Diagonal` , et d'autres.
