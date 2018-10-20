|                                    |                                                                                      |
| ---------------------------------- | ------------------------------------------------------------------------------------ |
| Tipo inteiro                      | `IntN` e `UIntN`, com `N ∈ {8, 16, 32, 64, 128}`, `BigInt`                        |
| Tipos de pontos flutuantes               | `FloatN` com `N ∈ {16, 32, 64}`<br>`BigFloat`                                       |
| Tipos de valores de máximo e mínimo | `typemin(Int8)`<br>`typemax(Int64)`                                                  |
| Tipo complexo                      | `Complex{T}`                                                                         |
| Unidade imaginária                     | `im`                                                                                 |
| Precisão da máquina                  | `eps() # o mesmo que eps(Float64)`                                                       |
| Arredondamento                           | `round() # floating-point`<br>`round(Int, x) # integer`                             |
| Tipos de conversões                   | `convert(TypeName, val) # attempt/error`<br>`typename(val) # calls convert` |
| Constantes Globais                   | `pi # 3.1415...`<br>`π  # 3.1415...`<br>`im # real(im * im) == -1`   |
| Outras constantes                     | `using Base.MathConstants`                                                           |

O Julia não checa automaticamente o overflow. Use o pacote
[SaferIntegers](https://github.com/JeffreySarnoff/SaferIntegers.jl) para checar o 
overflow de inteiros.
