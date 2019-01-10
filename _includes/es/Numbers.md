|                                        |                                                                    |
| -------------------------------------- | ------------------------------------------------------------------ |
| Tipos de entero                        | `IntN` y `UIntN`, con `N ∈ {8, 16, 32, 64, 128}`, `BigInt`         |
| Tipos de coma flotante                 | `FloatN` con `N ∈ {16, 32, 64}`<br>`BigFloat`                      |
| Valores máximos y mínimos de cada tipo | `typemin(Int8)`<br>`typemax(Int64)`                                |
| Tipos complejos                        | `Complex{T}`                                                       |
| Unidad imaginaria                      | `im`                                                               |
| Precisión de la máquina                | `eps() # igual que eps(Float64)`                                   |
| Redondeo                               | `round()       # punto flotante`<br>`round(Int, x) # entero`       |
| Conversiones de tipos                  | `convert(TypeName, val)  # tentativa/error`<br>`typename(val)           # llama al conversor` |
| Constantes globales                    | `pi # 3.1415...`<br>`π  # 3.1415...`<br>`im # real(im * im) == -1` |
| Otras constantes                       | `using Base.MathConstants`                                         |

Julia no comprueba automáticamente el desbordamiento numérico. Use el paquete
[SaferIntegers](https://github.com/JeffreySarnoff/SaferIntegers.jl) para enteros
con comprobación de desbordamiento.
