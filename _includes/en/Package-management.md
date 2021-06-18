Packages must be [registered](https://pkg.julialang.org) before they are visible to the
package manager. In Julia 1.0, there are two ways to work with the package manager:
either with `using Pkg` and using `Pkg` functions, or by typing `]` in the REPL to
enter the special interactive package management mode. (To return to regular REPL, just
hit `BACKSPACE` on an empty line in package management mode). Note
that new tools arrive in interactive mode first, then usually also
become available in regular Julia sessions through `Pkg` module.

## Using `Pkg` in Julia session

|                                            |                            |
| ------------------------------------------ | -------------------------- |
| List installed packages (human-readable)   | `Pkg.status()`             |
| Update all packages                        | `Pkg.update()`             |
| Install `PackageName`                      | `Pkg.add("PackageName")`   |
| Rebuild `PackageName`                      | `Pkg.build("PackageName")` |
| Use `PackageName` (after install)          | `using PackageName`        |
| Remove `PackageName`                       | `Pkg.rm("PackageName")`    |

## In Interactive Package Mode

|                                                          |                                       |
| -------------------------------------------------------- | ------------------------------------- |
| Add `PackageName`                                        | `add PackageName`                     |
| Remove `PackageName`                                     | `rm PackageName`                      |
| Update `PackageName`                                     | `update PackageName`                  |
| Use development version                                  | `dev PackageName` or `dev GitRepoUrl` |
| Stop using development version, revert to public release | `free PackageName`                    |
