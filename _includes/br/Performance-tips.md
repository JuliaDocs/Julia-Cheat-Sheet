- Write
  [type-stable](https://www.johnmyleswhite.com/notebook/2013/12/06/writing-type-stable-code-in-julia)
  code.
- In fact, use immutable types where possible.
- Use `sizehint` for large arrays.
- Free up memory for large arrays with `arr = nothing`.
- Access arrays along columns, because multi-dimensional arrays are stored in column-major order.
- Pre-allocate resultant data structures.
- Disable the garbage collector in real-time applications: `disable_gc()`.
- Avoid the splat (`...`) operator for keyword arguments.
- Use mutating APIs (i.e. functions with `!` to avoid copying data structures.
- Use array (element-wise) operations instead of list comprehensions.
- Avoid `try`-`catch` in (computation-intensive) loops.
- Avoid `Any` in collections.
- Avoid abstract types in collections.
- Avoid string interpolation in I/O.
- [Vectorizing](https://www.johnmyleswhite.com/notebook/2013/12/22/the-relationship-between-vectorized-and-devectorized-code "https://www.johnmyleswhite.com/notebook/2013/12/22/the-relationship-between-vectorized-and-devectorized-code")
  does not improve speed (unlike R, MATLAB or Python).
- Avoid `eval` at run-time.
