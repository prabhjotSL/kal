#Change Log

### [0.4.6](https://github.com/rzimmerman/kal/compare/r0.4.5...r0.4.6)
* Fixes to the `but` operator. It was failing to compile in certain cases, such as when combined with `not`.
* Added support for bitwise operators (see the README for a full list).
* Fixed an issue where you could not have an `if` statement directly after a multiline object definition.
* Multiple return values from `wait for`s now actually work.
* Fixed a (cosmetic) issue with JavaScript output for standard `return` statements.

### [0.4.5](https://github.com/rzimmerman/kal/compare/r0.4.4...r0.4.5)
* Cleaned up the npm configuration for users building the repo manually (does not affect npm repository packages)
* Fixed a bug with the command line tool where things like list comprehensions were not working when running a script directly with `kal`

### [0.4.4](https://github.com/rzimmerman/kal/compare/r0.4.3...r0.4.4)
* Fixed a bug with `try` blocks containing `wait for` statements that could throw unexpected errors when nested in certain ways
* Improvements to the command-line tool
* Added the ability to compile a whole directory and recursive directories to the command-line tool
* Fixed some issues with the `in` and `instanceof` operators in the REPL

### [0.4.3](https://github.com/rzimmerman/kal/compare/r0.4.2...r0.4.3)
* Fixed a bug with `for parallel` blocks that could cause them to return multiple times
* Better syntax error reporting in `catch` blocks
* Added support for `catch` blocks with no error variable
* `wait for` statements now work in the main file body instead of just in functions
* Added support for `safe wait for` for functions that don't call back with an error argument
* `wait for` statements now work in the REPL and bare files
* Added the `pass` keyword for blank statements (like Python)
* Added the `print` keyword as an alias for `console.log`

### [0.4.2](https://github.com/rzimmerman/kal/compare/r0.4.1...r0.4.2)
* Added support for no-brace multiline CoffeeScript style object assignments
* Fixed a bug with double quoted strings as the first argument to function calls
* Better error messages for when `wait for` statements get included in `catch` blocks

### [0.4.1](https://github.com/rzimmerman/kal/compare/r0.4.0...r0.4.1)
* Fixed the REPL and executable to actually work correctly

### [0.4.0](https://github.com/rzimmerman/kal/compare/r0.3.2...r0.4.0)
* Added support for `wait for` statements which simplify callback use
* `wait for` statements are supported inside conditionals and loops
* `for` loops have a `parallel` or `series` specifier available for when they contain `wait for` statements
* `try` blocks also support `wait for` statements
* Fixed some bugs with tail conditionals
* Fixed a bug where parentheses were not optional if the last line of a file was a function call
* Output files are now beautified by default using uglify-js. They can also be minified or "compact" which is just standard output without most of the whitespace.
* Known issues: the REPL is not really complete (scope is reset between each line) and running a script directly from the command line using `kal script.kal` doesn't always work right. Compiling a script using `kal -o out_dir/ script.kal` works fine.

### [0.3.2](https://github.com/rzimmerman/kal/compare/r0.3.1...r0.3.2)
* Better error reporting from the compiler
* List comprehension over objects is supported using the syntaxes:

    [expr(p) for property p of y]
    [expr(v) for property value v of y]
    [expr(p,v) for property p with value v of y]

* Fixed a bug where you couldn't call a function with a list argument and implicit parens like `myfunc [1,2,3]`
* Multi-line lists with optional commas (like CoffeeScript) are now supported. Multiline objects are not supported yet.
* Some fixes to the command line tool to get it to work with node.js 0.6.x. No promises, though.

### [0.3.1](https://github.com/rzimmerman/kal/compare/r0.3.0...r0.3.1)
* Support for list comprehensions using the `[expr(x) for x in y]` syntax

### [0.3.0](https://github.com/rzimmerman/kal/compare/r0.2.9...r0.3.0)
* Indentation on blank lines is now ignored
* The `Kal.eval` options argument is now optional
* Better Javascript output for comments

### [0.2.9](https://github.com/rzimmerman/kal/compare/r0.2.8...r0.2.9)
* Significant performance improvements for compile time
* Fixed the command line options to the `kal` executable
* Much better error reporting for syntax errors
* Fixed a bug to allow no-parentheses function calls in for and while loop headers

### [0.2.8](https://github.com/rzimmerman/kal/compare/r0.2.7...r0.2.8)
* Fixed some issues with escape sequences in strings
* Fixed some issues with conditional return statements
* Included an interactive shell which now runs be default if you run `kal` with no arguments.

### [0.2.7](https://github.com/rzimmerman/kal/compare/r0.2.6...r0.2.7)
* Added a proper npmignore file to reduce the package size
* Added this change log
* Added support for reserved words as properties and function calls to reserved word properties

### [0.2.6](https://github.com/rzimmerman/kal/compare/r0.2.5...r0.2.6)
* Now correctly parses and compiles expressions inside of double-quoted strings. Previous versions just
  treated these as Javascript
* Added support for the `super` keyword

### [0.2.5](https://github.com/rzimmerman/kal/tree/8d994cca210638b2ac2518a2f7bbe598e067a418) - Nov 25 2012
* Fixes reported version (was reporting 0.2.3 for version 0.2.4)

### [0.2.4](https://github.com/rzimmerman/kal/tree/c6a34fc132f15a10b787e5814d89648e27061aee) - Nov 25 2012
* Added a `kal` command line tool
* Still reports version 0.2.3 in some places (bug)

### [0.2.3](https://github.com/rzimmerman/kal/tree/f5a8cac5bace0a3d96b92f4d125a09026a4b9ae2) - Nov 25 2012
* Fixes to trailing conditionals on function calls with implicit parentheses

### [0.2.2](https://github.com/rzimmerman/kal/tree/4798522fef3e41fc40f2b7819cd41c75a1b1f16a) - Nov 25 2012
* Fixed the npm package.json file (was causing failed installs)

### [0.2.1](https://github.com/rzimmerman/kal/tree/914db52fa3a158c36b22bbde3480d9d8ba5bec3f) - Nov 25 2012
* Added support for negative unary expressions (`-3`)
* Added support for `!=` and `==`
* Full support for function calls without parentheses
* Added support for `not in` and `not of` operators
* Removed CoffeeScript source files

### [0.2.0](https://github.com/rzimmerman/kal/tree/63075434b0343520d0c4f9c7a0460742108d96b9) - Nov 24 2012
* Removed dependency on CoffeeScript, thought the .coffee files are still included for reference

### [0.1.0](https://github.com/rzimmerman/kal/tree/021497d75468bd648bf36944d5ab528f7185b8c9) - Nov 24 2012
* Initial release
