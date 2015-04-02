# closure-compiler
Nim binding to [closure compiler](http://closure-compiler.appspot.com) web API.

# Usage example: nakefile
```Nim
import nake
import browsers
import closure_compiler

task "js", "Create Javascript version":
    direShell nimExe, "js", "main"
    closure_compiler.compileFileAndRewrite("nimcache" / "main.js", SIMPLE_OPTIMIZATIONS)
    openDefaultBrowser "main.html"
```
[More about nake](https://github.com/fowlmouth/nake)

# Usage example: command line
```sh
nim js main # Compile main.nim and save it to nimcache/main.js
closure_compiler nimcache/main.js # Run closure compiler
```

