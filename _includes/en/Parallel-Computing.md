Parallel computing tools are available in the `Distributed` standard library.

|                                            |                                   |
| ------------------------------------------ | --------------------------------- |
| Launch REPL with N workers                 | `julia -p N`                      |
| Number of available workers                | `nprocs()`                        |
| Add N workers                              | `addprocs(N)`                     |
| See all worker ids                         | `for pid in workers()`<br>`    println(pid)`<br>`end` |
| Get id of executing worker                 | `myid()`                          |
| Remove worker                              | `rmprocs(pid)`                    |
| Run f with arguments args on pid           | `r = remotecall(f, pid, args...)`<br>`# or:`<br>`r = @spawnat pid f(args)`<br>`...`<br>`fetch(r)` |
| Run f with arguments args on pid (more efficient) | `remotecall_fetch(f, pid, args...)` |
| Run f with arguments args on any worker    | `r = @spawn f(args) ... fetch(r)` |
| Run f with arguments args on all workers   | `r = [@spawnat w f(args) for w in workers()] ... fetch(r)` |
| Make expr available to all workers         | `@everywhere expr`                |
| Parallel for loop with <a class="tooltip" href="#">reducer<span>A reducer combines the results from different (independent) workers.</span></a> function red | `sum = @distributed (red) for i in 1:10^6`<br>`    # do parallelstuff`<br>`end` |
| Apply f to all elements in collection coll | `pmap(f, coll)`                   |

Workers are also known as concurrent/parallel processes.

Modules with parallel processing capabilities are best split into a
functions file that contains all the functions and variables needed by
all workers, and a driver file that handles the processing of data. The
driver file obviously has to import the functions file.

A non-trivial (word count) example of a reducer function is provided by
[Adam DeConinck](https://web.archive.org/web/20231209184522/https://blog.ajdecon.org/parallel-word-count-with-julia-an-interesting/).
