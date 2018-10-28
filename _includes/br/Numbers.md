|                                    |                                                                                      |
| ---------------------------------- | ------------------------------------------------------------------------------------ |
| Tipo inteiro                      | `IntN` e `UIntN`, com `N ∈ {8, 16, 32, 64, 128}`, `BigInt`                        |
| Tipos de ponto flutuante               | `FloatN` com `N ∈ {16, 32, 64}`<br>`BigFloat`                                       |
| Valores mínimo e máximo por tipo | `typemin(Int8)`<br>`typemax(Int64)`                                                  |
| Tipo complexo                      | `Complex{T}`                                                                         |
| Unidade imaginária                     | `im`                                                                                 |
| Precisão da máquina                  | `eps() # o mesmo que eps(Float64)`                                                       |
| Arredondamento                           | `round() # ponto flutuante`<br>`round(Int, x) # inteiro`                             |
| Conversão de tipo                   | `convert(TypeName, val) # tentativa/erro`<br>`typename(val) # chama conversor` |
| Constantes Globais                   | `pi # 3.1415...`<br>`π  # 3.1415...`<br>`im # real(im * im) == -1`   |
| Outras constantes                     | `using Base.MathConstants`                                                           |

O Julia não checa automaticamente o overflow numérico. Use o pacote
[SaferIntegers](https://github.com/JeffreySarnoff/SaferIntegers.jl) para inteiros
com verificação de overflow.
