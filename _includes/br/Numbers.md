|                                    |                                                                                      |
| ---------------------------------- | ------------------------------------------------------------------------------------ |
| Integer types                      | `IntN` e `UIntN`, com `N ∈ {8, 16, 32, 64, 128}`, `BigInt`                        |
| Floating-point types               | `FloatN` com `N ∈ {16, 32, 64}`<br>`BigFloat`                                       |
| Minimum and maximum values by type | `typemin(Int8)`<br>`typemax(Int64)`                                                  |
| Complex types                      | `Complex{T}`                                                                         |
| Unidade imaginária                     | `im`                                                                                 |
| Precisão da máquina                  | `eps() # same as eps(Float64)`                                                       |
| Arredondamento                           | `round() # floating-point`<br>`round(Int, x) # integer`                             |
| Type conversions                   | `convert(TypeName, val) # attempt/error`<br>`typename(val) # calls convert` |
| Constantes Globais                   | `pi # 3.1415...`<br>`π  # 3.1415...`<br>`im # real(im * im) == -1`   |
| Outras constantes                     | `using Base.MathConstants`                                                           |

Julia does not automatically check for numerical overflow. Use package
[SaferIntegers](https://github.com/JeffreySarnoff/SaferIntegers.jl) for ints
with overflow checking.
