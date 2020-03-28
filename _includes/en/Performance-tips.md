See full [Performance Tips][Tips] in julia's manual.

## General Tips
- Avoid global variables.
- Write [type-stable][type-stable] code.
- Use immutable types where possible.
- Measure performance with `@time` and pay attention to memory allocation.
- Break functions into multiple definitions.

## Arrays
- Pre-allocate resultant data structures.
- Use `sizehint!` for large arrays.
- Consider using views for slices.
- Access arrays along columns, because multi-dimensional arrays are stored in column-major order.
- Free up memory for large arrays with `arr = nothing`.
- Disable the garbage collector in real-time applications: `disable_gc()`.
- Use mutating APIs (i.e. functions with `!` to avoid copying data structures.
- Use array (element-wise) operations instead of list comprehensions.

## Other Tips
- Avoid the splat (`...`) operator for keyword arguments.
- Avoid `try`-`catch` in (computation-intensive) loops.
- Avoid `Any` in collections.
- Avoid abstract types in collections.
- Avoid string interpolation in I/O.
- Avoid `eval` at run-time.
- [Vectorizing][vectorized] does not improve speed (unlike R, MATLAB or Python).
- Fix deprecation warnings.

[Tips]: https://docs.julialang.org/en/v1/manual/performance-tips/
[type-stable]: https://www.johnmyleswhite.com/notebook/2013/12/06/writing-type-stable-code-in-julia
[vectorized]: https://www.johnmyleswhite.com/notebook/2013/12/22/the-relationship-between-vectorized-and-devectorized-code
