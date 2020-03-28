|                  |                                |
| ---------------- | ------------------------------ |
| Type             | `typeof(name)`                 |
| Type check       | `isa(name, TypeName)`          |
| Type stable check| `code_warntype(f, (types,))`   |
| List subtypes    | `subtypes(TypeName)`           |
| List supertype   | `supertype(TypeName)`          |
| Function methods | `methods(func)`                |
| JIT bytecode     | `code_llvm(expr)`              |
| Assembly code    | `code_native(expr)`            |
