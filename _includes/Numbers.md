|                                    |                                                                                      |
| ---------------------------------- | ------------------------------------------------------------------------------------ |
| Integer types                      | `IntN` and `UIntN`, with `N ∈ {8, 16, 32, 64, 128}`, `BigInt`                        |
| Floating-point types               | `FloatN` with `N ∈ {16, 32, 64}`<br>`BigFloat`                                       |
| Minimum and maximum values by type | `typemin(Int8)`<br>`typemax(Int64)`                                                  |
| Complex types                      | `Complex{T}`                                                                         |
| Imaginary unit                     | `im`                                                                                 |
| Machine precision                  | `eps() # same as eps(Float64)`                                                       |
| Rounding                           | `round() # floating-point`<br>`round(Int, x) # integer`                             |
| Type conversions                   | `convert(TypeName, val) # attempt/error`<br>`typename(val) # calls convert` |
| Global constants                   | `pi # 3.1415...`<br>`π  # 3.1415...`<br>`im # real(im * im) == -1`   |
| More constants                     | `using Base.MathConstants`                                                           |

Julia does not automatically check for numerical overflow. Use package
[SaferIntegers](https://github.com/JeffreySarnoff/SaferIntegers.jl) for ints
with overflow checking.
