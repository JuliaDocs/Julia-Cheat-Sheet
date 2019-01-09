|                                   |                                             |
| --------------------------------- | ------------------------------------------- |
| Declaration                       | `arr = Float64[]`                           |
| Pre-allocation                    | `sizehint!(arr, 10^4)`                      |
| Access and assignment             | `arr = Any[1,2]`<br>`arr[1] = "Some text"`  |
| Comparison | `a = [1:10;]`<br>`b = a      # b points to a`<br>`a[1] = -99`<br>`a == b     # true` |
| Copy elements (not address)       | `b = copy(a)`<br>`b = deepcopy(a)`          |
| Select subarray from m to n       | `arr[m:n]`                                  |
| n-element array with 0.0s         | `zeros(n)`                                  |
| n-element array with 1.0s         | `ones(n)`                                   |
| n-element array with #undefs      | `Vector{Type}(undef,n)`                     |
| n equally spaced numbers from start to stop | `range(start,stop=stop,length=n)` |
| Array with n random Int8 elements | `rand(Int8, n)`                             |
| Fill array with val               | `fill!(arr, val)`                           |
| Pop last element                  | `pop!(arr)`                                 |
| Pop first element                 | `popfirst!(a)`                              |
| Push val as last element          | `push!(arr, val)`                           |
| Push val as first element         | `pushfirst!(arr, val)`                      |
| Remove element at index idx       | `deleteat!(arr, idx)`                       |
| Sort                              | `sort!(arr)`                                |
| Append a with b                   | `append!(a,b)`                              |
| Check whether val is element      | `in(val, arr) or val in arr`                |
| Scalar product                    | `dot(a, b) == sum(a .* b)`                  |
| Change dimensions (if possible)   | `reshape(1:6, 3, 2)' == [1 2 3; 4 5 6]`     |
| To string (with delimiter del between elements) | `join(arr, del)`              |
