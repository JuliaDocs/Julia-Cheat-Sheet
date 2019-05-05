|                  |                       |
| ---------------- | --------------------- |
| name の型        | `typeof(name)`        |
| 型をチェックする    | `isa(name, TypeName)` |
| 下位型(サブタイプ) を列挙する | `subtypes(TypeName)`  |
| 上位型(スーパータイプ) を得る | `supertype(TypeName)` |
| 名前 func のメソッドを列挙する | `methods(func)`       |
| JIT バイトコードを表示する  | `code_llvm(expr)`     |
| ネイティブコードを表示する  | `code_native(expr)`   |
