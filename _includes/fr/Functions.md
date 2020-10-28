Tous les arguments de fonctions sont passés par référence.

Par convention, les fonctions dont le nom se termine par `!` changent (mutent)
au moins l'un de leurs arguments (en général le premier). Par exemple :
`sort!(arr)`.

Les arguments positionnels sont séparés par une virgule. Ils sont obligatoires,
sauf si une valeur par défaut est fournie dans la signature de la fonction, au
moyen du signe `=`. A partir du premier argument optionnel, tous les arguments
positionnels suivants doivent aussi être optionnels.

Les arguments par mot-clé sont identifiés par leur nom, et listés dans la
signature de fonction après un point-virgule :

````
function func(req1, req2, opt1=dflt1; key1=dflt1, key2=dflt2)
    # do stuff
end
````

Le point-virgule n'est *pas* nécessaire pour identifier les arguments par
mot-clé lors de l'appel à la fonction :
```
func(val_req1, val_req2, key1=val_key1)
# opt1 et key2: valeur par défaut
```

Le mot-clé `return` est optionnel. S'il n'est pas présent, la valeur de la
dernière expression évaluée est renvoyée.

On peut renvoyer plusieurs valeurs en utilisant un `Tuple`: `return (val1, val2)`

Les arguments passés à Julia en ligne de commande (`julia script.jl arg1
 arg2...`) peuvent être récupérés dans la constante globale `ARGS`:

```
for arg in ARGS
    println(arg)
end
```

Les fonctions anonymes sont souvent utiles en conjonction avec des fonctions
d'ordre supérieur ou des listes en compréhension:
`x -> x^2`.

Les fonctions peuvent accepter un nombre variable d'arguments:
```
function func(a...)
    println(a)
end

func(1, 2, [3:5]) # tuple: (1, 2, UnitRange{Int64}[3:5])
```

Les déclarations de fonctions peuvent être imbriquées:

```
function outerfunction()
    # do some outer stuff
    function innerfunction()
        # do inner stuff
        # can access prior outer definitions
    end
    # do more outer stuff
end
```

Les fonctions peuvent spécifier un type pour leur arguments ainsi que leur
résultat :

```
# accepte n'importe quel argument sous-typant un nombre,
# et le renvoie sous forme de chaîne de caractères
function stringifynumber(num::T)::String where T <: Number
    return "$num"
end
```

Les fonctions peuvent être
["vectorisées"](https://docs.julialang.org/en/v1/manual/functions/#man-vectorized-1),
(appliquées élément-par-élément) en utilisant la syntaxe "`.`" :

```
julia> using Statistics
julia> A = rand(3, 4);

# La soustraction est "broadcastée" ici
julia> B = A .- mean(A, dims=1)
3×4 Array{Float64,2}:
  0.0387438     0.112224  -0.0541478   0.455245
  0.000773337   0.250006   0.0140011  -0.289532
 -0.0395171    -0.36223    0.0401467  -0.165713
julia> mean(B, dims=1)
1×4 Array{Float64,2}:
 -7.40149e-17  7.40149e-17  1.85037e-17  3.70074e-17
```

Julia génère des <a class="tooltip" href="#">versions spécialisées<span> Le
dispatch multiple choisit la *méthode* la plus adaptée aux types d'arguments
fournis (dynamiquement, *i.e* sur la base des types de valeurs constatés lors de
l'exécution). A partir du code de la méthode choisie, la spécialisation permet
ensuite de générer un code binaire natif optimal pour les types d'arguments
fournis. Tout ceci est différent de la surcharge de fonctions, qui s'appuie
exclusivement sur les types connus à la compilation.</span></a> de chaque
fonction, pour chaque type de données passées en argument. Quand une fonction
est appelée à nouveau pour les mêmes types d'arguments, une version précédemment
spécialisée peut être ré-utilisées ce qui évite d'avoir à repasser par une phase
de compilation.

Il est possible que l'ensemble des méthodes définies conduisent à des ambiguïtés
*potentielles*, mais réaliser effectivement un appel à une méthode ambiguë
provoque une **erreur** à l'exécution.

Des dépassements de pile (*Stack Overflows*) peuvent arriver lorsque des appels
de fonctions récursives s'imbriquent sur trop de niveaux. Des techniques de
[trampoline](https://web.archive.org/web/20140420011956/http://blog.zachallaun.com/post/jumping-julia)
peuvent être mises en place pour émuler l'optimisation de la récursivité
terminale (*Tail Call Optimization*), que Julia ne réalise pas ([encore
?](https://github.com/JuliaLang/julia/issues/4964)) par défaut. Les situations
de récursivité terminale peuvent aussi être récrites sous forme de boucle.
