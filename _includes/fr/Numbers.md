|                                    |                                                                    |
| ---------------------------------- | ------------------------------------------------------------------ |
| Type Entier                        | `IntN` et `UIntN`, avec `N ∈ {8, 16, 32, 64, 128}`, `BigInt`      |
| Type Flottant                      | `FloatN` avec `N ∈ {16, 32, 64}`<br>`BigFloat`                     |
| Valeurs minimale et maximale de types | `typemin(Int8)`<br>`typemax(Int64)`                                |
| Type Complex                       | `Complex{T}`                                                       |
| Unité imaginaire                   | `im`                                                               |
| Précision de la machine            | `eps() # identique à eps(Float64)`                                     |
| Arrondi                            | `round()       # flottant`<br>`round(Int, x) # entier`      |
| Conversion de type                 | `convert(TypeName, val)  # essai/erreur`<br>`typename(val)           # appelle une conversion` |
| Constantes globales                | `pi # 3.1415...`<br>`π  # 3.1415...`<br>`im # real(im * im) == -1` |
| Autres constantes                  | `using Base.MathConstants`                                         |

Julia ne vérifie pas automatiquement les dépassements numériques. Utiliser le 
paquet [SaferIntegers](https://github.com/JeffreySarnoff/SaferIntegers.jl) pour 
employer des Entiers en contrôlant les dépassements.
